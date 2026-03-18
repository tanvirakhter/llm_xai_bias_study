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

## 🔍 Day 3: Explainability (SHAP)

- Applied **SHAP (SHapley Additive Explanations)**
- Analysed feature importance globally

### Key Insights:
- Strong predictors:
  - Age
  - Education level
  - Capital gain
  - Hours worked per week

### Outputs:
- SHAP Summary Plot → `figures/shap_summary.png`
- SHAP Bar Plot → `figures/shap_bar.png`


## Day 4: Bias & Fairness Analysis

Evaluated model behaviour across demographic groups:

### Groups Analysed:
- Gender (`sex`)
- Race (`race`)

### Metrics:
- Accuracy per group
- Positive prediction rate per group

### Key Findings:
- Model performance varies across demographic groups
- Differences in prediction rates suggest potential bias
- Highlights importance of fairness in high-stakes AI systems

### Outputs:
- `results/gender_bias.csv`
- `results/race_bias.csv`
- `results/gender_positive_rate.csv`
- `results/race_positive_rate.csv`

---

## 👨‍💻 Author
**Tanvir Akhter Shakib**  
MSc Data Science & Analytics
BSc Computer Science (Software Engineerring)  
Brunel University of London  

---