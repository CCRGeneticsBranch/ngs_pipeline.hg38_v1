NGS pipeline can be launched using a yaml input file containing metadata information like Diagnosis, capture kit used, sample references and  Sample type. The output of the ngs pipeline is uploaded to the Oncogenomics database. Master file must contain the following columns. The order of the columns doesnot matter.


| **Patient ID** | **Type** | **Library ID** | **FCID** | **Diagnosis** | **Enrichment step** | **SampleRef** | **Matched normal** | **Matched RNA-seq lib** | **Case Name** | 
| -- | -- | -- | -- | -- | -- | -- | -- | -- | -- |
Samplename | tumor RNA | Samplename_T1R_T | AAAAAAAA5 | Medulloblastoma | access | hg38 |  |   | Test |
Samplename | tumor DNA | Samplename_T1D_E | HMHAAAAA3 | Medulloblastoma | access | hg38 |Samplename_N1D_E |Samplename_T1R_T | Test |
Samplename | blood DNA | Samplename_N1D_E | HMHYYYYY3 | Medulloblastoma | access | hg38 |  |   | Test |

| **Master file columns** | **Values** |
|-------------|--------------|
| Patient ID | Unique name of the Patient |
| Type | Format: "[tumor/normal/cell line/blood/xeno] [RNA/DNA]"; must be "blood DNA" or "normal DNA" to be recognized as "Normal", "tumor DNA" as "Tumor", or "tumor RNA" as "RNAseq" |
| Library ID | Sequencing library, in file name  |
|  FCID  | Sequencing flow cell ID  |
| Diagnosis | Cancer type |
| Enrichment step | Capture kit used. All currently supported kits are listed [here](https://github.com/CCRGeneticsBranch/ngs_pipeline.hg38_v1/blob/main/config/config_common_biowulf.json) under "target_intervals" |
| Sampleref | Accepted entries are hg19/hg38 |
| Matched normal | Library ID of normal DNA from same patient. Must be listed for tumor DNA only. |
| Matched RNA-seq lib | Library ID of tumor RNA from same patient. Must be listed for tumor DNA only|
| Case Name | Combine related samples that are jointly run with the pipeline, such as tumor/normal DNA + tumor RNA must be same as Case folder, should be meaningful (not date).  Normal DNA can be assigned to multiple cases using comma-separated list  |

When the pipeline runs, it will create a folder structure: Patient ID > Case Name > Library ID 

Use createyaml.py to create the yaml input file from the master file . Provide Patient ID, Case Name, and data location as arguments. 

```
python3 createyaml.py Samplename Test_Case </path to the master file>
```

For a Patient sample containing RNAseq, Exome Tumor-normal pair, the pipeline runtime is ~22hrs.

------Add a table contianing no. of raw reads vs completion times. -------
