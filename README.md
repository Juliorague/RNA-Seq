RNA-seq Analysis of Arabidopsis thaliana Upon Enhancement of Dehydration Resistance by Interaction with Flavonoid-Attracted Aeromonas sp. from Root Microbiome


Introduction

Background

In light of current alarming climatic challenges, the aim is to identify plants that can withstand abiotic stress conditions. Flavonoids, a secondary metabolite synthesized by plants under stress, play a crucial role in plant-microbiome relationships, potentially enhancing resistance to water stress. This relationship is well-studied in nodulating bacterial species, but less so in non-nodulating bacteria such as those in the Aeromonadaceae family. This study aims to investigate the behavior of Arabidopsis thaliana in the presence and absence of Aeromonas sp. under drought conditions.

Objective

To test differential gene expression in Arabidopsis thaliana in the presence and absence of Aeromonas sp. under drought conditions.


Materials and Methods

Experimental Design

This study is based on the reference accession number GSE184872 from the GEO (Gene Expression Omnibus) database. Arabidopsis thaliana plants were subjected to the following conditions:

Controls: GSM5599109, GSM5599110, GSM5599111

Drought Treatment: GSM5599112, GSM5599113, GSM5599114

Aeromonas Treatment: GSM5599115, GSM5599116, GSM5599117

Drought and Aeromonas Treatments: GSM5599118, GSM5599119, GSM5599120


Workflow

Data Preparation: Download data from GEO, convert SRA files to FASTQ, and perform quality analysis using FastQC.

Alignment and Assembly: Use HISAT2 for alignment and StringTie for transcript assembly.

Expression Quantification: Quantify gene expression using StringTie.

Data Analysis:

Normalize data and perform quality checks in R.

Analyze global gene expression distribution.

Conduct differential gene expression analysis using limma and DESeq2.

Perform GO term and KEGG pathway enrichment analysis.


Results

Quality Analysis

High-quality sequencing data were confirmed by FastQC, with normalization ensuring comparability between samples.

Global Gene Expression

Gene expression levels were measured in TPM, normalized, and visualized using boxplots and scatterplots to assess replicates' consistency.

Differential Gene Expression

Significant differential expression was identified between various conditions, highlighting genes involved in drought response and those influenced by Aeromonas sp. inoculation.

Enrichment Analysis

GO term and KEGG pathway enrichment analyses revealed key biological processes and pathways, notably the jasmonic acid-mediated signaling pathway, which is critical for drought resistance.

Conclusions

Arabidopsis thaliana exhibits enhanced drought resistance when inoculated with Aeromonas sp., primarily through the activation of specific genes and pathways related to stress response. The synergistic effect of Aeromonas sp. and drought stress highlights potential strategies for improving plant resilience to abiotic stress.


How to Use This Repository

Prerequisites:

R and RStudio

Required R packages: ballgown, NormalyzerDE, FactoMineR, limma, ggvenn, factoextra, clusterProfiler, org.At.tair.db, enrichplot and pathview

HISAT2, StringTie, FastQC, samtools


License

This project is licensed under the ... License - see the LICENSE file for details.
