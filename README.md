# AI-Assisted Materials Design — Course Labs

> **Course:** AI-Assisted Materials Design (AI辅助材料设计)  
> **Institution:** School of Materials, Sun Yat-sen University (SYSU)  
> **Instructor:** Prof. Xiangguo Li  
> **Author:** Jiaxin Lin (林嘉馨) — **Top of class, 98/100**

This repository contains my solutions to all three lab assignments from the course *AI-Assisted Materials Design* (third-year elective, School of Materials, SYSU). Each lab is a self-contained Jupyter Notebook combining Python code, analysis, and materials-science discussion.

---

## Labs overview

| Lab | Topic | Key tools |
|-----|-------|-----------|
| [Lab 1](./lab1-data-processing/) | Data processing — Materials Project & OQMD | `pymatgen`, `pandas`, `scipy` |
| [Lab 2](./lab2-linear-methods/) | Linear methods & clustering | `scikit-learn`, `pymatgen`, `matplotlib` |
| [Lab 3](./lab3-final-project/) | End-to-end ML — cohesive energy prediction | `scikit-learn`, `pymatgen`, neural networks |

---

## Environment setup

All labs share a single conda environment. To reproduce:

```bash
# 1. Clone the repo
git clone https://github.com/<your-username>/AI-Assisted-Materials-Design.git
cd AI-Assisted-Materials-Design

# 2. Create and activate the environment
conda env create -f environment.yml
conda activate AIMat

# 3. Set your Materials Project API key (required for Lab 1)
#    Get a free key at: https://next.materialsproject.org/api
export MP_API_KEY="your_api_key_here"

# 4. Launch Jupyter
jupyter notebook
```

> **Note on Lab 1 API key:** The Materials Project API key is read from the environment variable `MP_API_KEY`. Never hard-code your key in a notebook before pushing to a public repository.

---

## Repository structure

```
AI-Assisted-Materials-Design/
├── README.md
├── environment.yml
├── .gitignore
│
├── lab1-data-processing/
│   ├── AIMat-lab1-Jiaxin-LIN.ipynb   # Full solution notebook
│   ├── README.md
│   └── data/                          # Downloaded automatically via API / URL
│
├── lab2-linear-methods/
│   ├── AIMat-lab2-Jiaxin-LIN.ipynb
│   ├── README.md
│   └── data/
│       ├── data2022.csv
│       ├── element_properties.csv
│       └── catalyst.png
│
└── lab3-final-project/
    ├── AIMat-lab3-Jiaxin-LIN.ipynb
    ├── README.md
    └── data/
        ├── train.csv
        ├── test.csv
        ├── predict.csv
        ├── element_properties.csv
        ├── liner_model_predict.csv    # Submitted predictions — linear model
        ├── tree_model_predict.csv     # Submitted predictions — tree model
        └── nn_model_predict.csv       # Submitted predictions — neural network
```

---

## Lab summaries

### Lab 1 — Data Processing (Lecture 3)
Querying and comparing two public materials databases:
- **Q1:** Retrieve all ABO₃ compounds from the Materials Project via `pymatgen`, compute statistics, visualise formation energy and band gap distributions.
- **Q2:** Download and clean the OQMD perovskite dataset from Figshare.
- **Q3:** Cross-validate both datasets; Welch's t-test shows MP formation energies are significantly lower than OQMD (Δ ≈ −0.35 eV/atom, p = 9.6 × 10⁻²⁷), attributed to differences in DFT functionals and reference energies.

### Lab 2 — Linear Methods & Classification (Lecture 5)
Machine learning on halide/iodide materials from the Materials Project:
- **Q1:** Exploratory data analysis — element frequency, dataset statistics.
- **Q2:** Feature engineering — composition-averaged element properties (mean, max, min) → 33-dimensional design matrix.
- **Q3:** Regression (Linear, Ridge, LASSO) and classification (LDA, QDA, Logistic Regression) for formation energy and metallicity prediction.
- **Q4:** Image-based clustering of Pd/Ru bimetallic nanocatalysts with K-means and DBSCAN.

### Lab 3 — Final Project (Lecture 8)
Predicting cohesive energy per atom (Eᶜ) from the MatPES r2SCAN dataset (~400k DFT structures):
- Composition-based feature engineering with extended element properties from `pymatgen`.
- Three model families: **Linear (Ridge/LASSO)**, **Gradient Boosted Trees (HistGradientBoosting)**, **Neural Network (MLPRegressor)**.
- Full pipeline: cross-validation, hyperparameter tuning, permutation importance analysis, blind prediction set submission.

---

## Citation / acknowledgement

If you find this repository useful for learning, feel free to reference it. Please do not submit any part of this work as your own for academic assessment.
