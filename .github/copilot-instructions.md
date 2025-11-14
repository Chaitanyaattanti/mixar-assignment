# Copilot Instructions for This Repo

Purpose: Help AI coding agents work productively in this repository.

## Overview
- This repo currently contains 3D mesh assets only, under `8samples/`.
- File types observed: `.obj` meshes (e.g., `girl.obj`, `table.obj`, `explosive.obj`) and one PDF reference.
- There is no application code, build system, or tests present.

## Repository Structure
- `8samples/`: Small set of example meshes for downstream use.
  - Examples: `girl.obj`, `person.obj`, `table.obj`, `cylinder.obj`, `fence.obj`, `explosive.obj`, `talwar.obj`, `branch.obj`.
- No package manifests (`package.json`, `requirements.txt`, etc.) found.

## Typical Tasks in This Repo
- Preview meshes locally (e.g., quick viewer scripts or HTML pages).
- Validate/inspect geometry (counts, manifoldness, bounding boxes).
- Convert/optimize formats (OBJ → glTF/GLB, Draco compression).
- Organize assets and produce metadata for consumers.

## Conventions
- Assets live under `8samples/` and are referenced by relative paths.
- Do not rename or move existing files unless explicitly requested, as consumers may rely on stable paths.
- Keep added scripts/tools in a new folder (e.g., `tools/`) and avoid modifying original assets.

## Quick Start: Mesh Preview (Local)
- Python + trimesh quick inspection:
  ```python
  import trimesh
  m = trimesh.load('8samples/girl.obj')
  print(m.vertices.shape, m.faces.shape)
  m.show()  # opens viewer if available
  ```
- Node + three.js static viewer (minimal): create `viewer/index.html` and load `8samples/girl.obj` via `OBJLoader`.

## Conversion Examples
- Python + `assimp` via `pyassimp` or `trimesh` to export GLB:
  ```python
  import trimesh
  mesh = trimesh.load('8samples/table.obj')
  mesh.export('8samples/table.glb')
  ```
- glTF-Pipeline/obj2gltf (Node):
  ```bash
  npx obj2gltf -i 8samples/person.obj -o 8samples/person.gltf
  npx gltf-pipeline -i 8samples/person.gltf -o 8samples/person_draco.glb -d
  ```

## Validation Checklist
- Load success for each asset: `trimesh.load('8samples/<file>.obj')` without exceptions.
- Reasonable triangle/vertex counts for intended targets (mobile vs desktop).
- Unit scale expectations: assume meters unless consumer specifies otherwise.
- Origin and orientation: Y-up typical for many engines; confirm consumer needs.

## Adding Utilities
- Place scripts under `tools/` with a clear README on usage.
- Prefer cross-platform CLI usage with minimal dependencies.
- Output derived assets/metadata alongside originals or in `derived/`.

## Unknowns / Ask Before Assuming
- Target engines (Unity/Unreal/Three.js/WebXR) and required formats.
- Desired naming, LOD strategy, texture handling (none found in repo).
- Performance budgets and compression requirements.

## Safe Defaults for Agents
- Non-destructive by default: read/validate assets; don’t overwrite originals.
- If creating previews, use separate paths (e.g., `viewer/`, `derived/`).
- Keep commands copy-pasteable and paths relative to repo root.
