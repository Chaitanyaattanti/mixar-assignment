
## **Mesh Normalization, Quantization, and Reconstruction**

This assignment contains three Jupyter notebooks that implement the full preprocessing pipeline for 3D mesh data.  
The tasks include loading the mesh, performing normalization, applying quantization, reconstructing the mesh, and computing error metrics.

A separate notebook is provided for the **Bonus Task (Seam Tokenization Prototype)**.

---

## **Files**

- **task-1.ipynb** → Mesh loading and inspection  
- **task-2.ipynb** → Normalization and quantization  
- **task-3.ipynb** → Reconstruction and error analysis  
- **bonus-task.ipynb** → Seam Tokenization Prototype (Optional Task)  
- **8samples/** → Folder containing `.obj` mesh files  
- **outputs/** → Generated `.ply` and `.png` files  

---

## **▶ How to Run**

### **1. Create and activate a virtual environment**

```bash
python3 -m venv .venv
source .venv/bin/activate
````

### **2. Install required packages**

```bash
pip install numpy trimesh matplotlib pyglet
```

### **3. Open the notebooks**

```bash
jupyter notebook
# Run task-1.ipynb, then task-2.ipynb, then task-3.ipynb in order.
# For each notebook, click: Run → Run All
```

---

## **▶ Running the Bonus Task 

 **Option 1: Seam Tokenization Prototype**, run the bonus notebook:

```bash
jupyter notebook bonus-task.ipynb
# Click Run All
```

No additional dependencies are required.

---

```
```
