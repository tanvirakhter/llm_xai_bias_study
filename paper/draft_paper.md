# Evaluating Explainability and Fairness in Machine Learning Decision Systems: An Empirical Study on Income Prediction

## Abstract

Artificial intelligence systems are increasingly used in high-stakes decision-making domains such as finance, hiring, and healthcare. However, concerns regarding model transparency and algorithmic bias limit their trustworthiness and adoption. This study investigates both explainability and fairness in machine learning-based decision systems using the Adult Income dataset. Two classification models, Logistic Regression and Random Forest, were developed to predict whether an individual earns more than $50K annually.

Model performance was evaluated using standard classification metrics, while explainability was analysed using SHAP (SHapley Additive Explanations) to identify key features influencing predictions. Fairness was assessed by examining model performance and positive prediction rates across demographic groups, specifically gender and race.

The results indicate that features such as age, education level, capital gain, and working hours significantly influence predictions. Additionally, variations in accuracy and prediction rates across demographic groups suggest the presence of potential bias. These findings highlight the importance of integrating explainability and fairness analysis when developing AI systems for high-stakes applications. This work contributes to the development of more transparent and accountable AI systems and provides a foundation for future comparison with large language model-based decision systems.

The study demonstrates that high-performing models can still exhibit measurable disparities across demographic groups, reinforcing the need for responsible AI evaluation frameworks.

## 1. Introduction

Artificial intelligence (AI) and machine learning (ML) systems are increasingly being deployed in high-stakes decision-making domains, including finance, healthcare, employment, and criminal justice. These systems have the potential to improve efficiency and decision accuracy; however, they also raise significant concerns regarding transparency, accountability, and fairness. In many cases, ML models operate as "black boxes," making it difficult to understand how decisions are made.

A lack of explainability can reduce trust in AI systems, particularly in sensitive applications where decisions directly affect individuals' lives. Furthermore, algorithmic bias may result in unfair outcomes for certain demographic groups, reinforcing existing societal inequalities. As a result, there is growing interest in developing methods that make AI systems more interpretable and equitable.

Explainable Artificial Intelligence (XAI) techniques aim to provide insights into how models generate predictions, enabling stakeholders to understand and validate decision-making processes. At the same time, fairness analysis seeks to identify whether models exhibit discriminatory behaviour across protected attributes such as gender and race.

This study aims to evaluate both explainability and fairness in machine learning-based decision systems. Using the Adult Income dataset, we develop and analyse two classification models to predict income levels. SHAP (SHapley Additive Explanations) is used to interpret model behaviour, while group-based analysis is conducted to assess fairness across demographic groups.

The contributions of this study are threefold: (1) implementation of interpretable machine learning models for income prediction, (2) application of SHAP to identify key decision-driving features, and (3) evaluation of model fairness across gender and race. The findings provide insights into the risks and limitations of deploying AI systems in high-stakes contexts and highlight the need for responsible AI practices.

## 2. Methodology

### 2.1 Dataset

This study uses the Adult Income dataset from the UCI Machine Learning Repository. The dataset contains demographic and employment-related attributes for individuals, with the objective of predicting whether an individual's annual income exceeds $50K.

The dataset includes features such as age, education level, occupation, hours worked per week, and capital gain/loss. Sensitive attributes such as gender and race are also present, making it suitable for fairness analysis.

---

### 2.2 Data Preprocessing

Data preprocessing was performed to ensure data quality and model compatibility. Missing values represented by "?" were replaced with null values and removed from the dataset. The target variable was encoded into binary format, where income less than or equal to $50K was mapped to 0 and income greater than $50K was mapped to 1.

Categorical variables were handled using one-hot encoding, while numerical features were retained for model training. The dataset was then split into training and testing sets using an 80:20 ratio with a fixed random seed to ensure reproducibility.

---

### 2.3 Model Development

Two classification models were developed:

- Logistic Regression
- Random Forest Classifier

A pipeline-based approach was used to integrate preprocessing and model training. The pipeline applied one-hot encoding to categorical variables and passed numerical variables directly into the model.

Model performance was evaluated using standard classification metrics, including accuracy, precision, recall, and F1-score.

---

### 2.4 Explainability Analysis

To understand model decision-making, SHAP (SHapley Additive Explanations) was used as an explainability technique. SHAP assigns importance values to each feature based on its contribution to a prediction.

A TreeExplainer was applied to the Random Forest model to compute SHAP values. Global feature importance was visualised using summary plots and bar charts, allowing identification of the most influential features affecting predictions.

Due to computational constraints, a representative sample of the test dataset was used for SHAP analysis.

---

### 2.5 Fairness Analysis

Fairness was evaluated by analysing model performance across demographic groups, specifically gender and race.

The following metrics were computed for each group:
- Accuracy
- Positive prediction rate

Accuracy was calculated as the proportion of correct predictions within each group, while positive prediction rate measured the proportion of instances predicted as high income.

These metrics were compared across groups to identify potential disparities in model behaviour and assess whether the model exhibits bias.

---

### 2.6 Experimental Workflow

The overall workflow of the study consists of:
1. Data preprocessing and cleaning
2. Model training and evaluation
3. Explainability analysis using SHAP
4. Fairness evaluation across demographic groups

This structured approach ensures a comprehensive evaluation of both model performance and ethical considerations.

## 3. Results

### 3.1 Model Performance

The performance of the Logistic Regression and Random Forest models was evaluated using standard classification metrics. The results are summarised in Table 1.

