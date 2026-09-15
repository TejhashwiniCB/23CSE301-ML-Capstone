# Algorithm Requirements by Track

## 1. Regression Track

| #   | Algorithm                         | Notes                                                                 |
|-----|-----------------------------------|-----------------------------------------------------------------------|
| 1.1 | Linear Regression                 | Baseline; interpret coefficients                                     |
| 1.2 | Ridge Regression                  | $L_2$ regularisation; tune alpha                                     |
| 1.3 | Lasso Regression                  | $L_1$ regularisation; observe feature sparsity                       |
| 1.4 | ElasticNet Regression             | Combined $L_1+L_2$; tune l1_ratio                                     |
| 1.5 | Polynomial Regression             | Apply `PolynomialFeatures` then Linear Regression; compare degrees   |
| 1.6 | Decision Tree Regressor           | Tune `max_depth`; show feature importance                            |
| 1.7 | Random Forest Regressor           | Ensemble baseline; tune `n_estimators`                               |
| 1.8 | Gradient Boosting Regressor       | `sklearn` GBM or XGBoost; tune `learning_rate`                       |
| 1.9 | Support Vector Regressor (SVR)    | Scale features first; tune C and `kernel`                            |
| 1.10 | K-Nearest Neighbors Regressor    | Tune k; discuss impact of scaling                                    |

- **Evaluation metrics(all mandatory) :** R2 score, RMSE, MAE, and 5-fold cross-validated R2 for the **two best-performing models.**

## 2. Classificatiion Track

| #    | Algorithm                          | Notes                                                     |
|------|------------------------------------|-----------------------------------------------------------|
| 2.1  | Logistic Regression                | Baseline classifier; interpret coefficients/odds          |
| 2.2  | K-Nearest Neighbors                | Tune k; discuss distance metrics                          |
| 2.3  | Naive Bayes (Gaussian)             | Discuss conditional independence assumption               |
| 2.4  | Decision Tree Classifier            | Tune `max_depth`; visualise the tree                      |
| 2.5  | Support Vector Machine (SVC)       | Tune C and `kernel`; scale features                       |
| 2.6  | Random Forest Classifier            | Feature importance; tune `n_estimators`                   |
| 2.7  | AdaBoost Classifier                 | Tune `n_estimators` and `learning_rate`                   |
| 2.8  | Gradient Boosting Classifier        | `sklearn` GBM or XGBoost/LightGBM                         |
| 2.9  | Bagging Classifier                  | Use Decision Tree as base estimator                       |
| 2.10 | MLP Classifier (Neural Network)     | Tune `hidden_layer_sizes` and `activation`                |

- **Evaluation metrics (all mandatory) :** Accuracy, Precision, Recall, F1-score (weighted), Confusion matrix, and ROC-AUC score.
- For multi-class problems use One-vs-Rest(OvR)for ROC-AUC.
- The **final Review 2** deliverable must include a single consolidated comparison table across all ten algorithms.

## 3. Clustering Track

Unlike regression and classification, **clustering has no labels during training**. Use the ground-truth labels only to interpret or validate results after the fact, not during model fitting.

| #    | Algorithm                          | Notes                                      |
|------|------------------------------------|--------------------------------------------|
| 3.1  | K-Means Clustering                 | Plot Elbow curve (inertia vs. k) to choose k |
| 3.2  | Agglomerative Hierarchical Clustering | Plot Dendrogram; compare linkage strategies |

- **Evaluation metrics (all mandatory):** Silhouette Score, Davies-Bouldin Index, and Calinski-Harabasz Index for all algorithms.
- Cluster visualisation via PCA (2 principal components) is **mandatory**; t-SNE visualisation is **encouraged.**
