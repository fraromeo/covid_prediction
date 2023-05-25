# Forecasting COVID-related variables

The aim of the project is to implement a model which is able to predict data related to the COVID19 pandemic in three italian regions: Lombardia, Lazio, Sicilia. For each of these three regions we have a daily dataset containing information about four categories that we aim at predicting: New Infections, Hospitalised, Recovered, Deceased. In particular, we decided to discard data related to 2020, given the fact that the vaccination campaign started at the end of that year. 

To accomplish this task, two algorithms have been used: Artificial Neural Networks and ARIMA model. 

# ARIMA Model 

An ARIMA model is defined by the values of three parameters (p,d,q). To estiamte these parameters, we built different models and we selected the one that minimizes the Bayesian Information Criterion (BIC). 

The model is good in predicting the trend for new infections, and in particular it obtains a Mean Absolute Error of 64.06 in predicting new infections in Lazio for the week that goes from 24-05-22 to 30-05-22
