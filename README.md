# 🧠 Glioblastoma Multi-Omics Analysis Using MOFA

<p align="center">
  <b>Educational / Exploratory Multi-Omics Project</b>
</p>

<p align="center">
  R • Multi-Omics • MOFA • Glioblastoma • Data Analysis
</p>

---

## 📌 Project Overview

This project explores the integration of multiple molecular data layers from **glioblastoma** using **Multi-Omics Factor Analysis (MOFA)**.

The analysis was developed as part of a multi-omics analysis course and focuses on data handling, quality control, exploratory analysis, differential analysis, and multi-omics integration using **R**.

The project represents the **original educational analysis** completed during the course. Following feedback and methodological review, several preprocessing and analytical decisions were identified for improvement. These limitations are documented below as part of the learning process.

---

## 🔬 Research Question

> **Can multi-omics factor analysis identify latent sources of molecular variation across multiple molecular layers in glioblastoma?**

---

## 🧬 Omics Layers

| Omics Layer            | Biological Information          |
| ---------------------- | ------------------------------- |
| 🧬 **mRNA**            | Gene expression                 |
| 🧪 **Proteomics**      | Protein abundance               |
| 🧬 **DNA Methylation** | Epigenetic regulation           |
| 🧬 **miRNA**           | Post-transcriptional regulation |
| 🧬 **Mutations**       | Genomic alterations             |

---

## 🔄 Analysis Workflow

```text
                    Glioblastoma Data
                           │
             ┌─────────────┼─────────────┐
             ↓             ↓             ↓
           mRNA       Proteomics    Methylation
             │             │             │
             └─────────────┼─────────────┘
                           ↓
                    Data Processing
                           ↓
                     Quality Control
                           ↓
                  Exploratory Analysis
                           ↓
               Differential Analysis
                           ↓
                 Multi-Omics Integration
                           ↓
                          MOFA
                           ↓
                Latent Factor Analysis
                           ↓
                Variance Explained
                           ↓
              Biological Interpretation
```

---

## 💻 Tools & Technologies

| Tool / Package   | Purpose                     |
| ---------------- | --------------------------- |
| **R**            | Statistical analysis        |
| **MOFA**         | Multi-omics factor analysis |
| **limma**        | Differential analysis       |
| **ggplot2**      | Data visualization          |
| **tidyverse**    | Data manipulation           |
| **LinkedOmics**  | Data source                 |
| **Google Colab** | Computational environment   |

---

## 📊 Quality Control & Exploratory Analysis

The analysis included exploratory quality-control procedures to investigate sample relationships and variation within the different molecular layers.

Examples of analyses performed include:

* Sample correlation analysis
* PCA
* Sample-level quality assessment
* Visualization before and after quality-control procedures

### PCA

<p align="center">
  <img src="figures/qc/PCA_before_QC.png" width="45%">
  <img src="figures/qc/PCA_after_QC.png" width="45%">
</p>

<p align="center">
  <i>Exploratory PCA before and after the original quality-control workflow.</i>
</p>

> ⚠️ **Note:** These visualizations belong to the original educational analysis. The preprocessing strategy was subsequently identified as requiring revision, so these figures should be considered exploratory rather than definitive biological results.

---

## 📈 Differential Analysis

An initial differential analysis was performed to explore molecular differences between **EGFR-mutant** and **EGFR-wild-type** glioblastoma samples.

The original analysis used the **limma** framework and evaluated differential expression using adjusted p-values and log₂ fold-change thresholds.

### Volcano Plot

<p align="center">
  <img src="figures/differential_expression/volcano_plot.png" width="75%">
</p>

> ⚠️ This analysis was part of the original workflow and is retained for documentation of the project development. It should not be interpreted as the final biological analysis.

---

## 🧠 Multi-Omics Factor Analysis

**MOFA (Multi-Omics Factor Analysis)** was used to identify latent factors capturing patterns of variation across the molecular layers.

