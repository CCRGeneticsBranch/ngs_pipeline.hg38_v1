## Introduction
This is the implimentation of KhanLab NGS Pipeline using Snakemake.
## Installation

The easiest way to get this pipeline is to clone the repository.

```
git clone https://github.com/patidarr/ngs_pipeline.git
```
## Conventions

- Sample names cannot have "/" or "." in them
- Fastq files end in ".fastq.gz"
- Fastq files are stored in DATA_DIR (Set as Environment Variable) 

### DNASeq:
- QC
- BWA, Novoalign
- Haplotype Caller, Platupys, Bam2MPG, MuTect, Strelka
- snpEff, Annover, SIFT, pph2, Custom Annotation
- Coverage Plot, Circos Plot, Hotspot Coverage Box Plot

### RNASeq:
- QC
- Tophat, STAR
- fusion-catcher, tophat-fusion, deFuse
- Cufflinks (ENS and UCSC)
- Haplotype Caller
- snpEff, Annover, SIFT, pph2, Custom Annotation


Rulegraph


![alt tag](rulegraph.png)





DAG for example Sample
![alt tag](dag.png)