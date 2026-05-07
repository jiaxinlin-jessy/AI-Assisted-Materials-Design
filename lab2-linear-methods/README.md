# Lab 2 — Linear Methods & Classification in Materials Science

**Lecture:** 5 | **Score:** Part of overall 98/100

## Overview

This lab applies classical machine learning to real materials data — both computational (Materials Project) and experimental. It covers the full workflow from raw data to trained and evaluated models.

## Tasks

| Question | Description | Points |
|----------|-------------|--------|
| Q1 | Exploratory data analysis on halide/iodide materials | 7 |
| Q2 | Data cleaning, deduplication, and composition-based feature engineering (33-dim design matrix) | 24 |
| Q3 | Regression (Linear, Ridge, LASSO) and classification (LDA, QDA, Logistic Regression) | 39 |
| Q4 | Image-based clustering of Pd/Ru nanocatalyst EDX micrograph using K-means and DBSCAN | 30 |

## Key results

- **Feature matrix:** 33 features per material (composition-averaged mean / max / min of 11 element properties)
- **Best regression model:** LASSO with optimised α — outperforms plain linear regression due to feature sparsity in halide/iodide space
- **Classification:** LDA achieves highest accuracy for metal vs. non-metal prediction; pure composition features have inherent limitations (cannot distinguish polymorphs)
- **Clustering:** DBSCAN outperforms K-means for the nanocatalyst image — handles irregular cluster shapes and identifies noise pixels as background more naturally than a fixed-K approach

## Data files

Place the following files in the `data/` directory before running:

| File | Description |
|------|-------------|
| `data2022.csv` | Materials Project halide/iodide subset |
| `element_properties.csv` | 11 elemental features used for featurisation |
| `catalyst.png` | EDX micrograph of Pd/Ru bimetallic nanoparticles |

## Running

```bash
jupyter notebook AIMat-lab2-Jiaxin-LIN.ipynb
```

No API key required for this lab.
