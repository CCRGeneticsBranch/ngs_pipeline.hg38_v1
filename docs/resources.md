1. Reference genomes
Hg38 references used in this pipeline are downloaded from [gencode](https://www.gencodegenes.org/). All the genome indexes are build using these fasta and gtf files.




| **files**      | **Species**   | **Annotation Version**    | **Notes**                                               |
| ------------   |-------------- | --------------------------| --------------------------------------------------------|
| Genome fasta   | Homo sapiens  | [Gencode release v39](https://ftp.ebi.ac.uk/pub/databases/gencode/Gencode_human/release_39/GRCh38.primary_assembly.genome.fa.gz) | 92 sequences of [ERCC spike](https://assets.thermofisher.com/TFS-Assets/LSG/manuals/ERCC92.zip) in are added to the fasta file |
| Annotation GTF |  Homo sapiens | [Gencode release v39](https://ftp.ebi.ac.uk/pub/databases/gencode/Gencode_human/release_39/gencode.v39.primary_assembly.annotation.gtf.gz) | 2 sequences of [ERCC spike](https://assets.thermofisher.com/TFS-Assets/LSG/manuals/ERCC92.zip) in are appended to the gtf file |



2. Tools and versions


| **Tool**               | **Version** |
|----------------------- |:-----------:|
| snakemake              |  5.24.1   |
| Graphviz               | v 2.40.1  |
| annovar                | 4/16/18   |
| arriba                 | 2.0.0     |
| bamutil                | 1.0.13    |
| bedtools               | 2.22.0    |
| bowtie                 | 1.1.1     |
| bwa                    | 0.7.10    |
| cnvkit                 | 0.9.3     |
| conpair                | 10102016  |
| fastqc                 | 0.11.2    |
| fusioncatcher          | 1         |
| GATK                   | 3.4-0     |
| mixcr                  | 2.1.12    |
| GATK                   | 3.8-1     |
| GATK                   | 4.1.8.0   |
| igvtools               | 2.3.31    |
| java                   | 1.8.0_11 |
| manta                  | 1.6.0     |
| STAR                   | 2.7.6a    |
| muTect                 | 1.1.7     |
| picard                 | 1.129     |
| python                 | 2.7       |
| python                 | 3.7       |
| R                      | 3.4       |
| R                      | 4.0.5     |
| rnaseqc                | 1.1.8     |
| rsem                   | 1.3.0     |
| bcftools               |  1.13     |
| samtools               | 0.1.19    |
| VEP                    | 86        |
| samtools               | 1.9       |
| sequenza-utils         | 3.0.0     |
| SIFT                   | 5.2.2     |
| singularity            |           |
| snpEff                 | 4.1c      |
| STAR                   | 2.7.8a    |
| STAR-Fusion            | 1.3.1     |
| strelka                | 2.9.10    |
| vcftools               | 0.1.13    |
| vdjtools               | 1.1.10    |
| verifybamid            | 1.1.3     |


