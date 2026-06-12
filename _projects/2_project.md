---
layout: page
title: Bioinformatics container library & build system
description: 68 version-locked container images + a YAML→Docker build system
img: assets/img/3.jpg
importance: 2
category: pipelines
related_publications: false
---

My reproducibility backbone. **68 Dockerfiles** build version-locked container
images of the entire bioinformatics toolchain — GATK4, BWA-MEM2, STAR, Salmon,
StringTie, MACS3, deepTools, VEP, AnnotSV, DeepVariant/DeepSomatic, Manta,
Strelka, GRIDSS, Delly, CNVkit, FreeBayes, SpliceAI, Trinity, SPAdes, Kraken2,
fastp, MultiQC, Picard, and many more — alongside conda/mamba environment
definitions.

Paired with a build system that turns a **single YAML** of tools and versions
into lightweight Docker images for Nextflow: multi-stage builds, parallel Mamba
environment creation, Docker Hub push, and smart skip-if-exists / force-rebuild
logic.
