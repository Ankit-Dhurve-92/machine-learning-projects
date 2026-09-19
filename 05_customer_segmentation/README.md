# Customer Segmentation using K-Means Clustering

## Overview

This project applies unsupervised machine learning to segment customers into distinct groups based on their annual income and spending behavior.

K-Means clustering is used to identify customer segments that can be interpreted based on income and spending patterns.

## Dataset

The project uses the Mall Customers dataset.

Important features include:

- `CustomerID`
- `Gender`
- `Age`
- `Annual Income (k$)`
- `Spending Score (1-100)`

The dataset is included in this repository as:

`Mall_Customers.csv`

Dataset source:

https://www.kaggle.com/datasets/vjchoudhary7/customer-segmentation-tutorial-in-python

## Machine Learning Approach

The project follows the following workflow:

1. Data loading and inspection
2. Exploratory Data Analysis (EDA)
3. Missing value and duplicate analysis
4. Data visualization
5. Feature selection
6. Feature scaling
7. Elbow Method for selecting the number of clusters
8. K-Means clustering
9. Silhouette Score evaluation
10. Cluster visualization
11. Customer segment profiling
12. New customer segment assignment

## Features Used for Clustering

The following two features were selected:

- `Annual Income (k$)`
- `Spending Score (1-100)`

`CustomerID` was removed because it is an identifier and does not provide meaningful information for clustering.

## Data Preprocessing

Since K-Means is a distance-based algorithm, the selected features were standardized using:

`StandardScaler`

This ensures that the features contribute appropriately to the distance calculations.

## Choosing the Number of Clusters

The **Elbow Method** was used to analyze Within-Cluster Sum of Squares (WCSS) for different values of K.

The analysis indicated an elbow around:

`K = 5`

Therefore, five customer segments were created using K-Means.

## Clustering Model

The final model uses:

- Algorithm: K-Means
- Number of clusters: 5
- Initialization: k-means++
- Random state: 42
- Number of initializations: 10

## Evaluation

The clustering solution was evaluated using the **Silhouette Score**.

Silhouette scores were also calculated for different values of K to compare cluster separation.

## Customer Segmentation

After clustering, each customer was assigned to one of five segments.

Cluster profiles were analyzed using:

- Age
- Annual Income
- Spending Score

Both mean and median statistics were calculated for each cluster to understand the characteristics of different customer groups.

## New Customer Assignment

A prediction function was implemented to assign a new customer to an existing segment based on:

- Annual Income
- Spending Score

Example:

```python
new_cluster = assign_customer_segment(
    income_k=60,
    spending_score=65,
    scaler=scaler,
    model=kmeans_final
)
