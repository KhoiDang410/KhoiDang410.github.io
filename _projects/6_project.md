---
layout: page
title: Somatic variant calling for a drug-response study
description: Tumor–normal somatic calling with Mutect2 & DeepSomatic
img: assets/img/7.jpg
importance: 6
category: analyses
related_publications: false
---

**Why it matters.** Profiling a tumor's somatic mutations before and after drug
treatment exposes drug-induced mutational signatures and candidate
resistance mechanisms — the genetic changes that let cancer cells survive therapy.
That directly informs combination-treatment strategies.

**Approach & tools.** A paired **tumor–normal** somatic pipeline in **Nextflow** on
**SLURM**:

- FastQC / MultiQC → Trim Galore → BWA-MEM2
- **GATK4** MarkDuplicates and BQSR
- somatic calling with GATK4 **Mutect2** (read-orientation & contamination models)
  and **DeepSomatic** (deep-learning caller) for orthogonal confidence
- **VEP** functional annotation, with downstream variant analysis in R
