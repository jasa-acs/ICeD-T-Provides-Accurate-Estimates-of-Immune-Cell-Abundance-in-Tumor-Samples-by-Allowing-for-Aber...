# ICeD-T Provides Accurate Estimates of Immune Cell Abundance in Tumor Samples by Allowing for Aberrant Gene Expression Patterns

# Author Contributions Checklist Form

## Data

### Abstract

We have used three datasets to evaluate our method. The first one is gene expression and flow cytometry data from peripheral blood of 20 healthy adults (Newman et al. 2015, Nature methods, 12(5), 453-457). The second one is gene expression and flow cytometry data from four melanoma patients (Racle et al. 2017, eLife 6, e26476). In both datasets, gene expression data were used to estimate cell type composition and the cell type composition measured by flow cytometry serve as a gold standard to compare. The third dataset include gene expression and clinical outcomes for 28 melanoma patients from a clinical trial of immunotherapy (Hugo et al. 2016, Cell, 165(1), 35–44). 

### Availability 

All the data are publicly available. 

The data of Newman et al. was downloaded from https://cibersort.stanford.edu/download.php, labeled by “Fig 3a PBMCs Gene Expression” and “Fig 3a PBMCs Flow Cytometry”.  

The data of Racle et al. was downloaded from their R package, which is available at https://github.com/GfellerLab/EPIC. The data we used were extracted from an Rdata object located at “EPIC-master/data/melanoma_data.rda” in the R package. 

For Hugo et al., we have downloaded the gene expression (RNA-seq) data from NCBI Sequence Read Archive under the accession numbers SRP067938 and SRP090294, and downloaded patient information data from the supplementary materials of their paper. 


### Description 

We have included the data needed to reproduce our results as well as our code in GitHub: https://github.com/Sun-lab/ICeDT/tree/master/scripts

This folder also includes some sample code to generate simulated data. 


## Code

### Abstract

We have implemented our method as an R package ICeD-T.

### Description

The R package as well as detailed readme file is available at  https://github.com/Sun-lab/ICeDT/

In a subfolder scripts, we have all the codes needed to reproduce our real data analyses results and simulation studies. The version of ICeD-T is 0.99.1 and the versions of all relevant R packages are listed below. 


## Instructions for Use

### Reproducibility 

All the results of our analyses can be reproduced. The real data analyses take multiple steps because we have started from raw data. Briefly, after downloading the raw RNA-seq read data in fastq format, we mapped them to human genome using STAR with gene annotation from GENCODE version 27. Then the number of RNA-seq fragments per gene were counted using R function GenomicAlignments/summarizeOverlaps. Next the gene expression data were normalized by TPM as described in the paper. 

We have provided the R code to reproduce the results in our GitHub websites using processed data. The README file at https://github.com/Sun-lab/ICeDT/ provides an example to run ICeDT. The simulation code is located at scripts/simulation/R. The real data analysis code is located at scripts/programs/running_ICeDT_on_Hugo_data.R. 

Computational time. ICeDT is computationally very efficient. For our simulations using 1,000 initial values for 250 genes and 5 cell types (including tumor as one cell type), it took 35 seconds (hence 0.035 second per run) given tumor purity, and it took 230 seconds (hence 0.23 second per run) without given tumor purity. The record of computational time can be found at 
https://github.com/Sun-lab/ICeDT/blob/master/scripts/simulation/R/Simulation_Diff_Initial.Rout. 

The computation was done on a Macbook Pro with 2.3G Intel Core i9 CPU. 
