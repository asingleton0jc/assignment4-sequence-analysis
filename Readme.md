Readme
================
Aaron Malcolm Singleton
2025-10-05

## Overview

This repository contains R scripts and analyses for two parts of the
final assignment:

**Part 1:** Gene expression and tree growth analysis  
- Analyze RNA-seq gene expression data.  
- Analyze tree growth measurements over 20 years at two sites.

**Part 2:** Biological sequence diversity analysis  
- Compare coding DNA sequences (CDS) and protein sequences of **E. coli
K-12** and **Mycoplasma hyopneumoniae ES-2**.  
- Analyze CDS counts, sequence lengths, nucleotide and amino acid
frequencies, codon usage, and protein k-mers.

------------------------------------------------------------------------

## Part 1: Gene Expression and Tree Growth Analysis

**Purpose:**  
Develop skills in importing data, performing calculations, visualizing
results, and statistical testing in R.

**Input Files:**  
- **Gene expression data:** `gene_expression.tsv`  
URL: [Raw GitHub
link](https://raw.githubusercontent.com/ghazkha/Assessment4/main/gene_expression.tsv)  
- **Tree growth data:** `growth_data.csv`  
URL: [Raw GitHub
link](https://raw.githubusercontent.com/ghazkha/Assessment4/main/growth_data.csv)

**Steps / Workflow:**  
1. Import the gene expression dataset. Set gene identifiers as row
names.  
2. Calculate mean expression per gene and add as a new column.  
3. Identify the top 10 genes by mean expression.  
4. Count genes with mean expression \< 10.  
5. Create a histogram of log-transformed mean expression.  
6. Import the tree growth dataset. Check column names.  
7. Calculate mean and standard deviation of tree circumference at start
(2005) and end (2020).  
8. Create boxplots for tree circumference at start and end.  
9. Calculate mean growth over the last 10 years (2010–2020).  
10. Perform t-tests comparing 10-year growth between sites and visualize
results.

**Outputs:**  
- Tables: First six genes, mean expression, top 10 genes, tree growth
statistics.  
- Plots: Histogram of gene expression, boxplots of tree circumference
and growth.

**Script:** `Part1_GeneGrowth.Rmd`

------------------------------------------------------------------------

## Part 2: Biological Sequence Diversity

**Purpose:**  
Compare genome features and sequence statistics of two bacterial
organisms to understand coding DNA and protein diversity.

**Input Files (CDS DNA):**  
- **E. coli K-12:**  
URL: [Ensembl Bacteria
link](https://ftp.ensemblgenomes.ebi.ac.uk/pub/bacteria/release-62/fasta/bacteria_30_collection/escherichia_coli_k_12_gca_004803305/cds/Escherichia_coli_k_12_gca_004803305.ASM480330v1.cds.all.fa.gz)  
- **Mycoplasma hyopneumoniae ES-2:**  
URL: [Ensembl Bacteria
link](https://ftp.ensemblgenomes.ebi.ac.uk/pub/bacteria/release-62/fasta/bacteria_40_collection/mesomycoplasma_hyopneumoniae_gca_004768725/cds/Mesomycoplasma_hyopneumoniae_gca_004768725.ASM476872v1.cds.all.fa.gz)

**Steps / Workflow:**  
1. Load required libraries: Biostrings, seqinr, ggplot2, dplyr, tidyr.  
2. Download and load CDS files. Unzip as necessary.  
3. Count the number of coding sequences for each organism. Present
results in a table.  
4. Calculate total coding DNA length and present in a table.  
5. Create boxplots of CDS length; calculate mean and median lengths.  
6. Calculate nucleotide frequencies and plot for each organism.  
7. Translate CDS into protein sequences; calculate amino acid
frequencies and create bar plots.  
8. Compute codon usage and visualize the first 20 codons as an
example.  
9. Perform k-mer analysis (length = 3) for proteins; identify top 10
over-represented k-mers in both organisms.

**Outputs:**  
- Tables: CDS counts, total coding DNA length, mean/median CDS lengths,
top k-mers.  
- Plots: CDS length distribution, nucleotide frequency, amino acid
frequency, codon usage.

**Script:** `Final_Assignment_Part2.Rmd`

**Notes:**  
- All data are automatically downloaded from Ensembl Bacteria.  
- Missing codons are set to 0 for comparison purposes.  
- Plots are produced using ggplot2 for clarity.  
- R.utils::gunzip() is used to unzip `.gz` files.

------------------------------------------------------------------------

## Additional Notes

- Both RMarkdown scripts are fully reproducible. Knitting produces HTML
  or PDF reports.  
- All scripts contain comments explaining each step.  
- The repository is structured for clarity, with raw data, scripts,
  results, and reports organized in separate folders.
