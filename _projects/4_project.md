---
layout: page
title: Spatial transcriptomics (Visium HD)
description: Whole-tissue spatial profiling with GPU-accelerated single-cell
img: assets/img/5.jpg
importance: 4
category: analyses
related_publications: false
---

Whole-tissue **Visium HD** spatial transcriptomics across multiple samples and
disease stages. Python pipeline: **bin2cell** H&E + GEX segmentation → QC →
normalize / HVG / PCA → **Harmony** batch integration → **Leiden** clustering →
UMAP → dual annotation (cluster- and cell-level) → cellxgene export →
composition analysis and **pseudobulk DESeq2** differential expression with
GO/pathway enrichment.

GPU-accelerated with **rapids-singlecell** and fully seeded for reproducibility.
