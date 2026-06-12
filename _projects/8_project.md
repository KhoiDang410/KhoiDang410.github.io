---
layout: page
title: Protein function prediction (deep learning)
description: Multi-label GO prediction with ESM3 embeddings — Kaggle CAFA
img: assets/img/11.jpg
importance: 8
category: analyses
related_publications: false
---

Deep-learning **protein function prediction** (Gene Ontology) for the
**CAFA** Kaggle competition. **PyTorch / PyTorch-Lightning**: CNN, Transformer,
and hierarchical-loss models built over protein-language-model embeddings
(**ESM3**, HuggingFace `transformers`), predicting multi-label GO terms with
distributed training (DDP), mixed precision (AMP), and K-fold cross-validation.
