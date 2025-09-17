# Telco Customer Churn
---

## Introduction

This project predicts customer churn for a fictitous telecommonuications company. Project covers the full pipeline: data exploration, preprocessing, model training, and evaluation.

## Dataset

The dataset comes from [Kaggle: Telco Customer Churn](https://www.kaggle.com/datasets/blastchar/telco-customer-churn/data), **containing 7043 entries** and **21 columns** describing customers.

## Methodology

**<u>1. Data Investigation</u>**
    - An small-to-mid sized imbalanced dataset, with lower number of churned customers $\longrightarrow$ Stratified K-Fold CV
    - Imputation of `TotalCharges`
    - Column datatype transformation
**<u>2. Feature Engineering</u>**
    - `MonthlyCharges_per_tenure` is created as a result of EDA
    - Binary Features are created for those having multiple options
**<u>3. Data Preprocessing</u>**
    - `PowerTransformation` with `yeo-johnson` method is used as one of the columns is not right-skewed
    - Standard Scaling is used
    - One Hot Encoding (OHE) is applied to nominal categorical features
**<u>4. Model Training and Evaluation</u>**
    - Models are scored based on **ROC AUC**
    - Custom pipelines are integrated depending on the model
    - 10-Fold Stratified CV is used

**Models Trained and Evaluated**

* Logistic Regression
* Naive Bayes (purely Experimental)
* Support Vector Machine (SVM)
* Random Forest Classifier
* XGBoost Classifier

## Results

The best performing model (Logistic Regression) achieved **0.8480 ROC-AUC** and **0.6388 F1-Score**