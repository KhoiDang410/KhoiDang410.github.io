---
layout: page
title: Bioinformatics container library & build system
description: 68 version-locked container images + a YAML→Docker build system
img: assets/img/3.jpg
importance: 2
category: pipelines
related_publications: false
---

**Why it matters.** Reproducibility is foundational to trustworthy science:
results must be regenerable exactly, with every tool version fixed — a prerequisite
for peer review and for any eventual clinical translation. Drifting dependencies are
a leading cause of irreproducible bioinformatics.

**Approach & tools.** A reproducibility backbone of **68 Dockerfiles** building
version-locked container images of the entire toolchain, plus conda/mamba
environment definitions:

- **Alignment/quant:** BWA / BWA-MEM2, STAR, Salmon, StringTie, Subread
- **Variant calling:** GATK4, DeepVariant, DeepSomatic, FreeBayes, Manta, Strelka,
  GRIDSS, Delly, CNVkit, SpliceAI
- **Epigenomics/QC:** MACS3, SEACR, LanceOtron, deepTools, Picard, mosdepth,
  Qualimap, RSeQC, FastQC, MultiQC, fastp, UMI-tools
- **Assembly/metagenomics:** Trinity, SPAdes, MEGAHIT, Kraken2
- **Annotation:** VEP, AnnotSV

Paired with a build system that turns a **single YAML** of tools/versions into
lightweight Docker images for Nextflow — multi-stage builds, parallel **Mamba**
environment creation, Docker Hub push, and skip-if-exists / force-rebuild logic.
