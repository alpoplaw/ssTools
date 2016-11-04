# ssTools

This repository contains all the code for the simulation and sample size estimation in "Feasibility of sample size calculation for RNA-seq studies"

## Data for simulation

The RNA-Seq count data "Muscle.Expression.data.RData" and "Skin.Expression.data.RData" are extracted from GTEx Portal http://www.gtexportal.org/home. The Muscle count data consist of 102 esophagus muscle samples (group=0) and 151 skeletal muscle samples (group=1). The Skin count data consist of 152 non-sun-exposed samples (group=0) and 160 sun-exposed samples (group=1).

## Selecting 1000 DE genes

R code for selection of 1000 differentially expressed (DE) genes out of the "Skin.Expression.data" ("Muscle.Expression.data.RData").
The output (e.g. "selected_genes_Muscle_1000_FC_2.RData") is used for the simulation and for pilot data generation.  
Steps:  
1. Filtering Genes out with less than 1 cpm in at least half of the samples.  
2. Alalysing genes for differential expression using edgeR, DESeq2 and DESeq (FDR=0.05).  
3. Identify the intersection of DE genes with a predefined fold change in all three packages.  
4. Randomly selecting 1000 DE genes out of the intersection.  

## edgeR simulation, DESeq2 simulation and DESeq simulation

R codes for the simulation. Input see "Selecting 1000 DE genes".

##  Create Pilot Data

R codes for generation of 10 pilot data. Input see "Selecting 1000 DE genes".   

## Sample Size Estimation
Code to estimate the sample size using the 10 generated pilot data and the following tools:    
PROPER http://www.bioconductor.org/packages/release/bioc/html/PROPER.html  
RNASeqPowerCalculator http://www2.hawaii.edu/~lgarmire/RNASeqPowerCalculator.htm  
RnaSeqSampleSize http://www.bioconductor.org/packages/release/bioc/html/RnaSeqSampleSize.html  
ssizeRNA https://cran.r-project.org/web/packages/ssizeRNA/index.html  
SSPA http://www.bioconductor.org/packages/release/bioc/html/SSPA.html  
   
For the estimation with Scotty the MATLAB code https://github.com/mbusby/Scotty, with the following command was used.  
scottyEstimate('PATH to your working direction\pilotdata\Skin_1000DE\FC_2\for_Scotty\pilot31.csv',...
    '3','3','75','2.5','0.05','80','2.541','2.541','8.874',...
    '1000000','20','50000000','100000000','50','50','50',...
    'PATH to your working direction\resluts\Skin_1000DE\FC_2\Scotty\31\');
    
## Contact

alpoplaw@uni-mainz.de
