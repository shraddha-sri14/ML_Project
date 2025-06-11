# **Exploring Neuronal Subtypes in Alzheimer's Disease: A Single-Cell RNA-Seq and Machine Learning Study**

This project investigates the selective vulnerability (SV) of specific neuronal subtypes in Alzheimer's disease (AD) using single-cell RNA sequencing (scRNA-seq) data and machine learning approaches. By analyzing gene expression patterns in postmortem brain tissues, particularly focusing on excitatory neurons in the entorhinal cortex (EC), this study aims to understand the susceptibility of distinct neuronal populations to degeneration and identify potential therapeutic targets to enhance neuronal resilience.

This analysis leverages the Seurat pipeline, a widely used tool for scRNA-seq data processing, adapted from the official PBMC3K tutorial but applied to a different dataset and with additional customizations.

## **Table of Contents**

* [**Abstract**](#abstract)
* [**Motivation**](#motivation)
* [**Research Gap**](#research-gap)
* [**Contribution**](#contribution)
* [**Methodology**](#methodology)
    * [**Cell Nuclei Isolation and Data Generation**](#cell-nuclei-isolation-and-data-generation)
    * [**Workflow**](#workflow)
* [**Tools and Libraries**](#tools-and-libraries)
* [**Results**](#results)
    * [**Cluster Analysis**](#cluster-analysis)
    * [**Biomarker Discovery**](#biomarker-discovery)
    * [**Dimensionality Reduction**](#dimensionality-reduction)
* [**Conclusion and Future Work**](#conclusion-and-future-work)
* [**Data and Methods**](#data-and-methods)
    * [**Dataset**](#dataset)
    * [**Pipeline**](#pipeline)
* [**How to Run**](#how-to-run)
* [**References**](#references)
* [**Contact**](#contact)

## **Abstract**

Alzheimer’s disease (AD) is characterized by tau pathology, neuronal loss with specific spatiotemporal patterns, and selective vulnerability (SV) of certain neuronal populations. This study utilizes scRNA-seq data derived from postmortem brain tissues to analyze gene expression and identify selectively vulnerable neuronal subtypes, focusing on excitatory neurons in the entorhinal cortex (EC). By employing hierarchical clustering and dimensional reduction methods, nine clusters (s1 to s9) were identified, with significant reduction in clusters s1, s2, and s4. Biomarkers like RORB were identified and validated as major markers for selective vulnerability. Through machine learning and clustering algorithms, we examined neuronal subtypes, their biomarkers, and their role in disease progression, providing insights for therapeutic strategies.

## **Motivation**

The motivation behind this study is to understand why certain neuronal populations are more susceptible to degeneration in AD. This understanding is critical in identifying therapeutic targets and enhancing neuronal resilience. AD is known for its selective vulnerability (SV), where specific neuronal types in brain regions like the entorhinal cortex (EC) are affected earlier and more severely. The study focuses on elucidating the molecular mechanisms behind this SV using advanced computational and molecular techniques.

## **Research Gap**

Despite extensive research on network-level vulnerability in AD, cellular-level mechanisms of SV remain poorly understood. Key gaps include:

* Limited understanding of the genetic and molecular factors driving SV.
* Lack of information on neuronal subpopulation variability in susceptibility.
* Insufficient knowledge of selective resilience (SR) and its relation to tau pathology or synaptic dysfunction.

Understanding these gaps can yield insights into disease mechanisms and therapeutic strategies.

## **Contribution**

This study contributes to AD research by:

* Identifying the optimal resolution for stable clustering, yielding biologically meaningful cell clusters.
* Discovering RORB as a major marker for selectively vulnerable excitatory neurons in the EC.
* Highlighting significant neuronal loss in clusters s1, s2, and s4, along with variations in biomarker expression across subpopulations.
* Performing refined subpopulation analyses to reveal differential loss patterns between neuronal populations.
* Unveiling biomarkers such as CD24, CSMD1, CADPS2, TLL1, and DOCK4 linked to selectively vulnerable neuronal subtypes.

## **Methodology**

### **Cell Nuclei Isolation and Data Generation**

Postmortem brain tissues were processed for snRNA-seq analysis, focusing on the entorhinal cortex (EC) and superior frontal gyrus (SFG). A total of 42,528 cells were analyzed, including 8,362 excitatory neurons. Using machine learning approaches, clustering algorithms identified distinct neuronal subtypes, and biomarker analysis highlighted selectively vulnerable populations.

### **Workflow**

The data analysis was performed using the Seurat pipeline and included the following steps:

**Preprocessing:**

* Loading the dataset (sce.EC.Exc.scAlign.rds) and converting it to a Seurat object.
* Identification of highly variable features.
* Data Scaling and Dimensional Reduction:

**Dimensional Reduction:**

* Scaling the data using ScaleData.
* Performing Linear dimensional reduction (PCA, ICA).
* Generating Elbow plots to determine the optimal dimensionality.

**Clustering:**

* Running FindNeighbors and FindClusters with varying resolution parameters.
* Visualizing the dependency of clusters on different resolutions.

**Marker Identification:**

* Identifying cluster markers using FindMarkers and FindAllMarkers.
* Filtering and visualizing top markers.

**Visualization:**

* Generating cluster plots for t-SNE and UMAP projections.
* Plotting features of interest, such as the RORB gene.

## **Tools and Libraries**

**Programming Language:** R

**Libraries:** Seurat, scater, cowplot, dplyr, patchwork, ggpubr

**Algorithms:** Louvain community detection, hierarchical clustering

**Dataset:** Entorhinal cortex excitatory neurons from Leng et al., 2021.

## **Results**

### **Cluster Analysis**

* Identified nine clusters (s1-s9) at resolution 0.4.
* Observed significant neuronal loss in clusters s1, s2, and s4.
* Stable clusters identified at resolutions 9, 12, and 26.

### **Biomarker Discovery**

* RORB was confirmed as a major marker for selectively vulnerable neurons.
* Additional biomarkers, including CD24, CSMD1, CADPS2, and DOCK4, were identified for cluster 3.

### **Dimensionality Reduction**

* Visualized clusters using t-SNE and UMAP.
* DimHeatmaps highlighted co-expressed genes driving principal components.

## **Conclusion and Future Work**

This study highlights selective vulnerability (SV) in AD, identifying neuronal subtypes and biomarkers associated with neurodegeneration. Key findings include:

* Identification of biomarkers like RORB and CD24 for selectively vulnerable neurons.
* Insights into differential neuronal loss in Braak stages 2 and 6.

Future work includes:

* Validating biomarkers for cluster 3 and expanding biomarker exploration.
* Investigating subtypes of cell clusters exhibiting selective neuronal loss.
* Exploring therapeutic targets and drug development based on identified biomarkers.

## **Data and Methods**

### **Dataset**

Entorhinal cortex excitatory neurons from the dataset published in Leng et al., 2021, Nature. The specific file used is `sce.EC.Exc.scAlign.rds`.

### **Pipeline**

The single-cell RNA sequencing data analysis was performed using the Seurat pipeline in R, adapted from the official Seurat PBMC3K tutorial ([**References**](#references)) with modifications to suit the specific dataset and research questions.

The key steps included:

1.  **Loading the dataset:** Reading the `sce.EC.Exc.scAlign.rds` file and converting it into a Seurat object.
2.  **Preprocessing:** Normalization, identification of 2,000 highly variable genes, and scaling.
3.  **Dimensional Reduction:** Principal Component Analysis (PCA) and determination of significant principal components using Elbow plots.
4.  **Clustering:** Graph-based clustering using the `FindNeighbors` and `FindClusters` functions with varying resolution parameters to identify stable cell populations.
5.  **Non-linear Dimensional Reduction:** Visualization of cell clusters using Uniform Manifold Approximation and Projection (UMAP) and t-distributed Stochastic Neighbor Embedding (t-SNE).
6.  **Marker Identification:** Identification of differentially expressed genes for each cluster using the `FindMarkers` and `FindAllMarkers` functions to characterize neuronal subtypes and potential biomarkers.
7.  **Visualization:** Generation of UMAP and t-SNE plots to visualize clusters and the expression of key marker genes.

## **How to Run**

1.  **Clone this repository:** `git clone [repository URL]`
2.  **Place the dataset:** Download the `sce.EC.Exc.scAlign.rds` file and place it in the root directory of the cloned repository.
3.  **Run the code:** Execute the R code provided in `Project code.txt`. Ensure you have the necessary R libraries (Seurat, scater, cowplot, dplyr, patchwork, ggpubr) installed.
4.  **Output:** The final Seurat object containing the analysis results will be saved as `pbmc_tutorial.rds` in the working directory.

## **References**

* Leng, et al. (2021). A molecularly defined signature for entorhinal cortex excitatory neurons. Nature.
* Seurat PBMC3K Tutorial: [Link to the Seurat PBMC3K Tutorial if available]


