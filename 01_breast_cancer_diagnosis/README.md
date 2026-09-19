# Breast Cancer Diagnosis using Machine Learning

## Overview

This project uses machine learning techniques to classify breast tumors as **Benign** or **Malignant** using the Breast Cancer dataset.

The project includes data preprocessing, exploratory data analysis, dimensionality reduction, model training, hyperparameter tuning, and model evaluation.

## Dataset

The dataset contains numerical features extracted from breast tumor samples.

The target variable represents two classes:

- **Benign**
- **Malignant**

The dataset used in this project is included in this repository as:

`breast_cancer_dataset.csv`

## Machine Learning Approach

The following steps were performed:

1. Data loading and preprocessing
2. Exploratory Data Analysis (EDA)
3. Feature scaling using StandardScaler
4. Logistic Regression as a baseline model
5. Dimensionality reduction using Principal Component Analysis (PCA)
6. Classification using Support Vector Machine (SVM)
7. Hyperparameter tuning using GridSearchCV
8. Stratified 5-Fold Cross-Validation
9. Model evaluation using classification metrics and confusion matrix

## Models Used

### Logistic Regression

Logistic Regression was used as a baseline classification model.

### PCA + SVM

Principal Component Analysis (PCA) was used for dimensionality reduction, followed by a Support Vector Machine with an RBF kernel for classification.

Hyperparameters were optimized using GridSearchCV.

## Evaluation Metrics

The models were evaluated using:

- Accuracy
- Precision
- Recall
- F1-Score
- Confusion Matrix

Recall was given particular attention because correctly identifying malignant cases is important in this classification problem.

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
01_breast_cancer_diagnosis/
│
├── 15_2_breast_cancer_diagnosis.ipynb
├── breast_cancer_dataset.csv
└── README.md
