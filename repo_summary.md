# NgocKhoi Dang — Bioinformatics Portfolio Summary

> Auto-generated from 23 private Git repositories on UTSW BioHPC GitLab
> (`git.biohpc.swmed.edu/s241653` and collaborating lab namespaces).
> Sole author of all **206 commits** spanning **2025-06-20 → 2026-06-10** (~12 months).
> Use this file as raw material for your personal website / CV — adapt the prose freely.

---

## Narrative Bio

I'm a bioinformatics scientist at UT Southwestern Medical Center, where I build
reproducible, production-grade analysis pipelines for a broad set of wet-lab
collaborators across genomics, transcriptomics, proteomics, metabolomics, spatial
biology, and epigenomics. Over the past year I single-handedly authored and
maintained **23 analysis projects** for **9+ different labs** (Chen, Bachoo, Conzen,
Tu, Selfa, Wang, Zheng, and others), turning raw sequencing and mass-spec data into
publication-ready results.

My work centers on **workflow engineering** — I design modular **Nextflow DSL2**
pipelines that run on **SLURM HPC** with full **Apptainer/Docker containerization**,
and I maintain a personal library of **68 version-locked container images** covering
the modern bioinformatics toolchain (GATK4, BWA-MEM2, STAR, Salmon, MACS3, deepTools,
VEP, DeepVariant/DeepSomatic, and many more). On the analysis side I'm fluent in **R**
(Bioconductor, DESeq2, limma, Seurat-style single-cell, enrichment/pathway analysis)
and **Python** (scanpy, squidpy, anndata, rapids-singlecell for GPU-accelerated
single-cell, PyTorch/PyTorch-Lightning for deep learning).

I treat scientific software as software: my flagship variant-calling pipeline ships
with **61 `nf-test` unit tests and snapshots** across 83 modules. I care about
reproducibility (seeded stochastic steps, version pinning, containerized environments)
and about handing collaborators clean, interpretable reports.

**Domains:** DNA variant calling (germline/somatic/structural) · bulk & single-cell/
single-nucleus RNA-seq · spatial transcriptomics (Visium HD) · ChIP-seq/CUT&RUN
epigenomics · (phospho)proteomics · metabolomics · DNA methylation arrays · protein
function prediction (deep learning).

---

## Quantified Activity

| Metric | Value |
|---|---|
| Repositories authored/maintained | **23** |
| Collaborating lab namespaces | **9+** |
| Total commits (all by me) | **206** |
| Active window | 2025-06-20 → 2026-06-10 (~12 months) |
| Nextflow process files (`.nf`) | 161 files · ~8,400 lines |
| R scripts/reports (`.R`/`.Rmd`) | 118 files · ~43,700 lines |
| Python sources (`.py`) | 35 files · ~5,900 lines |
| Jupyter notebooks | 19 |
| Shell scripts | 57 |
| Dockerfiles (container recipes) | **68** |
| `nf-test` tests + snapshots (vc-dicer1) | 61 + 61 |

**Most active project:** `vc-dicer1` — 81 commits over ~10 months (Jul 2025 – May 2026).

---

## Projects

Grouped by domain. Each entry: collaborator/namespace · what it does · your stack.

### DNA Variant Calling & Genomics

**vc-dicer1** — *Chen lab · 81 commits · flagship*
Ultra-deep DICER1 targeted-panel variant-calling pipeline. Production-grade **Nextflow
DSL2**, cohort-scale on **SLURM** with full **Apptainer** containerization. Covers the
complete germline + somatic + **structural-variant** workflow across 10 stages: QC →
BWA-MEM2 mapping → GATK4 BQSR → HaplotypeCaller/FreeBayes (germline) →
Mutect2 (somatic) → SV calling → VEP/AnnotSV annotation → variant QC & reporting.
83 modules backed by **61 nf-test unit tests + snapshots** — the most engineering-mature
repo in the portfolio.

**vc_lurbinectedin** — *Selfa lab · 12 commits*
Somatic variant calling on paired tumor-normal mouse cell lines treated with
Lurbinectedin and RR-III-11. Nextflow on SLURM: fastqc/multiqc → trim_galore →
BWA-MEM2 → GATK4 (MarkDuplicates, BQSR) → **Mutect2** (with read-orientation &
contamination models) and **DeepSomatic** → **VEP** annotation (GRCm39), plus
downstream R analysis.

### Bulk RNA-seq & Differential Expression

**gr_dex** — *Conzen lab · 8 commits*
Glucocorticoid-receptor / dexamethasone RNA-seq study. EDA (PCA, sample-correlation
heatmaps, dispersion), DESeq2 differential expression across GR/E2/Dex/C134 contrasts,
and over-representation/pathway enrichment (ORA-BP). R Markdown reports.

**rnaseq_celllines** — *Bachoo lab · 1 commit*
nf-core/rnaseq quantification + custom R differential-expression analysis (DESeq2)
across cell-line conditions, with MA plots, Venn diagrams, and ORA enrichment.

