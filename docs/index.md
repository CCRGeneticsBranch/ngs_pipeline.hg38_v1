## 1. Introduction

This guide serves as the main source of documentation for the [ngs_pipeline.hg38_v1](https://github.com/CCRGeneticsBranch/ngs_pipeline.hg38_v1). This is a comprehensive Snakemake workflow that can process RNAseq, Exome ( tumor only and Tumor-normal pairs) & TCRseq 
data. It involves a series of data processing, quality control steps followed by variant analysis, fusion calling, and annotation. All the tools used in this pipeline are listed [here](/Applications/Projects/ngs_pipeline.hg38_v1/docs/resources.md). 
containers. The Pipeline is currently hosted on NIH biowulf cluster and provides support hg38 genome. The pipeline is containerized via singularity and can be run on cloud platforms. This pipeline submits jobs to a cluster using a job schedules like slurm. This documentation provides a step to step walkthrough to understand and launch the pipeline. The output from this pipeline can be visualized using the [oncogenomics_website](https://oncogenomics.ccr.cancer.gov/production/public/login).


## 2. Pipeline

We follow tool suggested best practices for all the data processing. The pipeline can be launched using a yaml/json file. Metadata information like sample libraries, capture kit used, diagnosis, tumor-normal pairing are needed to create the yaml file. Detailed process can be found  [here]. The pipeline can be run in RNAseq, tumor only and tumor-normal modes. // insert pipeline overview image //


### 2.1 Quality Control

[**FastQC**](https://www.bioinformatics.babraham.ac.uk/projects/fastqc/) is a program designed to spot potential problems in high througput sequencing datasets. It provides an overview of basic quality control metrics for raw next generation sequencing data. The output is a html file summarizing several read statistics like Per base seqeunce quality, Per base GC content, Per seqeunce GC content, sequence length distribution, duplicated sequences and over represented sequences.

**Picard** provides a high level metrics about the alignment of reads within a SAM/BAM file. This tool takes a SAM/BAM file input and produces metrics detailing the quality of the read alignments as well as the proportion of the reads that passed machine signal-to-noise threshold quality filters.

[**RNAseQC**](https://software.broadinstitute.org/cancer/cga/rnaseqc_run) The RNA-SeQC package has functions for computing various quality metrics, such as alignment quality, duplication rates, GC bias, rRNA content, coverage continuity, covered alignment regions, transcript count, and 3'/5' bias. It produces Read counts, coverage, correlation quality control metrics, and is also suitable for use with scRNA-seq data sets.

**Flagstat** does a full pass through the input file to calculate and print statistics to stdout and Provides  counts for each of 13 categories based primarily on bit flags in the FLAG field. Each  category  in  the  output  is  broken down into QC pass and QC fail.  In the default output format, these are presented as "#PASS + #FAIL" followed by  a  description  of  the category.

**Circos Plots**


**Genotyping**

**Coverage Plots**


### 2.2 Data Processing

This comprehensive pipeline is capable of processing different sample libraries together and seperately. This scalable ngs workflows involve RNA-seq sample processing,Tumor-Normal processing, and Tumor only processing. 


7. In Development
8. References
