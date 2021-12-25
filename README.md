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
Scince we are interested only furniture sales we want to know how much is the furniture data represent out of the whole dataset we have, and how much furniture sales represents out of the whole sales in the dataset. Answer 21% of the data belong to furniture, 32% of the sales belong to the furniture.

![](graphs/data_disturbution.png?raw=true "")


### Annual Furniture-Sales
The following graph shows a month-wise comparison over years, noticeable, few months like 3,7, and 9 have close sales to each other over the past 4 years vice versa in months like 5,9, and 11: 

![](graphs/furniture_sales_annual.png?raw=true "")


### Quarterly Furniture-Sales
The following graph shows seasonality increasing (yearly) in the furniture sales: 

![](graphs/furniture_sales_quarterly.png?raw=true "")


### trend in Furniture-Sales
The following graph shows an increasing trend in furniture sales over the last 4 years:

![](graphs/trend.png?raw=true "")




# Data Preprocessing


### Missing Days
The following graph shows missing days (days with no furniture sales on them) in Jan 2016 as an example, the total missing days in the whole data is 565 days out of 1,461 days. To avoid the missing days, we took weekly furniture sales instead.

![](graphs/missing_values_in_daily_furniture_sales.png?raw=true "")




# Modeling


### 1. Base Model - Naive Model
To have base performance measure that we can compare any later model performance with, we can start by the simplest naive model (persistence model), basically forecasting based on the previous value, naive model performed (RMSE = 3149.0964, R2 Score = -0.048).

![](graphs/model_evaluation_naive.png?raw=true "")


### 2. Linear Regression + Lag=1 Model
As a first try to build a high-performance, non-complex forecasting model, linear regression with lag equal to 1 was built and tested. This model shows RMSE=3140.5 and R2 Score=-0.0145, based on these results we can notice it is a bad-performed model let's try to build a better model.

![](graphs/model_evaluation_linear_regression_lag_1.png?raw=true "")


**1st (Linear Regression), 2nd, and 3rd degree ploynomial + Lag = 1-60** 
Searching for the best number for the Lag between 1 and 60, and for the best degree between 1st, 2nd, and 3rd polynomial. Based on the RMSE metric, Lag=52 is the best (make sense, since a year has ~52.17 weeks) and 1st-degree polynomial (Linear Regression) has the best performance. The following graph illustrates the experiment:

![](graphs/three_degree_polynomial_comparison.png?raw=true "")


### 3. Linear Regression + Lag=52 Model
Now let's try the best model we have until now and see the results to compare with the other models. This model shows RMSE=2353.2 and R2 Score=0.3405, so this model has the best performance so far, but it's not enough so let's try to build a better one: 

![](graphs/model_evaluation_linear_regression_lag_52.png?raw=true "")


### 4. ARIMA Model
Let's try to build a more complex model, so let's go with ARIMA and see how it will perform. ARIMA shows RMSE=2133.9 and R2 Score=0.4577, which has the best performance so far, however, let's try Seasonal-ARIMA and see if it will perform better than the winner so far, ARIMA model.

![](graphs/model_evaluation_ARIMA.png?raw=true "")


### 5. SARIMA Model
Now by trying the Seasonal-ARIMA model, its performance was RMSE=1906.2 and R2 Score=0.5673, which indicate SARIMA is the best-performed model among the others, winner model.

![](graphs/model_evaluation_SARIMA.png?raw=true "")




# Summary
To conclude, by trying different models from simplest to more complex, from Naive to SARIMA, we can notice an increase in the performance of these models in the following graph. SARIMA has the best performance among the other models.


### R2 Score 

![](graphs/evaluation_r2_score.png?raw=true "")


### Root Mean Square Error (RMSE)

![](graphs/evaluation_rmse.png?raw=true "")


### Final Forecasting using SARIMA
Now let's see how is the winner model (SARIMA) will forecast the next 3 years since it's our goal.

![](graphs/model_forecasting_final.png?raw=true "")




</br>

*Contributors [Abdulaziz Alshehri](https://github.com/AbdulazizAlshehri)*
