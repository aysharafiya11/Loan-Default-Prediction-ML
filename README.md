# Loan Default Prediction & Credit Risk Analysis

![Python](https://img.shields.io/badge/Python-3.13-blue)
![Pandas](https://img.shields.io/badge/Pandas-Data%20Analysis-blue)
![Scikit-learn](https://img.shields.io/badge/Scikit--learn-Machine%20Learning-orange)
![Random Forest](https://img.shields.io/badge/Model-Random%20Forest-green)
![Jupyter](https://img.shields.io/badge/Notebook-Jupyter-orange)

## Project Overview

This project uses machine learning to predict whether a loan is likely to be **Fully Paid** or **Charged Off**.

The project builds on a previous Power BI analysis of the same loan dataset. While the Power BI project focused on historical credit-risk patterns, this project applies machine learning to predict loan outcomes.

## Objectives

- Clean and prepare loan data for machine learning
- Identify and address data-quality issues
- Prevent data leakage during model validation
- Build classification models for loan-status prediction
- Compare model performance using multiple evaluation metrics
- Identify important features influencing model predictions
- Generate predictions for the provided test dataset

## Dataset

The training dataset contains loan and borrower information such as:

- Current Loan Amount
- Credit Score
- Annual Income
- Monthly Debt
- Years of Credit History
- Number of Open Accounts
- Current Credit Balance
- Maximum Open Credit
- Home Ownership
- Loan Purpose
- Loan Term

The target variable is:

- **Fully Paid**
- **Charged Off**

## Data Preparation

The dataset was prepared by:

- Removing completely blank records
- Correcting suspicious Credit Score values
- Replacing placeholder Current Loan Amount values with missing values
- Removing exact duplicate records
- Handling missing values through preprocessing
- Encoding categorical variables
- Scaling numerical variables
- Preventing Loan ID and Customer ID leakage during validation

## Machine Learning Models

Two classification models were evaluated:

1. Logistic Regression
2. Random Forest

### Model Evaluation

The models were evaluated using:

- Accuracy
- Precision
- Recall
- F1-score
- ROC-AUC
- Confusion Matrix

Random Forest was selected as the final model because it provided better recall, F1-score, and ROC-AUC than Logistic Regression on the corrected validation split.

## Final Model

The selected Random Forest model was retrained using the complete cleaned training dataset.

It was then used to generate predictions for the valid records in the provided test dataset.

The test dataset does not contain the actual `Loan Status`, so the final test predictions cannot be evaluated using standard classification metrics.

## Key Insights

The Random Forest model identified several financial and credit-history variables as important predictors, including:

- Current Loan Amount
- Maximum Open Credit
- Monthly Debt
- Current Credit Balance
- Years of Credit History
- Annual Income
- Credit Score

Feature importance represents the contribution of features to the model's predictions and does not imply a causal relationship.

## Tools & Technologies

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn
- Jupyter Notebook
- Git & GitHub

## Project Structure

```text
Loan-Default-Prediction-ML/
│
├── data/
│   ├── credit_train.csv
│   └── credit_test.csv
│
├── Images/
│   ├── loan_status_distribution.png
│   └── random_forest_feature_importance.png
│
├── notebooks/
│   └── loan_default_analysis.ipynb
│
├── outputs/
│   └── loan_predictions.csv
│
└── README.md

