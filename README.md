# RNAseq Analysis of Arabidopsis thaliana Upon Enhancement of Dehydration Resistance by Interaction with Flavonoid-Attracted Aeromonas sp. from Root Microbiome

## Introduction

### Background
In view of the current alarming climatic problems, the aim is to find plants that can withstand abiotic stress conditions. Flavonoids (a secondary metabolite synthesized by the plant when under stress) can be of great help in determining the plant-microbiome relationship, and to see how this improves resistance to water stress. This relationship is well studied in nodulating bacterial species, but not so much in non-nodulating bacteria such as those of the Aeromonadaceae family. Therefore, the motivation of the study is to check the behavior of Arabidopsis thaliana plants in the presence/absence of Aeromonas sp.

### Objective
To test differential expression in Arabidopsis thaliana, in the presence/absence of Aeromonas sp. and drought conditions.

## Materials and Methods

### Experimental Design
For our experimental design, we have used as a reference the accession number GSE184872 of the GEO (Gene Expression Omnibus) website.

We have a series of points that describe the conditions of our study, according to the treatment we have applied to Arabidopsis thaliana, the plant that is the model organism of this study.

#### Untreated (Controls)
- GSM5599109 At_mock_1
- GSM5599110 At_mock_2
- GSM5599111 At_mock_3

#### Drought Treatment
- GSM5599112 At_Drought_1
- GSM5599113 At_Drought_2
- GSM5599114 At_Drought_3

#### Aeromonas Treatment
- GSM5599115 At_H1_1
- GSM5599116 At_H1_2
- GSM5599117 At_H1_3

#### Drought and Aeromonas Treatments
- GSM5599118 At_H1_Drought_1
- GSM5599119 At_H1_Drought_2
- GSM5599120 At_H1_Drought_3

### Workflow
The following is the series of steps followed to perform the mathematical/computational analysis of the RNA-seq data:

1. **Data Preparation**: Download data via sbatch from the reference article, converting SRA files to FASTQ using fastq-dump, and performing quality analysis using FastQC.
2. **Mapping and Assembly**: Use hisat2 to map the short sequence reads against the reference genome, converting .sam files to .bam using samtools. Assemble transcripts using stringtie and merge them to compile the complete transcriptome.
3. **Quantification**: Quantify gene expression levels using ballgown in R, normalizing data and comparing the quality data of different samples.
4. **Data Normalization**: Apply a normalization algorithm to correct bias and facilitate comparison of results between different samples.
5. **Correlation and PCA**: Perform Pearson correlation, principal component analysis (PCA), and hierarchical clustering to check data variability and replicate consistency.
6. **Differential Expression Analysis**: Identify differentially expressed genes (DEGs) using scatterplots, volcano plots, and functional enrichment analysis to highlight the most represented biological processes.

## Results

### Quality Analysis
The quality analysis of all samples showed high quality, with boxplots remaining in the green-colored area. Normalization was necessary to compare the quality data of different samples accurately.

### Analysis of Global Distribution of Gene Expression
Gene expression analysis by TPM confirmed that the results were consistent with those obtained by FPKM. Normalization was performed to correct biases and facilitate comparison, with VSN being identified as the best standardization technique initially, but Quantile normalization was ultimately chosen based on Pearson's correlation.

### Scatterplots and Principal Component Analysis
Scatterplots indicated high correlation between replicates (around 99%). PCA and hierarchical clustering revealed some variability, with certain replicates (ctl_drought2, h1_water3, ctl_water1) showing deviations from their condition groups.

### Differential Gene Expression Analysis
Five comparisons were made to identify DEGs under different conditions:

1. **Ctl_drought vs Ctl_water**: 112 activated and 36 repressed genes.
2. **H1_drought vs H1_water**: 282 activated and 45 repressed genes.
3. **H1_drought vs Ctl_drought**: 84 activated and 28 repressed genes.
4. **H1_water vs Ctl_water**: No differentially expressed genes.
5. **H1_drought vs Ctl_water**: 556 activated and 150 repressed genes.

### GO Term Enrichment Analysis
Gene ontology term enrichment was performed for differentially activated and repressed genes, revealing significant processes and pathways involved in drought resistance and the role of Aeromonas sp.

## Conclusions
The analysis demonstrated that Arabidopsis thaliana produces a stronger response to drought stress when treated with Aeromonas sp. GO term enrichment highlighted the importance of the jasmonic acid-mediated signaling pathway and specific genes like JAZ7, ERF2, and NAC3 in enhancing drought resistance. The study also confirmed that treatment with Aeromonas sp. does not have a detrimental effect under basal conditions.

A simple experiment was suggested to further explain the effects of Aeromonas sp. on Arabidopsis thaliana under dehydration conditions.

## References
He, D., Singh, S. K., Peng, L., Kaushal, R., Vílchez, J. I., Shao, C., ... & Zhang, H. (2022). Flavonoid-attracted Aeromonas sp. from the Arabidopsis root microbiome enhances plant dehydration resistance. The ISME Journal, 16(11), 2622-2632.
