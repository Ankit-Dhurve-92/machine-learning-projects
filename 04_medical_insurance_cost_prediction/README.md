# Medical Insurance Cost Prediction using Machine Learning

## Overview

This project develops a machine learning regression system to predict individual medical insurance costs using demographic and health-related features.

The project covers exploratory data analysis, preprocessing, baseline modeling, model comparison, cross-validation, hyperparameter tuning, target transformation, and final prediction.

## Dataset

The dataset contains information about individuals and their medical insurance charges.

Features include:

- `age` - Age of the individual
- `sex` - Gender
- `bmi` - Body Mass Index
- `children` - Number of dependent children
- `smoker` - Smoking status
- `region` - Residential region
- `charges` - Medical insurance cost (target)

The dataset is included in this repository as:

`insurance.csv`

Dataset source:

https://www.kaggle.com/datasets/mirichoi0218/insurance

## Machine Learning Approach

The project follows the following workflow:

1. Data loading and inspection
2. Exploratory Data Analysis (EDA)
3. Missing value and duplicate analysis
4. Statistical analysis and visualization
5. Outlier analysis
6. Correlation analysis
7. Train-test split
8. Feature preprocessing using pipelines
9. Linear Regression baseline
10. Model comparison using 5-Fold Cross-Validation
11. Random Forest hyperparameter tuning
12. Target variable log transformation
13. Final model training
14. Test-set evaluation
15. Residual analysis
16. Medical insurance cost prediction for new inputs

## Data Preprocessing

### Numerical Features

Numerical features are standardized using:

- `StandardScaler`

### Categorical Features

Categorical features are converted into numerical representations using:

- `OneHotEncoder`

The preprocessing steps are implemented using `ColumnTransformer` and Scikit-learn pipelines to maintain a consistent preprocessing workflow.

## Models Used

The following regression models were compared:

- Linear Regression
- Ridge Regression
- Lasso Regression
- Decision Tree Regressor
- Random Forest Regressor
- XGBoost Regressor

Model performance was compared using **5-Fold Cross-Validation**.

## Model Optimization

Random Forest was selected based on cross-validation performance.

Hyperparameters were optimized using `GridSearchCV`, including:

- Number of estimators
- Maximum depth
- Maximum features
- Minimum samples split
- Minimum samples per leaf
- Bootstrap sampling

## Target Transformation

The target variable `charges` is right-skewed.

A `log1p` transformation was applied to the target variable using `TransformedTargetRegressor` to improve the modeling of highly skewed insurance costs.

The predictions were converted back to the original scale using the inverse `expm1` transformation.

## Evaluation Metrics

The models were evaluated using:

- MAE (Mean Absolute Error)
- RMSE (Root Mean Squared Error)
- R² Score

MAE was emphasized because it provides an interpretable measure of the average prediction error and is less sensitive to extreme values than RMSE.

## Prediction System

A prediction function was implemented to estimate medical insurance costs for new individuals using:

- Age
- Sex
- BMI
- Number of children
- Smoking status
- Region

Example:

```python
pred = predict_insurance_charges(
    rf_best_log,
    age=35,
    sex="male",
    bmi=29.5,
    children=2,
    smoker="no",
    region="southeast"
)
