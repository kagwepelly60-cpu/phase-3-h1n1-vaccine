# Phase 3 H1N1 Vaccine
# Phase 3 Project: Predicting H1N1 Vaccine Uptake

## Overview
This project uses supervised machine learning classification to predict whether an individual received the H1N1 influenza vaccine. The analysis follows the full data science workflow, including problem framing, data preparation, model development, evaluation, and interpretation. The purpose of the project is to demonstrate how predictive modeling can support public health decision-making by identifying patterns associated with vaccine uptake.

---

## Business and Data Understanding
The primary stakeholders for this project are public health agencies and policymakers responsible for vaccination campaigns. During public health emergencies, such as influenza pandemics, understanding which groups are less likely to get vaccinated is critical for designing effective outreach strategies and allocating limited resources.

The dataset used in this analysis comes from the 2009 H1N1 Flu Survey conducted in the United States. It includes demographic characteristics, health behaviors, medical history, and attitudes toward vaccines. The target variable indicates whether an individual received the H1N1 vaccine, making this a classification problem. The dataset is imbalanced, with a majority of individuals not receiving the vaccine, which has important implications for model evaluation.

---

## Modeling
An iterative modeling approach was used to solve this classification problem. First, a baseline logistic regression model was built to establish a simple and interpretable benchmark. This model allowed for an initial assessment of predictive performance and provided insight into how individual features relate to vaccination outcomes.

The baseline model was then improved through hyperparameter tuning and the use of a nonparametric ensemble model. Ensemble methods were explored to capture nonlinear relationships and interactions between features that could not be modeled effectively by a purely linear approach. Each model iteration was evaluated and compared to justify progression to a more complex model.

---

## Evaluation
Due to the class imbalance in the target variable, accuracy was not an appropriate primary evaluation metric. Instead, the F1-score was prioritized because it balances precision and recall and provides a more meaningful measure of performance for imbalanced classification problems.

Model evaluation focused on performance on the test dataset to ensure realistic estimates of generalization. The final model demonstrated strong performance in identifying individuals who did not receive the vaccine, while performance for identifying vaccinated individuals was more limited. This outcome reflects both the imbalance in the dataset and the inherent difficulty of predicting minority classes in public health data.

---

## Conclusion
The results of this project indicate that vaccination behavior is influenced by a combination of demographic factors, health behaviors, and beliefs about vaccines. While the final model shows useful predictive capability, its limitations—particularly in recall for vaccinated individuals—must be considered before applying it in a real-world setting.

From a business perspective, this model is most useful as a decision-support tool rather than a definitive predictor. Public health agencies could use insights from the model to inform targeted education and outreach efforts. Future work could explore additional feature engineering, alternative ensemble models, or techniques specifically designed to address class imbalance.
