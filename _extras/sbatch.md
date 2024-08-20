---
layout: page
title: Submitting jobs using sbatch
permalink: /sbatch/index.html
---

## Overview

We have to get appropriate resources allocated for our jobs. Each job needs its OWN script with different resources. These scripts are a great way to keep track of what resources you needed for the program and also what parameters your program required. 

## sbatch script

To submit a job, you have to make a script `my_slurm_script.sh` with follow headers. (Change the parameters)

### A template sbatch script

```bash

#!/bin/bash
#SBATCH --tasks=1
#SBATCH --cpus-per-task=<threads>
#SBATCH --partition=<partitions,listed,here>
#SBATCH --mem=<>
#SBATCH --time=<hh:mm:ss>
#SBATCH --job-name=<job_name_id>
#SBATCH --output=<outdir>/<tool>.slurm.out.%j
#SBATCH --error=<outdir>/<tool>.slurm.err.%j

# activate the conda environment

source /path/to/miniconda3/etc/profile.d/conda.sh && conda activate <tool_env>

echo date

my commands here

```

### Resources

These options tell slurm:
- how many tasks (a slurm term) you want to run
- how many threads you want per task (commonly called "threads" parameters for bioinformatic programs - this has to match)
- how much memory you want allocated. The maximum memory allowed here is 250GB - but this is a lot and none of the programs we use require this much for our application.
- how long we expect our job to run - an educated guess. 

```bash
#SBATCH --tasks=1
#SBATCH --cpus-per-task=<threads>
#SBATCH --mem=<>
#SBATCH --time=<hh:mm:ss>
```

### Other options

These tell slurm:
- your job name
- which partitions you want to run the task on. We will primarily be using the "short" and "standard" partitions
- standard output from the program
- standard error from the program - usually has more helpful info if they program crashes

```bash
#SBATCH --job-name=<job_name_id>
#SBATCH --partition=<partitions,listed,here>
#SBATCH --output=<outdir>/<tool>.slurm.out.%j
#SBATCH --error=<outdir>/<tool>.slurm.err.%j

```


### Example sbatch script

```
#!/bin/bash
#SBATCH --tasks=1
#SBATCH --cpus-per-task=10
#SBATCH --partition=short,standard
#SBATCH --mem=1G
#SBATCH --time=2:00:00
#SBATCH --job-name=sequencing_QC
#SBATCH --output=10_nanoplot/nanoplot.slurm.out.%j
#SBATCH --error=10_nanoplot/nanoplot.slurm.err.%j

# First, we check the quality of the reads using nanoplot
# activate the conda environment containing nanoplot

source /vast/groups/VEO/tools/anaconda3/etc/profile.d/conda.sh && conda activate nanoplot_v1.41.3
```


## Submitting the script

```bash
sbatch my_slurm_script
```

## Other useful slurm commands

```bash
# submit a job
sbatch

# check on your jobs
squeue -u <fsuid>

squeue --me
# how many resources are being consumed
sstat <job id>

# kill a job
scancel <job id>

# information about nodes
sinfo --long

scontrol show node
```
