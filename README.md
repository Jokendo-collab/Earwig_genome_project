# Zebrafish genome assembly project

This repository contains all the scripts used to assemble and annotate the zebrafish genome.
The pipeline is presented in three parts:

1. Genome assembly
2. Denovo repeat library
3. Genome annotation
---
## 1. Genome assembly

Genome is assembled using linked reads from 10x chromium and long reads from Oxford nanopore.
Long and linked reads were individually assembled and then merged together. After multiple iterations of scaffolding, gapclosing, and haplotigs and contaminants removal, assembly was polished with mRNA-seq reads to obtain final assembly. Schematic representation in figure below (Created with BioRender.com).

![Alt text](Genome_assembly/Assembly_pipeline.png?raw=true "Title")

Workflow and Scripts:
1. [Linked read assembly](Genome_assembly/Linked_reads_only_assembly.md)
2. [Long read assembly](Genome_assembly/Long_read_assembly.md)
3. [Merging two assemblies](Genome_assembly/merging_assemblies.md)
4. [Further processing with long reads](Genome_assembly/Processing_with_long_reads.md)
5. [Further processing with linked reads](Genome_assembly/Processing_with_linked_reads.md)
6. [Processing with RNA-seq reads](Genome_assembly/Processing_with_RNA-seq_reads.md)
7. [Final bits: Haplotigs removal, cleaning and polishing](Genome_assembly/Final_bits.md)
---
## 2. Denovo repeat library
A comprehensive denovo repeat library is prepared for the assembled genome. It was used for repeat content analysis, repeat masking and as input for annotation pipeline.

Workflow:
1. Repeat library preparation
      1. [Repeatmoduler](Denovo_repeat_library/Repeatmoduler.md)
      2. [LTRharvest & LTRdigest](Denovo_repeat_library/LTRharvest&LTRdigest.md)
      3. [TransposonPSI](Denovo_repeat_library/TransposonPSI.md)
      4. [Sine database](Denovo_repeat_library/SINE.md)
2. Concatenating, filtering, and classifying repeats
      1. [RepeatClassifier](Denovo_repeat_library/RepeatClassifier.md)
3. Repeat masking the genome
      1. [RepeatMasker](Denovo_repeat_library/RepeatMasking.md)

---

## 3. Genome annotation
Maker2 pipeline is used for genome annotation. mRNA-seq data is denovo assembled using Trinity. Other relavant publicly available datasets were downloaded and used as input.

1. [Processing mRNA-seq data](Genome_annotation/Processing_mRNA_seq_data.md)
2. [GeneMark-ES](Genome_annotation/GeneMark.md)
3. [Braker](Genome_annotation/Braker.md)
4. [Configuring and running Maker2 pipeline](Genome_annotation/maker_pipeline.md)
