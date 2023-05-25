# Forecasting COVID-related variables

The aim of the project is to implement a model which is able to predict data related to the COVID19 pandemic in three italian regions: Lombardia, Lazio, Sicilia. For each of these three regions we have a daily dataset containing information about four categories that we aim at predicting: New Infections, Hospitalised, Recovered, Deceased. In particular, we decided to discard data related to 2020, given the fact that the vaccination campaign started at the end of that year. 

To accomplish this task, two algorithms have been used: Artificial Neural Networks and ARIMA model. 

# ARIMA Model 

An ARIMA model is defined by the values of three parameters (p,d,q). To estiamte these parameters, we built different models and we selected the one that minimizes the Bayesian Information Criterion (BIC). We trained the model using data from 02-01-2021 to 23-05-2022. The permorfances are evaluated on the following week: 24-05-2022 to 31-05-2022.

The model is good in predicting the trend for new infections. In particular, the model predicts new infections in Lazio with a Mean Absolute Error of 64.06, in Lombardia with a Mean Absolute Error of 37.18 and in Sicilia with a Mean Absolute Error of 130.13.

Predictions for new infections in Lazio:
![image](https://github.com/fraromeo/covid_prediction/assets/64698911/9c9b5c5d-8f33-414a-a757-60ed0344455b)


![image](https://github.com/fraromeo/covid_prediction/assets/64698911/e040475c-2a0a-428d-a988-4298601934c4)


![image](https://github.com/fraromeo/covid_prediction/assets/64698911/0cfc3406-6899-4188-aa98-c0a06f85bcca)

