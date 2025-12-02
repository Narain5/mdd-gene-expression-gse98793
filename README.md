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
