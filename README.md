[NHANES Environmental Chemical Mixtures and Depression Risk Prediction.md](https://github.com/user-attachments/files/21542006/NHANES.Environmental.Chemical.Mixtures.and.Depression.Risk.Prediction.md)
# NHANES Environmental Chemical Mixtures and Depression Risk Prediction

This project uses NHANES 2011–2016 data to develop interpretable machine learning models that predict the risk of depression based on exposure to multiple environmental chemicals. The workflow includes feature selection, model training, performance evaluation, and visualization.

## 1. Data Source

- Dataset: NHANES (2011–2016 cycles)
- Outcome: Depression status based on PHQ-9 score (binary: ≥10 vs <10)
- Predictors: 83 environmental chemical biomarkers, demographic and lab variables
- Design: Weighted cross-sectional analysis using survey design

## 2. Workflow

### Feature Selection

- Method: Recursive Feature Elimination (RFE) with Random Forest
- Cross-validation: 5-fold CV
- Selected features include: Poverty, folic acid, selenium (Se), uric acid (UA), creatinine (CRE)

### Model Training

Classifiers trained with repeated cross-validation:

- Logistic Regression (GLM)
- Random Forest (RF)
- Support Vector Machine (SVM)
- XGBoost
- Gradient Boosting Machine (GBM)
- Multilayer Perceptron (MLP)
- Neural Network (nnet)
- Gaussian Process
- Naive Bayes
- k-Nearest Neighbors (KNN)
- AdaBoost.M1
- C5.0 Decision Tree

### Model Evaluation

- Metrics: Area Under ROC Curve (AUC), accuracy, sensitivity, specificity, F1-score, 95% CI
- Tools: Confusion matrix, ROC curve, threshold optimization (Youden index)

## 3. Results Summary

- Selected variables: Poverty, folic acid, Se, UA, CRE
- Top-performing models on training set:
  - Random Forest: AUC = 0.987
  - XGBoost: AUC = 0.873
  - Naive Bayes: AUC = 0.833
- Top-performing models on test set:
  - XGBoost: AUC = 0.733
  - Naive Bayes: AUC = 0.672
  - Logistic Regression: AUC = 0.627

## 4. Project Structure

project-root/
 ├── code/
 │   ├── 01_rfe_feature_selection.R
 │   ├── 02_model_training.R
 │   └── 03_model_evaluation.R
 ├── data/                    # Not uploaded due to NHANES restrictions
 ├── figures/                 # Output plots (ROC, confusion matrix)
 ├── reproducibility-checklist.pdf
 └── README.md

## 5. Environment and Packages

- R version: 4.3+
- Key packages:
  - `caret`
  - `pROC`
  - `ggplot2`
  - `xgboost`
  - `doParallel`
  - `e1071`, `naivebayes`, `kknn`, `gbm`, `nnet`

## 6. Reproducibility

All scripts are written in R using the `caret` framework and support parallel computing. The entire analysis is reproducible with the provided scripts under the `/code` directory.
