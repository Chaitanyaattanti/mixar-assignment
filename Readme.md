

# **README.md**

## **Mesh Normalization, Quantization, and Reconstruction**

This Assignment  contains three Jupyter notebooks that implement the full preprocessing pipeline for 3D mesh data.
The tasks include loading the mesh, performing normalization, applying quantization, reconstructing the mesh, and computing error metrics.

---

## ** Files**

task-1.ipynb   → Mesh loading and inspection  
task-2.ipynb   → Normalization and quantization  
task-3.ipynb   → Reconstruction and error analysis  
8samples/      → Folder containing .obj input meshes  
outputs/       → Generated .ply and .png files  

---

## **▶ How to Run**

### 1. Create and activate a virtual environment

```bash
python3 -m venv .venv
source .venv/bin/activate
```

### 2. Install required packages

```bash
pip install numpy trimesh matplotlib pillow open3d  pyglet
```

### 3. Open the notebooks

```bash
jupyter notebook
```

Run **task-1**, then **task-2**, then **task-3** in order.


