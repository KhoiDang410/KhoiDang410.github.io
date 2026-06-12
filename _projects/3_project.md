---
layout: page
title: Single-cell & single-nucleus RNA-seq
description: scanpy / Seurat-style pipelines + a reusable in-house scRNA framework
img: assets/img/1.jpg
importance: 3
category: analyses
related_publications: false
---

**Why it matters.** Bulk RNA-seq averages over every cell in a sample; single-cell
and single-nucleus resolution instead reveal *which* cell populations within a
complex tissue (e.g., kidney) change in response to a genetic perturbation. That
makes it possible to pinpoint the specific cell types driving a developmental or
disease phenotype — signal that bulk assays wash out.

**Approach & tools.** End-to-end **Python/scanpy** pipelines:

- **CellBender** ambient-RNA / background removal
- **anndata** concatenation, **BioMart** gene-symbol mapping
- QC and doublet filtering → normalization / HVG / PCA
- neighborhood graph → **Leiden** clustering → UMAP → marker-based annotation

Alongside R Markdown / **Seurat**-style reports for collaborators, and a reusable,
**config-driven in-house scRNA framework** (21 R modules, lintr-linted) that
standardizes the workflow across studies. Conda-env reproducible throughout.
