# ssTools

This repository contains all the code....

## Data for simulation

The RNA-Seq count data "Muscle.Expression.data.RData" and "Skin.Expression.data.RData" are extracted from GTEx Portal http://www.gtexportal.org/home. The Muscle count data consist of 102 esophagus muscle samples (group=0) and 151 skeletal muscle samples (group=1). The Skin count data consist of 152 non-sun-exposed samples (group=0) and 160 sun-exposed samples (group=1).

## Selecting_1000_DE_genes

R code for selection of 1000 differentially expressed (DE) genes out of the "Skin.Expression.data" ("Muscle.Expression.data.RData").
The output (e.g. "selected_genes_Muscle_1000_FC_2.RData") is used for the simulation and for pilot data generation.

Steps:
1. Filtering Genes out with less than 1 cpm in at least half of the samples. 
2. Alalysing genes for differential expression using edgeR, DESeq2 and DESeq (FDR=0.05).
3. Identify the intersection of DE genes with a predefined fold change in all three packages.
4. Randomly selecting 1000 DE genes out of the intersection.

## edgeR_simulation, DESeq2_simulation and DESeq_simulation

R codes for the simulation. 

## Contact

alpoplaw@uni-mainz.de
