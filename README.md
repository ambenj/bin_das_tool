## Pipeline for binning and aggregation using DAStool

This is a binning pipeline that takes metagenome assembly (fasta) and reads (fastq). It runs three binning programs (Maxbin2, Metabat2, and myCC) and then uses DAStool to aggregrate the three bin sets into a final consensus bin set.

It is not necessary to install any software, except for snakemake.



The pipeline can be run with the following command:
snakemake --snakefile ~/path/to/snakefile --configfile path/to/config --use-singularity --singularity-args '--bind /labs/ --bind /scratch/ --bind /home/' --profile scg --jobs 999


Note that if any of the individual binning programs fail to produce a bins above the minimum quality threshold for DAStool, there will be an error at the DAStool step of the pipeline.