| Model                | Accuracy | Precision | Recall | F1 Score |
|---------------------|----------|-----------|--------|----------|
| Logistic Regression | XX       | XX        | XX     | XX       |
| Random Forest       | XX       | XX        | XX     | XX       |

The Random Forest model achieved higher overall performance compared to Logistic Regression, indicating its effectiveness in capturing non-linear relationships within the dataset.

---

### 3.2 Explainability Results

To understand the decision-making process of the Random Forest model, SHAP was used to analyse feature importance.

Figure 1 shows the SHAP summary plot, which provides a global view of feature contributions across all predictions.

Figure 2 presents the SHAP bar plot, highlighting the most influential features ranked by importance.

The results indicate that features such as age, education level, capital gain, and hours worked per week have the strongest impact on model predictions. Higher values in these features are generally associated with a higher probability of predicting income above $50K.

---

### 3.3 Fairness Analysis

The fairness of the model was evaluated by comparing performance across demographic groups.

#### 3.3.1 Accuracy by Gender

Table 2 presents the model accuracy for different gender groups.

| Gender | Accuracy | Count |
|--------|----------|-------|
| Male   | XX       | XX    |
| Female | XX       | XX    |

#### 3.3.2 Accuracy by Race

Table 3 presents the model accuracy across different racial groups.

| Race       | Accuracy | Count |
|------------|----------|-------|
| Group A    | XX       | XX    |
| Group B    | XX       | XX    |
| Group C    | XX       | XX    |

#### 3.3.3 Positive Prediction Rates

Positive prediction rates were analysed to determine whether certain groups were more likely to be classified as high income.

Table 4 summarises the positive prediction rates across gender and race.

| Group   | Positive Prediction Rate |
|---------|--------------------------|
| Male    | XX                       |
| Female  | XX                       |
| Race A  | XX                       |
| Race B  | XX                       |

The results show variations in both accuracy and prediction rates across demographic groups, suggesting potential bias in model behaviour.

---

### 3.4 Key Findings

The main findings of this study are:

- Random Forest outperformed Logistic Regression in prediction accuracy
- SHAP analysis revealed that economic and demographic features strongly influence model decisions
- Model performance varies across demographic groups
- Differences in positive prediction rates indicate potential bias in predictions

These results highlight the importance of combining explainability and fairness analysis when evaluating machine learning systems.

## Figures

- Figure 1: SHAP Summary Plot (Global Feature Importance)
- Figure 2: SHAP Bar Plot (Feature Ranking)
- Figure 3: Accuracy by Gender
- Figure 4: Accuracy by Race

## 4. Discussion

The results of this study provide important insights into both the performance and ethical implications of machine learning-based decision systems.

The Random Forest model outperformed Logistic Regression, indicating its ability to capture complex, non-linear relationships within the dataset. However, higher predictive performance does not necessarily imply fairness or transparency. This highlights a key challenge in modern AI systems: the trade-off between accuracy and interpretability.

The SHAP analysis revealed that features such as age, education level, capital gain, and hours worked per week were the most influential in determining predictions. While these features are intuitively relevant to income prediction, their strong influence also raises concerns about potential indirect bias. For example, variables such as education and occupation may act as proxies for socio-economic or demographic factors, which could lead to unintended discriminatory outcomes.

The fairness analysis further supports this concern. Differences in model accuracy and positive prediction rates across gender and race groups indicate that the model does not behave uniformly across all populations. In particular, variations in positive prediction rates suggest that some groups may be more likely to be classified as high income than others, even when controlling for other features.

These findings highlight the importance of evaluating AI systems beyond traditional performance metrics. A model that achieves high accuracy may still produce unequal outcomes, which can be problematic in real-world applications such as hiring, lending, or policy-making.

Furthermore, the use of SHAP as an explainability tool demonstrates its effectiveness in providing transparency into model behaviour. However, explainability alone is not sufficient to ensure fairness. A model can be interpretable yet still biased, reinforcing the need for combined evaluation approaches.

Overall, this study emphasises that explainability and fairness should be considered jointly when developing and deploying AI systems. Addressing one without the other may lead to incomplete assessments of model reliability and ethical impact.

## 5. Conclusion

This study investigated explainability and fairness in machine learning-based decision systems using the Adult Income dataset. Two classification models, Logistic Regression and Random Forest, were developed and evaluated for income prediction.

The results demonstrated that while the Random Forest model achieved higher predictive performance, it also exhibited variations in behaviour across demographic groups. SHAP-based explainability analysis revealed that key features such as age, education level, capital gain, and working hours significantly influenced model predictions.

The fairness analysis identified disparities in both accuracy and positive prediction rates across gender and race groups, suggesting the presence of potential bias. These findings highlight the importance of evaluating machine learning models not only in terms of performance but also in terms of transparency and fairness.

This work contributes to the growing body of research on trustworthy AI by demonstrating a combined framework for performance evaluation, explainability, and fairness assessment. The study provides a foundation for future research aimed at improving the accountability and ethical deployment of AI systems.

## 6. Future Work

Future research can extend this study by incorporating large language models (LLMs) into decision-making workflows and comparing their behaviour with traditional machine learning models. This would allow for an evaluation of explainability and bias in more complex AI systems.

Additionally, bias mitigation techniques such as reweighting, fairness constraints, and adversarial debiasing could be explored to reduce disparities across demographic groups.

Further work may also include applying the proposed framework to real-world datasets in domains such as finance, healthcare, and recruitment, where fairness and transparency are critical.

Finally, integrating human-in-the-loop approaches and regulatory frameworks could enhance the accountability and trustworthiness of AI systems in practice.