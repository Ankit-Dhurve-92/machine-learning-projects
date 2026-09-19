# Credit Card Fraud Detection using Machine Learning

## Overview

This project develops a machine learning system to detect fraudulent credit card transactions.

The dataset is highly imbalanced, with fraudulent transactions representing only a small fraction of the total transactions. Therefore, the project focuses on appropriate evaluation metrics such as **Precision-Recall AUC (PR-AUC)** rather than relying only on accuracy.

## Dataset

The dataset contains **284,807 credit card transactions** with 30 input features and one target variable.

The target variable is:

- `0` - Non-Fraudulent Transaction
- `1` - Fraudulent Transaction

The dataset is included in this repository as:

`creditcard.csv`

Dataset reference:

https://www.kaggle.com/datasets/mlg-ulb/creditcardfraud

## Machine Learning Approach

The project follows these steps:

1. Data loading and inspection
2. Exploratory Data Analysis (EDA)
3. Missing value and duplicate checks
4. Analysis of class imbalance
5. Feature engineering using `log1p` transformation on transaction amount
6. Stratified train-test split
7. Baseline Decision Tree model
8. Comparison of class-balanced models
9. Stratified 5-Fold Cross-Validation
10. Model selection using PR-AUC
11. Randomized hyperparameter search
12. Final Random Forest model
13. Model evaluation
14. Fraud prediction system

## Models Used

The following models were explored:

- Decision Tree
- HistGradientBoosting
- Random Forest

Class balancing was incorporated into the models to address the highly imbalanced target distribution.

## Model Optimization

Random Forest was selected during the model comparison stage.

`RandomizedSearchCV` was used for hyperparameter optimization with:

- 5-Fold Stratified Cross-Validation
- Average Precision (PR-AUC) as the scoring metric

The tuned parameters included:

- Number of estimators
- Maximum depth
- Minimum samples per leaf
- Maximum number of features

## Evaluation Metrics

The models were evaluated using:

- Accuracy
- Precision
- Recall
- F1-Score
- Confusion Matrix
- Precision-Recall AUC (PR-AUC)

Because the dataset is highly imbalanced, **PR-AUC is emphasized as a more informative metric than accuracy alone**.

## Technologies Used

- Python
- NumPy
- Pandas
- Matplotlib
- Seaborn
- Scikit-learn
- Jupyter Notebook

## Project Structure

```text
02_credit_card_fraud_detection/
│
├── README.md
├── 15_3_credit_card_fraud_detection.ipynb
└── creditcard.csv
