# Phase 3 Project: Predicting H1N1 Vaccine Uptake

## Overview
This project uses machine learning classification models to predict whether an individual received the H1N1 influenza vaccine based on demographic information, health behaviors, and personal beliefs. The goal is to support public health stakeholders in understanding vaccination patterns and improving outreach strategies during future public health emergencies.

The analysis follows the full data science lifecycle, including data preparation, iterative modeling, evaluation using appropriate classification metrics, and actionable recommendations.

---

## Business and Data Understanding

### Stakeholder
Public health agencies and policymakers responsible for designing vaccination outreach and preparedness strategies.

### Business Problem
During public health emergencies, resources for vaccine distribution and public messaging are limited. Understanding which individuals are more likely or less likely to vaccinate enables targeted communication strategies that maximize vaccine uptake and reduce preventable illness.

### Dataset
The dataset comes from the **National 2009 H1N1 Flu Survey**, containing responses from 26,707 individuals. It includes:
- Demographic attributes
- Health conditions
- Behavioral responses
- Opinions about vaccines and risk

Although the dataset includes two vaccination outcomes (H1N1 and seasonal flu), this project focuses exclusively on **H1N1 vaccination**, as it best reflects behavior during pandemic conditions.

---

## Data Preparation

The dataset underwent careful preparation to ensure valid and unbiased modeling:

- **Data merging:** Feature and label datasets were merged using respondent identifiers.
- **Target selection:** H1N1 vaccination was selected as the binary classification target.
- **Class imbalance analysis:** Only ~21% of respondents received the vaccine, making accuracy an unreliable metric.
- **Missing data handling:**
  - Columns with extreme missingness (>45%) were removed.
  - Numeric features were imputed using the median.
  - Categorical features were imputed using the mode.
- **Categorical encoding:** One-hot encoding was applied with `drop_first=True` to prevent multicollinearity.
- **Data leakage prevention:** The target variable was removed from features prior to modeling.
- **Train-test split:** Data was split into 80% training and 20% testing sets using stratification to preserve class balance.

These steps ensured the dataset was clean, interpretable, and suitable for machine learning.

---

## Modeling

An iterative modeling approach was used to balance interpretability and performance:

### Models Built
1. **Baseline Model:** Logistic Regression  
   - Simple, fast, and interpretable
   - Serves as a performance benchmark

2. **Tuned Logistic Regression (Final Model)**  
   - Hyperparameters adjusted to improve performance
   - Maintains interpretability while improving predictive balance

3. **Alternative Model:** Random Forest  
   - Non-parametric model capable of capturing complex relationships
   - Used for comparison against simpler approaches

---

## Evaluation

### Primary Metric: F1-Score
Due to class imbalance, accuracy alone is misleading. The F1-score was prioritized because it balances:
- **Precision:** Avoids unnecessary outreach
- **Recall:** Maximizes identification of individuals likely to vaccinate

Evaluation was performed exclusively on the **test dataset**, ensuring realistic performance estimates.

### Key Findings
- The tuned Logistic Regression model achieved the best balance between precision and recall.
- The model performs well at identifying non-vaccinators but is more conservative when predicting vaccination.
- Features related to perceived vaccine effectiveness, risk perception, and doctor recommendations were among the most influential.

---

## Limitations

- Missing data required imputation, which may introduce bias.
- Self-reported survey responses may be inaccurate or influenced by recall bias.
- The dataset represents behaviors and attitudes from the 2009 pandemic, which may not generalize to future outbreaks.
- Some important predictors of vaccine uptake (such as healthcare access or cultural factors) are not included.
- Grid search was limited to a small parameter space due to computational constraints.


---

## Conclusion

This project demonstrates how classification models can support public health decision-making by identifying patterns in vaccination behavior. The final tuned Logistic Regression model provides interpretable insights while maintaining balanced predictive performance. These findings can inform targeted communication strategies, helping public health agencies allocate resources more effectively during future vaccination campaigns.

---



