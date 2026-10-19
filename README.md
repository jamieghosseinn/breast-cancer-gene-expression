# Exploratory analysis of MMP11 and SCARA5 in breast cancer

Jamie Ghossein — Foundations of Data Science final project.

This project explores course-provided RNA-seq counts and metadata from the TCGA Breast Invasive Carcinoma (TCGA-BRCA) cohort. It compares MMP11 and SCARA5 across 1,111 primary tumor, 113 normal tissue, and seven metastatic samples.

The analysis includes summary statistics, a histogram, a scatter plot highlighting metastatic samples in response to peer feedback, box plots, a ten-gene heatmap with tissue and PAM50 annotations, and empirical cumulative distribution function (ECDF) plots. Findings are descriptive and exploratory.

## Files

- `analysis.Rmd`: analysis code, explanations, and figure/table exports.
- `Jamie-Ghossein-Final-Project.pdf`: knitted code document from the original local analysis.
- `report.tex`: LaTeX report source.
- `report.pdf`: compiled final report.
- `figures/`: exported PDF figures used by the report.
- `tables/`: exported summary statistics and software versions.
- `data/`: folder for the course-provided input files; raw CSVs are not included.

The repository's R Markdown is a copy of the submitted analysis with the computer-specific working directory replaced by relative input paths. The existing knitted code PDF was generated from the original local file.

## Data

Obtain `counts.csv` and `meta_data.csv` from the course materials and place them in `data/`. The count matrix contains 60,660 genes and 1,231 samples. The course-provided count file is approximately 205 MB and is excluded from this repository.

Source cohort documentation: [NCI Genomic Data Commons — TCGA-BRCA](https://portal.gdc.cancer.gov/projects/TCGA-BRCA).

## Reproduce the analysis

1. Download or clone the repository, preserving its folder structure.
2. Add the two course-provided CSV files to `data/`.
3. Open `analysis.Rmd` in RStudio and knit it to PDF. Run code in a fresh R session. When running individual chunks, use the repository root as the working directory.
4. The final chunk exports the report's figures and tables.
5. Compile `report.tex` with pdfLaTeX twice from the repository root to resolve citations and figure references. References are written directly in the source; BibTeX is not required.

PDF generation requires a LaTeX installation, such as TinyTeX. The report can be compiled using the included figures without the raw data.

## Software used

R 4.6.1; tidyverse 2.0.0; ggplot2 4.0.3; dplyr 1.2.1; tidyr 1.3.2; tibble 3.3.1; ComplexHeatmap 2.28.0; circlize 0.4.18; scales 1.4.0; knitr 1.51; rmarkdown 2.32.

## Interpretation

MMP11 generally had higher counts in primary tumors than normal tissue, while SCARA5 showed the opposite pattern. Metastatic samples overlapped the broad primary tumor range. Log-transformed raw counts do not normalize sequencing depth; the heatmap uses CPM followed by log transformation and row standardization. Gene selection and plotting used the same dataset, groups were unequal in size, and some samples came from the same patients. These results do not establish causation or a validated diagnostic test.
