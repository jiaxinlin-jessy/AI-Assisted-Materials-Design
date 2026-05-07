# Lab 1 — Applying Python to Materials Data Processing

**Lecture:** 3 | **Score:** Part of overall 98/100

## Overview

This lab introduces working with two major public materials databases using Python:

1. **Materials Project** — queried via `pymatgen` and the MP REST API
2. **OQMD (Open Quantum Materials Database)** — accessed through a Figshare CSV export

The lab covers data retrieval, cleaning, statistical analysis, and cross-database comparison.

## Tasks

| Question | Description | Points |
|----------|-------------|--------|
| Q1 | Query ABO₃ compounds from Materials Project; analyse stability and electronic properties | 38 |
| Q2 | Download and clean the OQMD perovskite dataset from Figshare | 30 |
| Q3 | Compare formation energies across both databases using hypothesis testing | 32 |

## Key results

- **2672** ABO₃ entries found in Materials Project (across **≈ 760** unique formulas)
- **23.6%** of compounds are experimentally synthesised (non-theoretical)
- Welch t-test: MP formation energies are significantly more negative than OQMD (p = 9.6 × 10⁻²⁷), consistent with DFT functional differences (PBE+U vs. different reference states in OQMD)

## Data

Lab 1 does **not** require local data files. Data is retrieved at runtime:
- **Q1:** via the Materials Project API (requires `MP_API_KEY` environment variable)
- **Q2:** downloaded automatically from `https://ndownloader.figshare.com/files/9158587`

## Running

```bash
# Set your MP API key first
export MP_API_KEY="your_key_here"

jupyter notebook AIMat-lab1-Jiaxin-LIN.ipynb
```

> The notebook will download ~2700 records from the MP API on first run (takes ~30 seconds depending on connection speed).
