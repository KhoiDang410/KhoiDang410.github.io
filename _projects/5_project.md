---
layout: page
title: ChIP-seq & CUT&RUN epigenomics
description: Spike-in-normalized peak calling & genome-wide visualization
img: assets/img/6.jpg
importance: 5
category: analyses
related_publications: false
---

**Why it matters.** Chromatin state and protein–DNA occupancy govern which genes
are transcribed. Crucially, when a perturbation shifts histone marks or polymerase
occupancy *globally*, standard read-depth normalization hides the change — it makes
every sample look the same. **Spike-in (ChIP-Rx) normalization** restores absolute,
quantitative comparison, which is what lets these experiments detect genome-wide
epigenetic shifts rather than just relative redistribution.

**Approach & tools.** A **Nextflow** epigenomics pipeline:

- Trim Galore → BWA-MEM2 → Picard MarkDuplicates
- peak calling with **MACS3**, **SEACR**, and **LanceOtron**
- **deepTools** (bamCompare, computeMatrix, metagene/heatmap plots)
- spike-in scale-factor normalization (e.g., *Drosophila* reference)
- **karyoploteR** genome-wide visualizations and R downstream analysis
