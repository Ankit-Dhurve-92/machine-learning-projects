# Sonar Signal Classification using SVM

## Overview

This project uses machine learning to classify underwater objects as **Rock** or **Mine** based on sonar signal measurements.

The dataset contains numerical sonar signal features representing the energy of returned signals at different frequencies.

A Support Vector Classifier (SVC) is trained to distinguish between the two classes.

## Dataset

The dataset contains sonar signal measurements with:

- 60 numerical signal features
- 1 target label

Target labels:

- `R` - Rock
- `M` - Mine

The dataset contains 207 samples and 60 numerical input features.

The dataset is included in this repository as:

`sonar_data.csv`

## Machine Learning Approach

The project follows these steps:

1. Load and inspect the dataset
2. Exploratory Data Analysis (EDA)
3. Analyze class distribution
4. Check missing values
5. Analyze feature correlations
6. Split data into training and testing sets
7. Standardize numerical features
8. Train a Support Vector Classifier
9. Evaluate the model
10. Build a predictive system for new sonar signals

## Exploratory Data Analysis

The dataset was analyzed to understand:

- Class distribution
- Feature distributions
- Correlation between signal features
- Outliers
- Differences between Rock and Mine signal patterns

A correlation heatmap was used instead of a pairplot because the dataset contains 60 numerical features.

## Data Preprocessing

The input features are standardized using:

`StandardScaler`

Feature scaling is important for SVM because the model is sensitive to the relative scale of input features.

The target labels are converted into numerical values for model training.

## Model

A **Support Vector Classifier (SVC)** is used for binary classification.

SVM is suitable for classification problems with a relatively large number of features compared with the number of samples.

The model learns a decision boundary that separates sonar signals corresponding to Rocks and Mines.

## Evaluation

The model is evaluated on both training and testing data using:

- Accuracy
- Classification Report
- Precision
- Recall
- F1-Score

The test-set performance is used to evaluate how well the model generalizes to unseen sonar signals.

## Prediction System

A prediction function is implemented to classify a new sonar signal.

The function:

1. Accepts the 60 signal measurements
2. Applies the same feature scaling used during training
3. Passes the transformed data to the trained SVM model
4. Returns either Rock or Mine

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
08_sonar_signal_classification/
│
├── README.md
├── 15_1_sonar_signal_classification.ipynb
└── sonar_data.csv
