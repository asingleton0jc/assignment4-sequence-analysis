---
title: "Final Assignment README"
author: "Aaron Malcolm Singleton"
date: "2025-10-05"
output: 
  html_document:
    toc: true
    fig_width: 7
    fig_height: 7
---

# Overview

This repository contains R scripts and analyses for the final assignment, divided into two main parts:  

**Part 1:** Gene expression and tree growth analysis  
- Analyze RNA-seq gene expression data.  
- Analyze tree growth measurements over 20 years at two sites.  

**Part 2:** Biological sequence diversity analysis  
- Compare coding DNA sequences (CDS) and protein sequences of **E. coli K-12** and **Mycoplasma hyopneumoniae ES-2**.  
- Analyze CDS lengths, nucleotide and amino acid frequencies, codon usage, and protein k-mers.  

---

# Part 1: Gene Expression and Tree Growth Analysis

**Workflow / Steps:**

1. Import `gene_expression.tsv` and inspect first six genes.  
   - Ensures data loaded correctly.  

2. Identify numeric columns representing expression measurements.  

3. Add a new column `mean_expression` per gene.  
   - Computes average expression across all samples.  

4. Sort genes by mean expression and identify top 10.  

5. Count genes with mean expression < 10.  

6. Log-transform mean expression and plot a histogram.  

7. Import `growth_data.csv` and inspect column names.  

8. Calculate growth from 2005–2020 and mean growth by site.  

9. Create boxplots of growth by site.  

10. Perform t-tests comparing growth between sites.  

11. Summarize mean and standard deviation of tree circumference at start (2005) and end (2020).  

12. Visualize tree circumference over time using long-format boxplots.  

13. Calculate growth from 2010–2020 and perform t-tests for 10-year growth.  

**Outputs:**  
- **Tables:** First six genes, mean expression, top 10 genes, number of low-expression genes, tree growth summary.  
- **Plots:** Histogram of log-transformed expression, boxplots of tree circumference and growth.  

---

# Part 2: Biological Sequence Diversity

**Workflow / Steps:**

1. Load required libraries (`seqinr`, `R.utils`).  

2. Download CDS files for *E. coli K-12* and *M. hyopneumoniae ES-2* from Ensembl Bacteria.  
   - Unzip `.gz` files using `R.utils::gunzip()`.  
   - Load sequences with `read.fasta()`.  

3. Count number of CDS for each organism.  

4. Calculate total, mean, and median CDS lengths; create boxplots.  

5. Calculate DNA base frequencies (A, T, C, G) and plot bar charts.  

6. Translate CDS to protein sequences; compute amino acid frequencies and plot.  

7. Compute codon usage (RSCU) and visualize with barplots.  

8. Perform protein k-mer analysis (lengths 3–5).  
   - Identify top over- and under-represented k-mers.  
   - Compare k-mers between organisms to highlight differences.  

**Outputs:**  
- **Tables:** CDS counts, total coding DNA, mean/median CDS lengths, top k-mers.  
- **Plots:** CDS length distributions, DNA base frequencies, amino acid frequencies, codon usage, k-mer distributions.  

**Notes:**  
- Stop codons (`*`) are excluded from amino acid and k-mer analyses.  
- *M. hyopneumoniae* exhibits AT-rich genome and stronger codon bias.  
- Protein k-mer differences reflect genome evolution, codon usage, and protein composition.  

---

# Additional Notes

- All scripts are fully reproducible; knitting produces HTML or PDF reports.  
- Step-by-step comments are included in each RMarkdown file.  
- Repository is organized with separate folders for raw data, scripts, results, and reports.  
