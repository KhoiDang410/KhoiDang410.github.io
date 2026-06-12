---
layout: page
title: ChIP-seq & CUT&RUN epigenomics
description: Spike-in-normalized peak calling & genome-wide visualization
img: assets/img/6.jpg
importance: 5
category: analyses
related_publications: false
---

Quantitative ChIP-seq / CUT&RUN pipelines using **ChIP-Rx spike-in
normalization** for accurate cross-sample comparison. Nextflow workflow:
trim_galore → BWA-MEM2 → MarkDuplicates → **MACS3 / SEACR / LanceOtron** peak
calling → **deepTools** (bamCompare, computeMatrix, metagene plots) →
scale-factor normalization, plus **karyoploteR** genome-wide visualizations and
R downstream analysis.
