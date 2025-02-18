---
layout: page
title: Ideas for Projects
permalink: /ideas_projects/index.html
---


## Project ideas involving functional annotation

### [running phold](https://phold.readthedocs.io/en/latest/run/)

### phold - for functional annotation using protein structures

>```bash
> #!/bin/bash
> #SBATCH --job-name phold
> #SBATCH --partition=gpu
> #SBATCH --cpus-per-task=32
> #SBATCH --output phold_%j_1.out
> #SBATCH --gres=gpu:1
> #SBATCH --mail-type=ALL
>
> ## load gpu module
> module load nvidia/cuda/12.1.0
>
> # conda environment
> source /vast/groups/VEO/tools/miniconda3_2024/etc/profile.d/conda.sh
>
> conda activate pholdENV_v0.2.0_gpu
>
> phold predict -i pharokka.gbk -o phold_predict_output
> phold compare -i pharokka.gbk -o phold_compare_output  --predictions_dir phold_predict_output -t 32
>
```

database for phold: -d /veodata/01/databases/phold/v240724/

### Comparing functional annotation between pharokka and genomad

- You could compare functional annotations between pharokka and geNomad

## Other ideas for detailed analyses projects

- Find potential prophages in the virome or metagenome dataset
- Run the full geNomad pipeline `end-to-end` command and check out the outputs. Running the complete pipeline for a 35 kbp viral genome takes 3-4 min
- When you used Jaeger to identify contigs, you saw that some were identified as viral while others not. You could dig deeper into the why. Do these two sets (viral vs. non-viral contigs) differ? For instance, are there any statistical differences in contig length, completeness and contamination? You could run a statistical test and visualize the distributions.
- Reassemble with all 7 samples, instead of 3 and make correlations with the salinity

## Ideas for research proposal projects

Check the papers we mention in the [main link of project design](https://mgxlab.github.io/Viromics2024/2.3.1_research_question/index.html).
