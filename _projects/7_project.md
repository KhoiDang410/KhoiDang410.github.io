---
layout: page
title: Proteomics & metabolomics analysis
description: Differential abundance, KSEA, batch harmonization, set enrichment
img: assets/img/9.jpg
importance: 7
category: analyses
related_publications: false
---

**Why it matters.** Transcript levels are an imperfect proxy for what a cell
actually does. **Phosphoproteomics** reads out active signaling — which kinase
pathways are switched on — while **metabolomics** captures metabolic reprogramming.
Together they reveal how cells rewire signaling and metabolism in disease, a layer
of biology invisible to RNA-seq alone.

**Approach & tools.** R analysis workflows across phospho-, total-proteomics, and
metabolomics datasets:

- differential abundance and volcano plots
- **KSEA** kinase-substrate enrichment (kinase-score heatmaps) for signaling inference
- **harmonizR** batch harmonization paired with random-forest modeling
- **MSEA / QEA** metabolite-set enrichment and **GSEA** against MSigDB / Reactome
- collaborator-facing R Markdown / HTML reports
