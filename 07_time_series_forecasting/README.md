# Time Series Forecasting using ARIMA and SARIMAX

## Overview

This project focuses on forecasting monthly airline passenger demand using historical time-series data.

The analysis explores long-term trends and recurring seasonal patterns in airline passenger traffic and applies statistical forecasting models to predict future passenger demand.

## Dataset

The project uses the **Airline Passengers** dataset containing monthly passenger counts.

The dataset contains:

- `Month` - Month and year of observation
- `Passengers` - Number of airline passengers

The dataset is included in this repository as:

`airline-passengers.csv`

## Time Series Analysis

The project follows these steps:

1. Load and inspect the time-series dataset
2. Convert the date column into a datetime index
3. Visualize the historical passenger trend
4. Analyze stationarity using the Augmented Dickey-Fuller (ADF) test
5. Perform seasonal decomposition
6. Identify recurring yearly seasonality
7. Create a chronological train-test split
8. Train ARIMA model
9. Generate 12-month forecasts
10. Train seasonal SARIMAX model
11. Compare forecasts with actual values
12. Evaluate forecasting performance

## Stationarity Analysis

The **Augmented Dickey-Fuller (ADF) test** was used to examine whether the time series is stationary.

The analysis indicated that the original passenger series is non-stationary, motivating the use of differencing and seasonal modeling.

## Seasonal Decomposition

Seasonal decomposition was performed using a multiplicative model with a period of:

`12 months`

This helps identify:

- Trend
- Seasonality
- Residual components

The analysis shows a clear recurring yearly seasonal pattern in airline passenger demand.

## Models Used

### ARIMA

ARIMA (AutoRegressive Integrated Moving Average) was used as a baseline time-series forecasting model.

Model configuration:

```text
ARIMA(5, 1, 0)
