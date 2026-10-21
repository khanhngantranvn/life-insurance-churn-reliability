# Leakage-Aware Life Insurance Churn Analytics

Reproducible research on data leakage, predictive model reliability, group-aware validation, and exploratory monetary segmentation in life insurance.

## Overview

This repository contains the computational materials for the research paper:

**Leakage-Aware Evaluation of Life Insurance Churn Prediction: Data Auditing, Group-Aware Validation, and Monetary Segmentation**

The study investigates whether apparently perfect churn prediction performance remains reliable after auditing suspicious predictors and repeated feature vectors.

The research uses 200,000 records from a publicly available life insurance dataset.

## Key Findings

- **Suspected outcome proxy:** BMI deterministically separates the churn labels in the observed dataset.
- **Predictor redundancy:** Removing BMI leaves 1,769 unique predictor vectors, with substantial feature-vector repetition.
- **Predictive validation:** AUC-ROC decreases from 1.000 to approximately 0.500 after BMI exclusion and group-aware evaluation.
- **Controlled ablation:** Additional experiments indicate that BMI inclusion dominates the observed performance difference.
- **Information analysis:** The remaining predictors provide limited empirical information about churn.
- **Monetary segmentation:** K-means reproduces a simple separation of existing premium categories without demonstrating retention effectiveness.

These findings are specific to the evaluated dataset and protocols. The results do not establish confirmed temporal leakage or imply that life insurance churn is inherently unpredictable.

## Repository Structure

```text
life-insurance-churn-reliability/
├── README.md
├── churn_paper_reproducibility_figures.ipynb
├── extensions/
│   ├── thesis_extensions_AB_C.ipynb
│   ├── requirements.txt
│   ├── tables/
│   └── figures/
└── demo/
    ├── app.py
    ├── requirements.txt
    ├── preflight.py
    ├── assets/
    └── .streamlit/
```

## Dataset

Source: [Customer Churn Dataset for Life Insurance Industry (Kaggle)](https://www.kaggle.com/datasets/usmanfarid/customer-churn-dataset-for-life-insurance-industry)

Download `randomdata.csv` from Kaggle and place it alongside the notebook being executed.

The original dataset is not redistributed in this repository.

## Reproducing the Experiments

**Core experiments**

Open `churn_paper_reproducibility_figures.ipynb` using Jupyter Notebook or Google Colab, provide the original CSV, and run the cells.

**Thesis extensions**

Open `extensions/thesis_extensions_AB_C.ipynb` and run the independent experiments using the same dataset.

The extensions include:

- A: Controlled Ablation Study
- B: Predictive Information and Label Ambiguity
- C: Robustness and Statistical Reliability

Precomputed experimental results and figures are available in `extensions/tables/` and `extensions/figures/`.

## Streamlit Dashboard

An interactive dashboard is provided to demonstrate the research findings.

To run locally, open the `demo/` directory and execute:

```bash
python -m pip install -r requirements.txt
python preflight.py
python -m streamlit run app.py
```

The dashboard uses precomputed research outputs and does not retrain models or generate validated individual churn predictions.

## Research Limitations

The dataset does not establish independent customer identities, feature availability timestamps, or intervention outcomes. The observed BMI relationship is treated as a suspected outcome proxy rather than confirmed data leakage.

Monetary segmentation is exploratory and does not establish customer lifetime value, retention uplift, or profitability improvements.

## Academic Use

This repository is intended for research transparency, reproducibility, and academic demonstration.

**Institution:** University of Economics Ho Chi Minh City (UEH), Vietnam.

**Data source:** Public Kaggle dataset linked above.