### Novel-Transcript / De-novo Assembly

**Saikat_set2_novel** — *Tu lab · 6 commits*
Novel/cryptic transcript discovery. Custom **Nextflow** pipeline using StringTie
(merge, split-BAM, quant), gffcompare, BAM/GTF subtraction & intersection, plus SPAdes
and nf-core/denovotranscript for de-novo assembly.

### ChIP-seq / CUT&RUN Epigenomics

**pc-abd1** — *Tu lab · 4 commits*
Quantitative ChIP-seq of mRNA-capping enzyme Abd1 and Pol II occupancy in
*S. cerevisiae*, using **ChIP-Rx spike-in normalization** (*Drosophila* reference).
Nextflow: trim_galore → BWA-MEM2 → MarkDuplicates → MACS3 / SEACR / LanceOtron peak
calling → deepTools (bamCompare, computeMatrix, metagene plots) → scale-factor
spike-in normalization.

**m7gip** — *Tu lab · 6 commits*
Histone-modification ChIP-seq (K4me3/K36me3/K79me3) in yeast (YPL vs SL conditions).
Nextflow peak-calling pipeline + **karyoploteR** genome-wide visualizations and R
downstream analysis.

### Single-cell / Single-nucleus RNA-seq

**snrna_drosha** — *Chen lab · 12 commits*
snRNA-seq of mouse kidney comparing WT, Drosha-KO (EK), and compound mutant (WCEK).
**Python/scanpy** pipeline: CellBender background removal → anndata concat → BioMart
gene-symbol mapping → QC/filtering → clustering & annotation. Conda-env reproducible.

**scrna_nephrogenic** — *Chen lab · 3 commits*
scRNA-seq of mutant vs control nephrogenic-zone cells at embryonic stages E15/E17.
R Markdown analysis & HTML reports.

**pipeline_scrna** — *personal · 16 commits*
A reusable single-cell RNA-seq analysis pipeline/framework in **R** (21 R modules,
config-driven, lintr-linted) — your in-house scRNA toolkit.

**scrna / spatialscRNA / pipeline_metabolomic** — *personal · prototyping repos*
Notebook-driven prototypes and HPC job scripts for single-cell, spatial, and
metabolomics analyses.

### Spatial Transcriptomics

**cuprizone_visiumhd** — *Wang lab · 2 commits*
Whole-brain **Visium HD** spatial transcriptomics of a mouse cuprizone demyelination
model (8 samples across disease stages). **Python** notebook pipeline: **bin2cell**
H&E+GEX segmentation → QC → normalize/HVG/PCA → **Harmony** batch integration → Leiden
→ UMAP → dual annotation (EnrichR cluster-level + **Allen MapMyCells** cell-level) →
cellxgene export → composition + **pseudobulk DESeq2 DE** + GO/pathway enrichment.
GPU-accelerated (**rapids-singlecell**), fully seeded for reproducibility.

### Proteomics & Phosphoproteomics

**phospho-pcf** — *Bachoo lab · 2 commits*
Phosphoproteomics & proteomics differential analysis (DTPCs vs Peg vs NoPeg). R:
DEA, volcano plots, and **KSEA** kinase-substrate enrichment (kinase score heatmaps).

**phosphoproteomics-aa** — *Enoch lab · 2 commits*
Phosphosite-level differential analysis with gene-level summaries and kinase
inference. R.

**Proteomic** — *Bachoo lab · 2 commits*
GBM "diet ecology" study — country-level ecological correlation between dietary
macronutrients and glioblastoma incidence (GLOBOCAN 2022), replicating a published
PDAC approach. R Markdown.

**T2-FLAIR** — *Enoch lab · 6 commits*
Proteomics analysis (Evan lab dataset): **harmonizR** batch harmonization + random-
forest modeling, GSEA against MSigDB GO-BP / Reactome gene sets. R.

### Metabolomics

**metabolomics** — *Bachoo lab · 7 commits*
GBM metabolomics: differential abundance + **MSEA/QEA/ORA** metabolite-set enrichment.
R Markdown reports.

### DNA Methylation

**ft_oe_occc** — *Zheng lab · 1 commit*
Illumina methylation-array analysis with **SeSAMe** (QC, masking, sex prediction,
SNP-identity, MDS/batch). R, with parquet/RDS outputs.

### Machine Learning

**cafa6** — *Kaggle competition · 7 commits*
Protein function prediction (Gene Ontology). **PyTorch / PyTorch-Lightning** deep
learning: CNN, Transformer, and hierarchical-loss models over protein-language-model
embeddings (**ESM3**, HuggingFace transformers `AutoModel`), multi-label GO term
prediction, distributed training (DDP), mixed precision (AMP), K-fold CV.

### Infrastructure & DevOps

