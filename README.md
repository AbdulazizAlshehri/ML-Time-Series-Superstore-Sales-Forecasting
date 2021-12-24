# ML-Time-Series-Superstore-Sales-Forecasting
Machine learning timeseries superstore sales forecasting




# Table of Content
- [Code](https://github.com/AbdulazizAlshehri/ML-Time-Series-Superstore-Sales-Forecasting/blob/main/code/Superstore_Sales_Forecasting_.ipynb)
- [Data](https://github.com/AbdulazizAlshehri/ML-Time-Series-Superstore-Sales-Forecasting/blob/main/datasets/Sample%20-%20Superstore.xls)
- [Presentation](https://github.com/AbdulazizAlshehri/ML-Time-Series-Superstore-Sales-Forecasting/blob/main/presentation/Furniture%20Sales%20Forecasting.pdf)




# About
A time-series project that aims to forecast the furniture sales for the next 3 years based on the data of the last 4 years. Linear Regression with lag, first three degrees polynomial with lag, ARIMA, and SARIMA were tested to forecast furniture sales for the next three years.




# Data Exploration


### Data Distribution
Scince we are interested only furniture sales we want to know how much is the furniture data represent out of the whole dataset we have, and how much furniture sales represents out of the whole sales in the dataset.

![](graphs/data_disturbution.png?raw=true "")


### Annual Furniture-Sales

![](graphs/furniture_sales_annual.png?raw=true "")


### Quarterly Furniture-Sales

![](graphs/furniture_sales_quarterly.png?raw=true "")


### Monthly Furniture-Sales

![](graphs/furniture_sales_monthly.png?raw=true "")


### trend in Furniture-Sales

![](graphs/trend.png?raw=true "")


### Sales Vs Profit of Furniture

![](graphs/furniture_sales_vs_profit.png?raw=true "")




# Data Preprocessing

### Missing Days
The following graph shows the missing days (days with no furniture sales on them) for Jan, 2016, so weekly furniture sales was taken to avoid missing-values in the time series.

![](graphs/missing_values_in_daily_furniture_sales.png?raw=true "")




# Modeling

### 01. Base Model - Naive Model
To have base performance that we can compare any later model performance with, we can start by the simplest naive model (persistence model), basically forecasting based on the previous value, naive model performed (RMSE = 3149.0964, R2 Score = -0.048).

![](graphs/model_evaluation_naive.png?raw=true "")


### 02. Linear Regression + Lag=1 Model

![](graphs/model_evaluation_linear_regression_lag_1.png?raw=true "")


### **1st (Linear Regression), 2nd, and 3rd degree ploynomial + Lag = 1-60** 
Searching for the best number for the Lag between 1 and 60, and for the best degree between 1st, 2nd, and 3rd polynomial. Based on RMSE metric, Lag=52 (make sense, since a year has ~52.17 weeks) and 1st degree polynomial (Linear Regression) has the best performance. The following graph illustrate the experement:

![](graphs/three_degree_polynomial_comparison.png?raw=true "")

### 03. Linear Regression + Lag=52

![](graphs/model_evaluation_linear_regression_lag_52.png?raw=true "")


### 04. ARIMA Model

![](graphs/model_evaluation_ARIMA.png?raw=true "")


### 04. SARIMA Model

![](graphs/model_evaluation_SARIMA.png?raw=true "")


# Summary

### R2 Score

![](graphs/evaluation_r2_score.png?raw=true "")


### RMSE

![](graphs/evaluation_rmse.png?raw=true "")







</br>

*Contributors [Abdulaziz Alshehri](https://github.com/AbdulazizAlshehri)*



