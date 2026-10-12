# Classification Track

## Dataset Selection 

### The following criteria were used while comparing potential datasets :

| Criterion | Requirement |
|---|---|
| Class Balance | Moderate imbalance |
| Number of Samples | Large enough for meaningful comparison |
| Number of Features | Sufficient predictive features |
| Feature Type | Numerical / easily preprocessable |
| Target Variable | Clearly defined fraud/non-fraud label |
| Dataset Size | Computationally manageable |
| Algorithm Compatibility | Must support all 10 classifiers |
| Evaluation | Must support all required classification metrics |

### Several fraud-detection datasets were considered before finalizing the dataset :

| Dataset | Approx. Samples | Approx. Features | Fraud Distribution | Decision |
|---|---:|---:|---|---|
| ULB Credit Card Fraud Dataset | 284,807 | 30 | ~0.17% fraud | ❌ Rejected |
| IEEE-CIS Fraud Detection | ~590,000 | ~871 | ~3.5% fraud | ❌ Rejected |
| PaySim | ~6.3 million | ~10+ | Highly imbalanced | ❌ Rejected |
| Credit Card Fraud Detection Dataset 2023 | ~568,630 | ~30 | ~50:50 | ❌ Rejected |
| Automobile Insurance Claims Fraud Dataset | 1,000 | ~39 | ~75:25 | ✅ Selected |

**Finalized Dataset Link :** [Automobile Insurance Claims Fraud Dataset](https://www.kaggle.com/datasets/mexwell/insurance-claims)

# Insurance Claim Fraud Detection

## 1. Project Overview

This project develops a machine learning classification pipeline to predict whether an insurance claim is fraudulent or legitimate.

The classification track is part of the **23CSE301 Machine Learning Capstone Project (Academic Year 2026–27)**. It covers dataset exploration, preprocessing, feature engineering, model training, hyperparameter tuning, evaluation, and comparison of classification algorithms.

## 2. Problem Statement

Insurance fraud can cause financial losses for insurance companies. The objective of this project is to build and evaluate machine learning models that classify insurance claims as fraudulent or non-fraudulent based on the available claim, policy, customer, incident, and vehicle information.

**Target variable:** `fraud_reported`

- `Y` — Fraud reported
- `N` — Non-fraudulent claim

The goal is to compare multiple classification algorithms and identify a suitable model based on its evaluation metrics.

## 3. Dataset Description

The project uses an insurance claims dataset stored as `insurance_claims.csv`.

The dataset contains numerical and categorical attributes related to insurance policies, customers, vehicles, incidents, and claim amounts.

Examples of features include:

- Customer information: age and months as a customer.
- Policy information: annual premium, deductible, and policy details.
- Incident information: incident type, severity, and time-related attributes.
- Claim information: injury, property damage, vehicle damage, and claim amounts.
- Vehicle information: vehicle year and other vehicle-related attributes.

The target column is `fraud_reported`.

The notebook examines the dataset shape, data types, missing values, duplicate records, feature distributions, target distribution, correlations, and feature-target relationships.

## 4. Data Preprocessing and Feature Engineering

The following preprocessing steps are used:

- **Missing values:** Numerical features are imputed using the median, while categorical features are imputed using the most frequent category.
- **Categorical encoding:** One-Hot Encoding converts categorical variables into numerical representations. Unknown categories are handled using `handle_unknown="ignore"`.
- **Feature scaling:** StandardScaler standardizes numerical features.
- **Train-test split:** The dataset is divided into 80% training data and 20% testing data using stratified sampling and `random_state=42`.
- **Data leakage prevention:** Preprocessing is performed within scikit-learn pipelines, which fit the preprocessing transformations on training data and apply them to the test data.

### Engineered Features

**1. Claim-to-Premium Ratio (`claim_premium_ratio`)**

Calculated as:

`total_claim_amount / policy_annual_premium`

This feature represents the claim amount relative to the annual premium and may help identify useful patterns that are not captured by either variable alone.

**2. Vehicle Age (`vehicle_age`)**

Calculated as:

`incident_year - auto_year`

This feature represents the age of the vehicle at the time of the incident and may provide additional information relevant to claim classification.

The completely empty `_c39` column is removed because it does not contain useful observed information.

## 5. Classification Algorithms

The project evaluates ten classification algorithms.

### Part A - Review 1

1. **Logistic Regression:** Baseline classification model that estimates class probabilities.
2. **K-Nearest Neighbors (KNN):** Classifies observations using their nearest neighbors.
3. **Gaussian Naive Bayes:** Uses Bayes' theorem with a conditional independence assumption and Gaussian feature distributions.
4. **Decision Tree Classifier:** Learns decision rules through recursive feature-based splits.
5. **Support Vector Machine (SVC):** Learns a decision boundary to distinguish between classes.

### Part B - Review 2

6. **Random Forest Classifier:** Combines multiple decision trees and examines feature importance.
7. **AdaBoost Classifier:** Sequentially combines weak learners, focusing on observations that are difficult to classify.
8. **Gradient Boosting Classifier:** Builds successive trees to improve the ensemble's predictions.
9. **Bagging Classifier:** Combines predictions from bootstrap-trained decision trees.
10. **MLP Classifier:** A feed-forward neural network that learns nonlinear relationships between features and the target.

## 6. Evaluation Metrics

The classification models are evaluated using the following metrics:

- **Accuracy:** Proportion of all observations classified correctly.
- **Precision (weighted):** Weighted measure of the proportion of positive predictions that are correct.
- **Recall (weighted):** Weighted measure of the proportion of actual instances correctly identified.
- **Weighted F1-score:** Weighted harmonic mean of precision and recall.
- **ROC-AUC:** Measures the ability of a model to distinguish between the target classes.
- **Confusion Matrix:** Displays true positives, true negatives, false positives, and false negatives.

The models are compared using the same held-out test set. Five-fold cross-validation is also performed for the two best-performing models.


## 7. AI Assistance and Academic Integrity

- Generative AI (ChatGPT) was used minimally for code scaffolding and debugging assistance. 

- The project workflow, dataset exploration, EDA visualisations, preprocessing decisions, feature engineering, model experimentation, evaluation, and interpretation of results were carried out by the project team.
    
- All generated code was reviewed and tested before use.
