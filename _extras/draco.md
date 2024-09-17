---
layout: page
title: Access to Draco
permalink: /draco/index.html
---

[Draco](https://wiki.uni-jena.de/pages/viewpage.action?pageId=22453002) is a high-performance cluster created and maintained by the Universitätsrechenzentrum. It is [available for members of Thuringian Universities](http://sternb.gitpages.tpi.uni-jena.de/draco-101-2023-01/#5).  

## SLURM ARCHITECTURE

This is a simplified overview of the slurm architecture. 

![slurm_architecture_simple](https://github.com/user-attachments/assets/f6baeec5-ddf0-413d-909c-aa2d2b947bd5)


To log in, you can use [ssh](http://sternb.gitpages.tpi.uni-jena.de/draco-101-2023-01/#15): 

```bash
# replace <fsuid> with your actual id like ab12cde

ssh <fsuid>@login1.draco.uni-jena.de
```

## Getting into Draco

### Terminal or ssh client  
You will require a terminal or an ssh client to access Draco, which is a remote server. 

#### Linux and MacOS
Lucky! You already have a terminal integrated into the OS. You can use this or can also use VSCode (see below).

#### Windows
Please switch to either a Linux or MacOS...

Just joking! You can either install the Windows Subystem for Linux (WSL) or **VScode (recommended)**

[Instructions for WSL](https://learn.microsoft.com/en-us/windows/wsl/install)

[Instructions for installing Visual Studio Code](https://code.visualstudio.com/docs/setup/windows)

#### Adding a ssh remote server to VSCode

![image](https://github.com/user-attachments/assets/3db3b016-b33f-469f-ac3f-df490d1f34b8)

![image](https://github.com/user-attachments/assets/d8e9d52b-6695-4608-a33f-9e4a28d11a04)

![image](https://github.com/user-attachments/assets/8e19f0da-2cbd-4119-bc83-8c63d928d544)


Then put in your password and you are in!

## File structure

As a best practice in bioinformatics, please number your directories on Draco and add meaningful headers. This makes it easy to trace where your data and outputs are later. An example of this directory numbering looks like below:

```bash
.
├── 1.1_QC
│   ├── 10_nanoplot
│   │   ├── 20_nanoplot_summary_file
│   │   ├── barcode62
│   │   ├── barcode63
│   │   └── barcode64
│   └── 20_chopper
├── 1.2_assembly
│   ├── 10_results_assembly_flye
│   │   ├── cross_assembly
│   │   └── single_assemblies
│   ├── 20_results_assessment_vclust
│   │   ├── cross_assembly
│   │   └── single_assemblies
│   ├── 30_results_assessment_quast
│   │   ├── cross_assembly
│   │   └── single_assemblies
│   └── 40_results_alignment_minimap2
├── 1.3_virus_identification
│   ├── 10_jaeger
│   │   └── results_jaeger
│   ├── 20_results_assessment_checkv
│   │   ├── cross_assembly
│   │   └── single_assemblies
│   └── 40_results_filter_contigs
├── 1.4_annotation
│   ├── 10_pharokka
│   │   ├── 11_selected_contig
│   │   └── logs
│   └── 20_plot_viral_genome
├── 2.2_taxonomy
│   ├── 10_vcontact_results
│   └── 20_genomad_results
│       └── assembly_annotate
├── data
│   ├── alignments
│   │   ├── cross_assembly
│   │   └── single_assemblies
│   └── sequences
├── py3env
│   ├── bin
│   ├── include
│   ├── lib
│   │   └── python3.9
│   ├── lib64
│   └── share
│       └── man
└── python_scripts
    ├── annotation
    ├── assembly
    ├── host_prediction
    ├── identify
    └── qc
```
