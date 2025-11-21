# Gene Expression Analysis of Major Depressive Disorder (MDD)

This repository contains a complete bioinformatics workflow analyzing the GEO dataset **GSE98793**, which includes whole-blood gene expression data from **128 MDD patients** and **64 healthy controls**. The goal is to identify gene expression signatures associated with MDD and evaluate whether these signatures can separate case and control samples through exploratory analysis, dimensionality reduction, and later differential expression and machine learning.

---



## 📊 Dataset Information

**Source:** NCBI Gene Expression Omnibus  
**Accession:** [GSE98793](https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE98793)  
**Platform:** GPL570 — Affymetrix Human Genome U133 Plus 2.0 Array  
**Samples:**  
- 128 MDD patients  
- 64 healthy controls  

**Data Format:**  
- Series Matrix file (normalized microarray expression)  
- Phenotype metadata (subject group, age, gender, batch)

---

## ⚙️ How to Run the Analysis

This project is designed to run easily in **Google Colab**.

### 1. Clone or download the repository:
### 2. Open the notebook:
- Upload the notebook to Google Colab  
**OR**
- Use Colab’s "Open Notebook from GitHub" feature

### 3. Run Notebook 01:
This notebook performs:
- Data download (GEOparse)
- Preprocessing  
- Label encoding  
- Top 10k feature selection  
- PCA  
- Correlation heatmap  
- Top 50 gene heatmap  
- UMAP projection  

Outputs are stored in `/results/figures/`.

---

## 📈 Figures Generated (Week 1)

- PCA plot (Top 10k genes)  
- Sample correlation heatmap  
- Heatmap of top 50 most variable genes  
- UMAP projection  

These will support the draft and final reports.

---

## 🚧 Future Work (Week 2–3)

- Differential gene expression  
- Volcano plot  
- Machine learning classification  
- ROC/AUC curves  
- Biological interpretation  
- Final report writing  

---

## 🤖 AI Usage

See **ai_usage.md** for a complete explanation of how AI tools assisted in the project.

---

## 📜 License

This project is released under the MIT License (for academic use).
