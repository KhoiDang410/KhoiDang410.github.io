---
layout: page
title: Spatial transcriptomics (Visium HD)
description: Whole-tissue spatial profiling with GPU-accelerated single-cell
img: assets/img/5.jpg
importance: 4
category: analyses
related_publications: false
---

**Why it matters.** Dissociating tissue for single-cell sequencing discards
spatial context. Spatial transcriptomics keeps tissue architecture intact, mapping
not just *what* genes change but *where* — which is decisive in structured organs
like the brain, where region- and cell-type-specific responses (e.g., during
demyelination and remyelination) define how a disease progresses.

**Approach & tools.** A **Visium HD** Python pipeline across multiple samples and
disease stages:

- **bin2cell** H&E + gene-expression segmentation into cell-like objects
- QC → normalization / HVG / PCA → **Harmony** batch integration
- **Leiden** clustering → UMAP
- dual annotation: **EnrichR** (cluster-level) + **Allen MapMyCells** (cell-level)
- **cellxgene** export, composition analysis, and **pseudobulk DESeq2**
  differential expression with GO / pathway enrichment

GPU-accelerated with **rapids-singlecell** and fully seeded for reproducibility.
