---
layout: page
title: Protein function prediction (deep learning)
description: Multi-label GO prediction with ESM3 embeddings — Kaggle CAFA
img: assets/img/11.jpg
importance: 8
category: analyses
related_publications: false
---

**Why it matters.** The overwhelming majority of known proteins have never been
experimentally characterized. Computational **Gene Ontology** prediction scales
functional inference across entire proteomes, accelerating hypothesis generation
and helping prioritize which proteins are worth experimental follow-up.

**Approach & tools.** A deep-learning entry for the **CAFA** Kaggle competition
in **PyTorch / PyTorch-Lightning**:

- protein representations from the **ESM3** protein language model
  (HuggingFace `transformers`, `AutoModel`)
- CNN, Transformer, and hierarchical-loss architectures for **multi-label** GO-term
  prediction (respecting the GO hierarchy)
- distributed training (**DDP**), mixed precision (**AMP**), and K-fold
  cross-validation; scikit-learn for evaluation
