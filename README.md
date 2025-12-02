# Gene Expression Analysis of Major Depressive Disorder (MDD) Using GEO Dataset GSE98793

This project analyzes whole-blood microarray data from the GEO dataset **GSE98793** to ask:

> **Can gene expression in blood distinguish Major Depressive Disorder (MDD) patients from healthy controls?**

The workflow includes data download, preprocessing, exploratory analysis (PCA, UMAP, heatmaps), differential expression testing, and machine learning classification (Logistic Regression and Random Forest).

---

## Dataset

- **Repository:** NCBI Gene Expression Omnibus (GEO)  
- **Accession:** [GSE98793](https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE98793)  
- **Platform:** Affymetrix Human Genome U133 Plus 2.0 (GPL570)  
- **Samples:** 128 MDD, 64 controls (whole blood)  

The raw data are *not* stored in this repository; they are downloaded directly from GEO using `GEOparse` in the notebook.


## Dataset Information

- Source: NCBI Gene Expression Omnibus (GEO)
- Accession ID: https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE98793
- Platform: GPL570 — Affymetrix Human Genome U133 Plus 2.0 Array
- Samples: 128 MDD patients, 64 healthy controls
- Tissue: Whole blood

Raw CEL files are not stored in this repository; they are downloaded automatically from GEO during notebook execution.

---

## How to Run the Analysis

### Option A — Run in Google Colab

1. Open `notebooks/Bioinformatics_final.ipynb`
2. Upload the notebook to Google Colab
3. Install dependencies:
4. Run all cells in order

### Option B — Run Locally

1. Clone the repository:
3. Run the notebook in Jupyter Notebook or VSCode

---

## Analysis Workflow

### 1. Data Download & Preprocessing
- Download GSE98793 using GEOparse
- Extract expression matrix and metadata
- Clean group labels and encode classes
- Select top 10,000 most variable probes

### 2. Exploratory Data Analysis
Includes:
- PCA
- UMAP
- Sample correlation heatmap
- Heatmap of top 50 variable probes

Observation:
MDD and Control samples show strong overlap and do not cluster separately.

### 3. Differential Expression
- Welch t-test per probe
- Benjamini–Hochberg FDR correction
- Volcano plot generation

Result:
No genes were significant after FDR correction. Effect sizes were small across all probes.

### 4. Machine Learning Classification
Models tested:
- Logistic Regression
- Random Forest

Performance Summary:

| Model | Accuracy | ROC-AUC | Notes |
|-------|----------|---------|-------|
| Logistic Regression | ~0.62 | 0.53 | Near random |
| Random Forest | ~0.62 | 0.63 | High recall for MDD, poor recall for controls |

Conclusion:
Gene expression does not provide strong predictive signal for distinguishing MDD from controls.

---

## Final Conclusion

All analyses indicate that whole-blood gene expression in GSE98793 does not strongly differentiate MDD patients from healthy controls. PCA and UMAP show overlapping clusters, differential expression reveals no significant genes after FDR correction, and machine learning models perform only slightly above random chance.

These results align with existing literature showing that peripheral blood typically reflects subtle, distributed regulation in psychiatric disorders rather than strong diagnostic biomarkers.

Future directions may include:

- Batch correction
- Covariate adjustments (age, sex, batch)
- Gene-set and pathway-level models
- Multi-omics integration
- Cell-type specific expression analysis

---

## AI Usage

See `ai_usage.md` for complete details.

AI was used for assistance with documentation, structuring analysis steps, and writing support. All data analysis, code execution, and result interpretation were performed manually.

---

## Citation

If using this repository, please cite:

Narain S. (2024). Gene Expression Analysis of Major Depressive Disorder (MDD) Using GEO Dataset GSE98793. GitHub.  
https://github.com/Narain5/mdd-gene-expression-gse98793

---

## Requirements

Primary Python libraries include:

- GEOparse
- numpy
- pandas
- matplotlib
- seaborn
- umap-learn
- scikit-learn

Full list is available in `requirements.txt`.

---

## Author

Narain Sarathy  
MS in Data Science  
University of Texas at Arlington


---

## Repository Structure

```text
mdd-gene-expression-gse98793/
├── data/
│   └── (placeholder; raw data downloaded via GEOparse)
├── notebooks/
│   ├── 01_download_preprocess_GSE98793.ipynb   # optional
│   └── Bioinformatics_final.ipynb             # main analysis notebook
├── results/
│   ├── figures/                               # PCA, UMAP, heatmaps, volcano, ML plots
│   └── tables/                                # DE results (e.g., DE_results_ttest_top10k.csv)
├── src/                                       # (reserved for helper scripts)
├── README.md
└── ai_usage.md

---
