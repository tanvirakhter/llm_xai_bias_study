# Explainable & Auditable AI for High-Stakes Decision Systems

## Project Overview
This project investigates the explainability and bias of AI systems used in high-stakes decision-making scenarios. The study compares traditional machine learning models with Large Language Model (LLM)-based decision systems.

## Objective
To evaluate:
- Model explainability (SHAP vs LLM explanations)
- Bias across sensitive attributes (gender, race)
- Trustworthiness of LLM-based decision systems

## Dataset
- Adult Income Dataset (UCI Machine Learning Repository)
- Predicts whether income exceeds $50K/year

## Project Structure
```text
llm_xai_bias_study/
├── data/                  # raw and cleaned datasets
├── notebooks/             # Jupyter notebooks
├── figures/               # plots and visualisations
├── results/               # model outputs and evaluation tables
├── paper/                 # paper drafts and notes
├── README.md
└── .gitignore
```

## Day 1 Progress
- Dataset loaded and structured
- Missing values handled (`?` → NaN)
- Rows with missing values removed
- Target variable (`income`) encoded (0/1)
- Clean dataset saved for modelling

## Day 2 Progress
Completed:
- feature and target preparation
- categorical encoding and numerical scaling
- train-test split
- Logistic Regression baseline model
- Random Forest baseline model
- evaluation using accuracy, precision, recall, and F1-score
- baseline results saved to the results folder