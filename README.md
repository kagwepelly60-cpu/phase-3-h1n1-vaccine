# Predicting H1N1 Vaccine Uptake

## Overview
This project uses machine learning classification models to predict whether an individual received the H1N1 vaccine during the 2009 pandemic. The goal is to support public health decision-making by identifying patterns associated with vaccine hesitancy and uptake, enabling more targeted and effective vaccination campaigns.

---

## Repository Structure
├── README.md # Project overview and findings
├── h1n1_analysis 2 ipynb.ipynb # Full technical analysis notebook
├── Predicting H1N1 Vaccine Uptake.pdf # Non-technical presentation
├── training_set_features.csv # Survey features dataset
└── training_set_labels.csv # Vaccination outcomes dataset

---

## Business and Data Understanding

### Stakeholder
**Primary Stakeholders:**  
Public health agencies (e.g., CDC, Ministry of Health, county health departments)

**Secondary Stakeholders:**  
Healthcare providers, policymakers, and public health communication teams

**Stakeholder Needs:**
- Identify vaccine-hesitant populations
- Understand barriers to vaccination
- Target outreach campaigns effectively
- Allocate limited public health resources
- Improve preparedness for future pandemics

---

### Dataset
The dataset comes from the **2009 National H1N1 Flu Survey** and includes:
- 26,707 respondents
- Demographic information
- Health behaviors
- Attitudes toward vaccines
- Target variable: **H1N1 vaccination status (Yes/No)**

The dataset is highly imbalanced:
- 79% did not receive the vaccine
- 21% did receive the vaccine

---

### Why This Dataset?
This dataset was chosen because:
1. It represents a real-world public health classification problem
2. It includes actionable behavioral and attitudinal features
3. It reflects realistic class imbalance seen in vaccination campaigns
4. Insights can directly inform vaccination strategies
5. It is publicly available and well-documented

---

## Data Preparation
Key preparation steps included:
- Merging survey responses with vaccination outcomes
- Dropping features with more than 45% missing values
- Imputing remaining missing values (median for numeric, mode for categorical)
- One-hot encoding categorical variables
- Performing an 80/20 stratified train-test split to prevent data leakage

The final dataset contained **50 features** ready for modeling.

---

## Modeling
An iterative modeling approach was used:

1. **Baseline Logistic Regression**  
   - Simple, interpretable benchmark model

2. **Tuned Logistic Regression**  
   - Hyperparameter tuning (regularization strength)
   - Optimized for F1-score due to class imbalance

3. **Random Forest**  
   - Nonparametric ensemble model
   - Used to capture non-linear relationships and compare performance

---

## Evaluation

### Final Model: Tuned Logistic Regression
- **F1-Score:** 0.520
- **Accuracy:** 83.4%
- **Precision:** 67.4%
- **Recall:** 42.4%

**Why F1-Score?**  
Accuracy alone is misleading due to class imbalance. F1-score balances precision and recall, making it more appropriate for identifying vaccine-hesitant populations.

---

### Feature Importance
Top predictors of H1N1 vaccination:
1. Doctor recommendation (H1N1)
2. Perceived risk of H1N1
3. Belief in vaccine effectiveness

**Key Insight:**  
Vaccination decisions are driven more by medical advice and personal beliefs than by demographic factors.

---

## Recommendations
Based on model findings, public health agencies should:

1. **Strengthen Doctor Engagement**
   - Train providers in vaccine communication
   - Encourage proactive vaccine recommendations

2. **Address Risk Perception**
   - Design messaging emphasizing disease risk
   - Highlight vaccine effectiveness

3. **Target Vaccine-Hesitant Groups**
   - Use model predictions to focus outreach
   - Deploy mobile clinics and community programs
   - Allocate resources where impact will be highest

---

## Limitations
- Self-reported survey data may contain bias
- Missing data required imputation
- Dataset reflects behaviors from 2009 and may not fully generalize
- Some social and cultural factors are not captured

---

## Conclusion
This project demonstrates how machine learning classification can support public health decision-making. By identifying vaccine-hesitant populations and key drivers of vaccination behavior, the model provides actionable insights that can improve vaccination campaign effectiveness and inform future pandemic responses.
