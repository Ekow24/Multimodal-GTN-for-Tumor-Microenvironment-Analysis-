# Multimodal Spatial Transcriptomics Analysis: Integrating Gene Expression, Imaging, and Graph Learning for Cell-Type Identification

This repository contains a complete pipeline for analyzing **spatial transcriptomics data** using **gene expression**, **morphological imaging features**, and **graph-based deep learning**. The workflow integrates multimodal data at the single-cell level to identify biologically meaningful cell populations and spatial tissue structure.

---

## About

This project provides a reproducible framework for **multimodal single-cell analysis** by combining:

* Targeted spatial transcriptomics (gene expression)
* CNN-extracted morphological features from microscopy images
* Spatial graph-based representation learning

**Key goals:**

* Perform robust quality control tailored for spatial transcriptomics
* Integrate imaging and transcriptomic data at the single-cell level
* Learn spatially informed embeddings using graph neural networks
* Identify cell populations and annotate biological cell types
* Interpret clusters using marker genes and pathway enrichment

---

## Repository Structure

```
project/
│── README.md
│── requirements.txt
│── .gitignore
│
│── notebooks/
│ ├── 1_Data_loading_preprocessing_hvg.ipynb
│ ├── 2_CNN_feature_extraction.ipynb
│ ├── 3_Graph_model_construction.ipynb
│ └── 4_Clustering_annotation_and_pathway_analysis.ipynb
│
│── models/
│ └── CNN_embeddings.npy
│
└── dataset/
│ ├── raw/
│ ├── HumanOvarianCancerPatient2Slice2_cell_by_gene.csv
│ ├── HumanOvarianCancerPatient2Slice2_cell_metadata.csv
│ ├── processed/
│ ├── adata_500.h5ad
│ ├── adata_hvg_with_CNN_embeddings.h5ad
│ └── adata_with_graph_embeddings.h5ad
│ └── images/
```

**Notes:**

1. `notebooks/` contains step-by-step analysis in logical order.
2. `dataset/` includes raw data, processed AnnData files, and imaging data.
3. `models/` contains pretrained CNN weights.

---

## Visualizations

* UMAP (clusters & cell types)
* Spatial plots (tissue organization)
* PCA variance plots
* QC plots (violin, histogram, scatter)

---
