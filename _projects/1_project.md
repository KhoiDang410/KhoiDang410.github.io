---
layout: page
title: Targeted-panel variant calling pipeline
description: Production Nextflow pipeline — germline, somatic & structural variants
img: assets/img/12.jpg
importance: 1
category: pipelines
related_publications: false
---

A production-grade, ultra-deep **targeted gene-panel** variant-calling pipeline —
the most engineering-mature project in my portfolio. Built in **Nextflow DSL2**,
it runs cohort-scale on **SLURM** with full **Apptainer** containerization and
covers the complete germline + somatic + **structural-variant** workflow across
10 stages:

QC → BWA-MEM2 mapping → GATK4 BQSR → HaplotypeCaller / FreeBayes (germline) →
**Mutect2** (somatic) → SV calling → **VEP / AnnotSV** annotation → variant QC &
reporting.

83 modules, backed by **61 `nf-test` unit tests and snapshots** — scientific
software treated as software, with version pinning and seeded, reproducible runs.
