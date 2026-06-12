---
layout: page
title: Somatic variant calling for a drug-response study
description: Tumor–normal somatic calling with Mutect2 & DeepSomatic
img: assets/img/7.jpg
importance: 6
category: analyses
related_publications: false
---

Somatic variant calling on paired **tumor–normal** cell lines from a
drug-treatment study. Nextflow on SLURM: fastqc/multiqc → trim_galore →
BWA-MEM2 → GATK4 (MarkDuplicates, BQSR) → **Mutect2** (with read-orientation and
contamination models) and **DeepSomatic** → **VEP** annotation, with downstream
R analysis of the resulting variant calls.