**workplace_setup** — *personal · 17 commits*
Your reproducibility backbone: **68 Dockerfiles** building version-locked container
images of the entire bioinformatics toolchain, plus conda/mamba environment
definitions (scanpy, squidpy, scvi, rapids, harmony, SANTO, PyTorch). Tools include:
GATK4, BWA/BWA-MEM2, STAR, Salmon, StringTie, MACS3, deepTools, VEP, AnnotSV,
DeepVariant, DeepSomatic, Manta, Strelka, GRIDSS, Delly, CNVkit, FreeBayes,
SpliceAI, Trinity, MEGAHIT, SPAdes, Kraken2, fastp, FastQC, MultiQC, Qualimap,
Picard, mosdepth, RSeQC, Subread, UMI-tools, SortMeRNA, SEACR, LanceOtron, cellxgene,
and more.

**rstudio-hpc** ("Nextflow Conda Docker Builder") — *personal · 6 commits*
A build system that turns a single YAML of tools/versions into lightweight,
version-locked Docker images for Nextflow — multi-stage builds, parallel Mamba
environment creation, Docker Hub push, smart skip-if-exists, and force-rebuild flags.

---

## Skills & Technologies

**Languages**
R · Python · Bash/Shell · Nextflow DSL2 · Groovy (Nextflow config)

**Workflow & Infrastructure**
Nextflow (DSL2, modular pipelines) · SLURM HPC · Apptainer/Singularity · Docker ·
Mamba/Conda · nf-test (pipeline unit testing) · nf-core · Git/GitLab · YAML-driven
config · multi-stage container builds · Docker Hub CI

**Genomics / Variant Calling**
GATK4 (HaplotypeCaller, Mutect2, BQSR, MarkDuplicates) · DeepVariant · DeepSomatic ·
FreeBayes · BWA-MEM2 · STAR · structural variants (Manta, Strelka, GRIDSS, Delly) ·
CNVkit · VEP · AnnotSV · SpliceAI · Picard · SAMtools/BCFtools · mosdepth

**Transcriptomics**
Bulk RNA-seq (nf-core/rnaseq, Salmon, StringTie, Subload) · DESeq2 · limma ·
differential expression · ORA/GSEA enrichment · de-novo transcript assembly
(Trinity, SPAdes, gffcompare)

**Single-cell & Spatial**
scanpy · anndata · squidpy · rapids-singlecell (GPU) · CellBender · Harmony batch
integration · Leiden clustering · bin2cell · Visium HD · Allen MapMyCells ·
cellxgene · BioMart annotation · pseudobulk DE

**Epigenomics**
ChIP-seq / CUT&RUN · MACS3 · SEACR · LanceOtron · deepTools · ChIP-Rx spike-in
normalization · karyoploteR · DNA methylation arrays (SeSAMe)

**Proteomics / Metabolomics**
Differential abundance · KSEA (kinase-substrate enrichment) · harmonizR batch
correction · MSEA/QEA · MSigDB/Reactome GSEA

**Machine Learning**
PyTorch · PyTorch-Lightning · Transformers / protein language models (ESM3) · CNN &
Transformer architectures · hierarchical multi-label classification · DDP distributed
training · mixed-precision (AMP) · scikit-learn · K-fold CV

**Reporting & Reproducibility**
R Markdown · Jupyter · MultiQC · version pinning · seeded stochastic pipelines ·
containerized environments · interpretable collaborator-facing HTML reports

---

## Repository Index

| Repo | Lab | Domain | Commits |
|---|---|---|---|
| vc-dicer1 | Chen | Variant calling (panel) | 81 |
| workplace_setup | personal | Infra / containers | 17 |
| pipeline_scrna | personal | scRNA framework | 16 |
| vc_lurbinectedin | Selfa | Somatic variant calling | 12 |
| snrna_drosha | Chen | snRNA-seq | 12 |
| gr_dex | Conzen | RNA-seq DE | 8 |
| metabolomics | Bachoo | Metabolomics | 7 |
| cafa6 | Kaggle | ML / protein function | 7 |
| m7gip | Tu | ChIP-seq | 6 |
| Saikat_set2_novel | Tu | Novel transcripts | 6 |
| T2-FLAIR | Enoch | Proteomics | 6 |
| rstudio-hpc | personal | Infra / image builder | 6 |
| pc-abd1 | Tu | ChIP-seq (spike-in) | 4 |
| scrna_nephrogenic | Chen | scRNA-seq | 3 |
| pipeline_metabolomic | personal | Metabolomics proto | 3 |
| Proteomic | Bachoo | Ecological / proteomics | 2 |
| phospho-pcf | Bachoo | Phosphoproteomics | 2 |
| phosphoproteomics-aa | Enoch | Phosphoproteomics | 2 |
| cuprizone_visiumhd | Wang | Spatial (Visium HD) | 2 |
| rnaseq_celllines | Bachoo | RNA-seq DE | 1 |
| scrna | personal | scRNA proto | 1 |
| spatialscRNA | personal | Spatial proto | 1 |
| ft_oe_occc | Zheng | DNA methylation | 1 |

---

*Generated locally on UTSW BioHPC. Collaborator names and unpublished project details
are included for your reference — review and redact anything non-public before posting
to a public website.*
