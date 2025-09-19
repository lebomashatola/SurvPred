# **GeTopology**  
**Bimodal Phenotype Prediction from Multi-Modal Data**  
A tool combining **topological data analysis (TDA)**, **machine learning**, and **multi-modal data processing** (RNA-Seq, microarray, histopathology) to predict biological 
phenotypes.

---

## 🧠 **Overview**  
GeTopology processes:  
- RNA-Seq (`.fastq`)  
- Microarray (`.CEL`)  
- Tissue slides (`.SVS`)  

It uses **topological shape encoding** of gene expression data and **bimodal predictive learning** (CNN + MLP) to classify phenotypes from multi-modal datasets.

---

## 🧰 **Requirements**  
### **Programming Languages**  
- Python ≥ 3.9  
- R ≥ 4.0  

### **Software**  
- Linux/MacOS  
- [FastQC](https://www.bioinformatics.babraham.ac.uk/projects/fastqc/) 0.12.0  
- [Trimmomatics](http://www.usadellab.org/cms/?page=trimmomatic) 0.36  
- [STAR](https://github.com/alexdobin/STAR) 2.7.11a  
- [HTSeq](https://htseq.readthedocs.io/en/master/install.html) 2.0.3  

---

## 📦 **Installation**  
```bash
# Install Python dependencies
python -m pip install -r requirements.txt

# Install R dependencies
Rscript requirements.r
```

---

## 🚀 **Workflow**  
### **1. Data Processing**  
```bash
# Image Processing (Segmentation & Tiling)
python Image_Processing.py

# Microarray (RMA normalization for GPL570 CEL files)
python run_cels.py

# RNA-Seq (Process .fastq files)
python RNA-Seq_Processing.py

# Combine HTSeq counts into a Gene Expression Matrix
python Expression_Counts.py
```

### **2. Gene Preselection**  
```bash
# WGCNA with Deseq2/Limma
python run_preselection.py
```

### **3. Data Encoding**  
```bash
# Topological Data Analysis (Persistent Homology)
python generate_persistent_diagrams_images.py
```

### **4. Predictive Learning**  
```bash
# Topological Summaries → MLP
python phenotype_prediction.py

# Image Classification → CNN
python MobileNet.py

# Bimodal Classification (MLP + CNN)
python integrate.py
```

---

## 🧪 **Example Use Case**  
1. Process RNA-Seq and microarray data to generate gene expression matrices.  
2. Use TDA to extract topological features from gene expression.  
3. Train a CNN on histopathology images and an MLP on gene expression data.  
4. Combine results using a bimodal model to predict tumor subtypes or disease states.

---

## 🧑‍💻 **Authors**  
- [Lebohang Mashatola](mailto:681452@students.wits.ac.za)  
- [Mandeep Kaur](mailto:Mandeep.Kaur@wits.ac.za)  

---

## 📜 **Version History**  
- **0.1**  
  - Initial release with RNA-Seq, microarray, and image processing pipelines.  
  - Bimodal phenotype prediction using CNN + MLP.  

---

## 📄 **License**  
[MIT License](LICENSE)  

---

## 🤝 **Contributing**  
- Fork the repo and submit a pull request.  
- Add your name to the `AUTHORS.md` file.  
- Include test cases for new features.  

---

## 📌 **Notes**  
- Ensure all dependencies are installed and paths are correctly configured.  
- For advanced use, customize preprocessing pipelines in `run_preselection.py` and `integrate.py`.  

---
