# Graph Transformer-Based Integration of Multiplex Spatial Transcriptomics and Morphology for Tumor Microenvironment Analysis​

This repository contains a complete pipeline for analyzing **spatial transcriptomics data** using **gene expression**, **morphological imaging features**, and an **attention-based graph neural network**. The workflow integrates multimodal data at the single-cell level to identify biologically meaningful cell populations and spatial tissue structure.

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
## Data Source

The primary dataset comes from the **Vizgen MERSCOPE FFPE Human Immuno-Oncology Data Release:**

🔗 [https://info.vizgen.com/ffpe-showcase?submissionGuid=c2b903c1-af36-4e0e-be04-08489f6aeb95](https://info.vizgen.com/ffpe-showcase?submissionGuid=c2b903c1-af36-4e0e-be04-08489f6aeb95)

* Generated using the **MERSCOPE Platform®** with MERFISH spatial transcriptomics technology.

* Includes multiple human tumor types measured using a **500-gene immuno-oncology panel**.

* This project specifically uses **Ovarian Cancer – Patient 2, Slice 2**, containing:

  * **71,381 cells**
  * Spatially resolved gene expression and imaging data

* Data includes:

  * Single-cell transcript counts
  * Spatial coordinates and segmentation masks
  * High-resolution DAPI images

* Blank control probes (~50) are included in the panel and were removed during preprocessing.

* Imaging data (Z-stack TIFFs) used for CNN-based feature extraction is available at:
  🔗 [https://console.cloud.google.com/storage/browser/vz-ffpe-showcase/HumanOvarianCancerPatient2Slice2/images](https://console.cloud.google.com/storage/browser/vz-ffpe-showcase/HumanOvarianCancerPatient2Slice2/images)

* The dataset is part of a larger release containing:

  * **16 samples across 8 cancer types**
  * **~4 billion transcripts and ~8.7 million cells**

To cite this data, please use:
**Vizgen MERFISH FFPE Human Immuno-oncology Data Set, May 2022.**

---
