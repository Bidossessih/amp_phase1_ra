# AMP Phase 1 RA

Accelerating Medicines Partnership Phase 1 Rheumatoid Arthritis

This repo has the code we used to analyze data and make figures in the
published manuscript:

> Zhang et al. TITLE, JOURNAL, DOI

## Overview

The files in the repo are organized as follows:

    .
    ├── R
    |── data

`R/` has code for analysis and creating figures.

`data/` has Excel sheets with sample metadata and RData files with processed data ready for analysis.

## Getting Started

Clone this repo:

```bash
cd ~/work/
git clone git@github.com:immunogenomics/amp_phase1_ra.git
cd amp_phase1_ra

# Download the data from Partners
rsync -avh rgs04:/data/srlab/public/srcollab/AMP/amp_phase1_ra/data .
```

## Multiple high-dimensional datasets analysis

#### CCA analysis of bulk and single-cell RNA-seq

We use canonical correlation analysis (CCA) to integrate bulk RNA-seq with
single-cell RNA-seq. See this file for a detailed walk-through of the analysis:

    R/scRNAseq_bulkRNAseq_integrative_pipeline.R

#### CCA analysis of bulk and single-cell RNA-seq

We use the regularized CCA to integrate bulk RNA-seq with mass cytometry. 
See this file for a detailed walk-through of the analysis:

    cytof_bulkRNAseq_integrative_pipeline.R
    
#### Identification of single-cell RNA-seq marker genes based on the cluster labels     
    
    cluster_marker_table.R
    
#### Differential analysis for bulk RNA-seq data

    limma_differential_bulk.R

#### Optimize leukocyte threshold to classify samples based on T cells, B cells, and monocytes by flow cytometry

    optimal_lymphocyte_threshold.R
    
#### Statistical analysis functions for PCA, densitiy analysis, etc

    pure_functioins.R
    

## Visualization of results to generate figures in the manuscript

#### Visualization of CCA-based framework results

    cca_bulk_singlecell_visualization

#### Visualization of mass cytometry clustering results

    cytof_results_plot.R
    
#### Plot flow gates for each disease cohort 

    Figure2_plots_krenn_flow.R

#### Plot DE markers for each single-cell RNA-seq cluster basedon AUC, wilcox p, FC, percent of non-zero expressing, etc

    plot_cluster_markers.R
    
#### Plot post-QC cells based on # genes detected vs. percent of Molecules from MT
    
    plot_genes_detected_mitoch.R
    



