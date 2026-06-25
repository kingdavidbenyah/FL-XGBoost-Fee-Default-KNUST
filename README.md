# FL-XGBoost: Student Fee Default Prediction — KNUST

## Overview
This repository contains the code and resources for the research study:

**"FL-XGBoost: A Focal-Loss Engineered Gradient Boosting Model for Early 
Prediction of Student Fee Default in Ghanaian Public Universities"**

A machine learning study conducted at Kwame Nkrumah University of Science 
and Technology (KNUST), Kumasi, Ghana.

## What This Study Does
Student fee default is a major operational problem in Ghanaian public 
universities. Finance offices currently identify defaulters only after 
deadlines pass — too late to intervene. This study builds FL-XGBoost, 
an engineered XGBoost model that predicts which students are likely to 
default on fee payments *before* the deadline, giving finance 
administrators time to act.

## Model Engineering
- **Base model:** XGBoost (Chen & Guestrin, 2016)
- **Engineering operation:** [F] FABRICATE — custom focal-loss objective 
  function replacing default cross-entropy loss
- **Why focal loss:** Fee defaulters are a minority class. Standard 
  XGBoost ignores them. Focal loss forces the model to focus on them.
- **Engineered model name:** FL-XGBoost

## Baselines Compared
| Model | Type |
|---|---|
| Standard XGBoost | Scientific control (unengineered) |
| LightGBM | Gradient boosting alternative |
| Random Forest | Tree ensemble baseline |

## Dataset
- **Primary:** KNUST Student Fee Payment Records (2021–2024), collected 
  under CHRPE ethics clearance
- **Supplementary:** Lending Club Loan Default Dataset (pre-validation only)
- **Ethics:** KNUST Committee on Human Research, Publications and Ethics 
  (CHRPE) — Reference No: [to be updated upon approval]

## Tech Stack
See `requirements.txt` for full library versions.

- Python 3.10
- XGBoost 1.7.6
- SHAP 0.43.0
- scikit-learn 1.3.0
- Google Colab Pro (training environment)

## Evaluation Metrics
- AUC-PR (primary — chosen for class imbalance)
- AUC-ROC, Macro F1, Precision, Recall
- Wilcoxon signed-rank test for statistical significance

## Repository Structure
