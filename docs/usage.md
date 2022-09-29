## Running the pipeline

The ngs pipeline can be run using a wrapper bash script and the input yaml file. This wrapper calls the launch script. Wrapper script can be set up as below.


```
#!/bin/sh
samplesheet=$1
a=`echo $samplesheet |sed -e 's/_/\t/' |sed -e 's/.json//g' |cut -f2`
/data/Clinomics/Tools/ngs_pipeline.hg38_v1/launch -d /path/to/data/directory/ -w /path/to/output/directory/ -s /path/to/yaml/${samplesheet} -m $a $2
```



Arguments
```
launch -datadir <path to data directory> -workdir <Path to the results directory> -s <yaml file path >
     Arguments: 

            -h, -help, --help Print this message.


            -d, -datadir    On biowulf the raw data is stored in /data/khanlab/projects/DATA/
                              On TGen the raw data is stored in /projects/Clinomics/DATA/
                              If your data is coming from somewhere else specify using this variable
                              -datadir "/data/Clinomics/testData/"

            -w, -workdir    Working directory where all the results will be stored. there are defaults to be used specific to host.
            -s, -sheet      A yaml file can be  downloded from  https://fr-s-bsg-onc-d.ncifcrf.gov/onco.sandbox1/public/viewPatients/null/all/1 
                            or can be create using the createyaml.py script. This dictates how the pipeline will run

```

Always do a dry run of the sample before launching the pipeline. This way we can ensure that all the steps are listed accurately and fix any irregularities.

```
./run.sh Samplename_TestCase.yaml --dryrun

```
Once the dry run looks good, the sample can be launched as below. The jobs will be submitted via sbatch to the slurm process.

```
./run.sh Samplename_TestCase.yaml 

```