The original analysis integrated:

* mRNA
* Proteomics
* DNA methylation
* miRNA
* Mutation data

### Variance Explained

| Omics Layer     | Variance Explained |
| --------------- | -----------------: |
| DNA Methylation |             87.44% |
| Proteomics      |             31.72% |
| miRNA           |              9.38% |
| mRNA            |              8.28% |
| Mutations       |              0.06% |

### MOFA Visualization

<p align="center">
  <img src="figures/mofa/variance_explained.png" width="75%">
</p>

> ⚠️ **Interpretation note:** These values originate from the original educational analysis. Because the preprocessing strategy requires revision, they should not be considered validated biological findings.

---

# ⚠️ Limitations & Lessons Learned

This project was particularly valuable as a learning exercise because subsequent review highlighted several methodological issues.

### 1. Preprocessing and normalization

The LinkedOmics data used in this project had already undergone normalization. An additional normalization step was therefore applied unnecessarily during the original analysis.

A corrected analysis should work from the appropriately prepared LinkedOmics data without introducing an unnecessary second normalization step.

### 2. Differential analysis before MOFA

Differential analysis was performed before the MOFA integration step.

For the intended unsupervised multi-omics integration workflow, this step was not required and should be reconsidered in a corrected analysis.

### 3. Biological interpretation

The project highlighted the importance of understanding the **biological meaning of each omics layer** rather than treating the analysis as purely computational.

Further investigation is required to connect latent factors and molecular patterns to relevant glioblastoma biology and pathways.

### Overall lesson

> **A computational result is not automatically a biological finding.**

The project helped reinforce the importance of understanding the dataset, validating preprocessing decisions, selecting appropriate analytical methods, and critically evaluating the biological meaning of statistical outputs.

---

## 📚 What I Learned

### Computational Skills

* R programming
* Multi-omics data handling
* Data preprocessing
* Quality-control analysis
* PCA and exploratory data analysis
* Differential analysis
* MOFA
* Data visualization
* Working with heterogeneous molecular datasets

### Scientific Skills

* Evaluating preprocessing strategies
* Understanding different molecular data types
* Interpreting variation across omics layers
* Distinguishing computational output from biological conclusions
* Critically evaluating an analysis pipeline
* Recognizing methodological limitations
* Connecting computational analysis with biological interpretation

---

## 📁 Repository Structure

```text
glioblastoma-multiomics-mofa/
│
├── 📄 README.md
│
├── 📁 analysis/
│   └── glioblastoma_multiomics_mofa_original.ipynb
│
├── 📁 scripts/
│   └── glioblastoma_mofa_analysis.R
│
├── 📁 figures/
│   ├── 📁 qc/
│   ├── 📁 differential_expression/
│   └── 📁 mofa/
│
├── 📁 results/
│   └── README.md
│
├── 📁 data/
│   └── README.md
│
└── 📁 presentation/
    └── Glioblastoma_Multiomics_Project.pdf
```

---

## 🔮 Future Improvements

A future version of this project will aim to:

* Revisit the preprocessing strategy
* Remove unnecessary normalization
* Re-run the MOFA analysis using appropriately prepared data
* Re-evaluate factor structure and significance
* Perform deeper biological interpretation
* Investigate pathways associated with important molecular factors
* Explore biologically meaningful relationships between the different omics layers

> **Future work:** A corrected version of the analysis may be added to this repository following further review.

---

## 📖 Data Source

The molecular datasets used in this project were obtained from **LinkedOmics**.

Raw datasets are not included in this repository. Dataset identifiers and relevant information can be provided in the `data/README.md` file.

---

## 👩‍💻 Author

**Merna Amr**

Biotechnology Graduate | Bioinformatics & Computational Biology

---

<p align="center">
  <i>This repository documents an educational multi-omics analysis and the methodological lessons learned throughout the project of EgCompBio online diploma previously sponsored by DAAD.</i>
</p>
