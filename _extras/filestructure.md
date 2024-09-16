---
layout: page
title: Folder Structure and Layout
permalink: /filestructure/index.html
---

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
