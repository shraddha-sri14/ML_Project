# Single-cell RNA-Seq Analysis of Entorhinal Cortex Excitatory Neurons
This project demonstrates the analysis of single-cell RNA sequencing data using the Seurat pipeline. The dataset used in this analysis is from entorhinal cortex excitatory neurons published in the Leng et al., 2021 Nature paper.

The analysis includes clustering, dimensional reduction, and visualization of the dataset using various Seurat functions. The steps in the analysis are adapted from the Seurat PBMC3K tutorial, but with a different dataset and additional customizations.

# Project Files
Project code.txt: Contains the R code for the complete analysis pipeline.
pbmc_tutorial.rds: The final Seurat object saved after analysis.
Analysis Overview
The main steps in this project include:

# Data Preprocessing:

Loading the dataset (sce.EC.Exc.scAlign.rds) and converting it to a Seurat object.
Identification of highly variable features.
Data Scaling and Dimensional Reduction:

Scaling the data using ScaleData.
Performing linear dimensional reduction (PCA, ICA).
Generating Elbow plots to determine the optimal dimensionality.
Clustering:

Running FindNeighbors and FindClusters with varying resolution parameters.
Visualizing the dependency of clusters on different resolutions.
Non-linear Dimensional Reduction:

Running UMAP and t-SNE for visualization of clusters.
Exploring clustering results at different resolutions.
Marker Identification:

Identifying cluster markers using FindMarkers and FindAllMarkers.
Filtering and visualizing top markers.
Visualization:

Generating cluster plots for t-SNE and UMAP projections.
Plotting features of interest, such as the RORB gene.
Data and Methods
Dataset: Entorhinal cortex excitatory neurons from Leng et al., 2021.
Pipeline: The Seurat pipeline adapted from the official PBMC3K tutorial.
Tools and Libraries:
Seurat, scater, cowplot, dplyr, patchwork, ggpubr.

# How to Run
Clone this repository.
Place the dataset (sce.EC.Exc.scAlign.rds) in the working directory.
Run the code in Project code.txt using R.
The final Seurat object will be saved as pbmc_tutorial.rds.

# References
Leng, et al. (2021). A molecularly defined signature for entorhinal cortex excitatory neurons. Nature.
Seurat PBMC3K Tutorial

# Contact
For any queries regarding this analysis, feel free to contact the repository owner.
