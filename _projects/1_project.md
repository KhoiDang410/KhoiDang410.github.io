---
layout: page
title: Targeted-panel variant calling pipeline
description: Production Nextflow pipeline — germline, somatic & structural variants
img: assets/img/12.jpg
importance: 1
category: pipelines
related_publications: false
---

**Why it matters.** Targeted gene-panel sequencing enables ultra-deep detection
of clinically relevant variation that broader assays miss — germline predisposition
alleles, low-frequency somatic driver mutations, and structural rearrangements.
Resolving all three variant classes together is essential for molecular diagnosis
and therapy selection in cancer, where a structural variant or CNV may explain a
phenotype that single-nucleotide variants alone cannot.

**Approach & tools.** A production-grade **Nextflow DSL2** pipeline running
cohort-scale on **SLURM** with full **Apptainer** containerization:

- **QC:** FastQC, MultiQC, fastp / Trim Galore
- **Alignment & preprocessing:** BWA-MEM2, **GATK4** (MarkDuplicates, BQSR)
- **Germline:** GATK4 HaplotypeCaller, FreeBayes
- **Somatic:** GATK4 **Mutect2** (read-orientation & contamination models)
- **Structural variants / CNV:** Manta, Strelka, GRIDSS, Delly, CNVkit
- **Annotation & reporting:** **VEP**, **AnnotSV**, variant QC summaries

83 modules backed by **61 `nf-test` unit tests and snapshots**, with version
pinning and seeded, reproducible runs — the most engineering-mature project in my
portfolio.
