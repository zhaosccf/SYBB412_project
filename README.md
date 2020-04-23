SYBB412 Class Project

RNAseq workflow – gene differential expression and gene set enrichment analysis

Introduction

This project retrieved data from the study “Whole transcriptome analysis identifies differentially regulated networks between osteosarcoma and normal bone samples” published on the journal of Experimental Biology and Medicine in 2017. This report summarizes the process of downloading the original data from Gene Expression Omnibus, quality control of the FASTQ files, mapping reads to the reference genome, counting how many reads mapped to each gene, and using R packages for gene differential expression and pathway analysis. There is also a discussion about the biological meaning of the results and biomedical relevance of the study at the end.

Experimental Data

The data GSE99671 used in this workflow can be accessed at GEO at NCBI (https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE99671). The researchers sequenced 36 samples (18 tumoral bone samples and 18 non-tumoral paired samples) matching in pairs for each osteosarcoma patient. Tumor and normal bone samples were collected from the removed bone right after the operation and stored at -80 until RNA extraction. 15 formalin-fixed paraffin-embedded (FFPE) samples were sequenced as well. FFPE samples were all biopsy samples. 10 of them before and 5 after chemotherapy. 

Goal of the workflow

My goal is to be familiar with the whole process from downloading the original data from NCBI to visualizing the final results using R and R packages. At the end, we visualize and analyze the relationship between normal and tumor samples and perform statistical tests to find which genes are changing their expression and which gene sets are enriched in comparison between tumor and normal samples.  

Below is an overview of the steps I take: 
	
	1.	Download the original data and data quality control
		•	Download SRA files from GEO and convert them into FASTQ files
		•	Perform quality control on FASTQ files using FastQC and Trim-galore
	2.	Process FASTQ files
		•	Align reads to the reference genome with HISAT2 or STAR
	3.	Generate a gene-level count matrix
		•	Count number of reads (single-end) or fragments (paired-end) mapping to each gene
	4.	Convert the count matrix into a package-specific object, e.g. a DESeqDataSet for DESeq2 
	5.	Make exploratory plots, such as PCA plots, MA plots, Volcano plots, etc
	6.	Perform differential expression testing for all genes and make summary plots and tables of the differential expression results.
	7.	Perform Gene Ontology analysis and GSEA analysis using R package – clusterProfiler.

The first three steps were performed on the Cleveland Clinic High-performance computer clusters (HPC) and the last four steps were 		completed using RStudio 3.6.2 and necessary Bioconductor packages.
