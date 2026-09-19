# House Price Prediction using Machine Learning

## Overview

This project develops a machine learning regression pipeline to predict median house values using the California Housing dataset.

The project covers exploratory data analysis, preprocessing, baseline modeling, cross-validation, model comparison, hyperparameter tuning, and final model evaluation.

## Dataset

The project uses the California Housing Prices dataset.

The target variable is:

`median_house_value`

The dataset contains numerical housing and demographic features along with a categorical feature describing the property's proximity to the ocean.

The dataset is included in this repository as:

`housing.csv`

Dataset source:

https://www.kaggle.com/datasets/camnugent/california-housing-prices

## Machine Learning Approach

The project follows the following workflow:

1. Data loading and inspection
2. Exploratory Data Analysis (EDA)
3. Missing value analysis
4. Duplicate and outlier analysis
5. Correlation analysis
6. Train-test split
7. Data preprocessing using pipelines
8. Linear Regression baseline
9. Model comparison using 5-Fold Cross-Validation
10. Hyperparameter tuning using GridSearchCV
11. Final model training
12. Test-set evaluation
13. Residual analysis
14. House price prediction for new input data

## Data Preprocessing

### Numerical Features

Numerical features are processed using:

- Median imputation
- StandardScaler

### Categorical Features

The `ocean_proximity` feature is processed using:

- Most-frequent imputation
- One-Hot Encoding

Scikit-learn pipelines and `ColumnTransformer` are used to keep preprocessing consistent and avoid data leakage.

## Models Used

The following regression models were compared:

- Linear Regression
- Ridge Regression
- Lasso Regression
- Random Forest Regressor
- HistGradientBoosting Regressor

Model selection was performed using **5-Fold Cross-Validation**.

## Model Optimization

HistGradientBoostingRegressor was selected based on cross-validation RMSE.

Hyperparameters were optimized using `GridSearchCV`, including:

- Learning rate
- Maximum depth
- Maximum leaf nodes
- Minimum samples per leaf
- L2 regularization

## Evaluation Metrics

The models were evaluated using:

- RMSE (Root Mean Squared Error)
- MAE (Mean Absolute Error)
- R² Score

RMSE was used as the primary model-selection metric.

## Prediction System

A prediction function was implemented to estimate the median house value for a new property using features such as:

- Longitude
- Latitude
- Housing median age
- Total rooms
- Total bedrooms
- Population
- Households
- Median income
- Ocean proximity

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
03_house_price_prediction/
│
├── README.md
├── 15_4_house_price_prediction.ipynb
└── housing.csv
