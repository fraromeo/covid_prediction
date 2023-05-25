# Forecasting COVID-related variables

The aim of the project is to implement a model which is able to predict data related to the COVID19 pandemic in three italian regions: Lombardia, Lazio, Sicilia. For each of these three regions we have a daily dataset containing information about four categories that we aim at predicting: New Infections, Hospitalised, Recovered, Deceased. In particular, we decided to discard data related to 2020, given the fact that the vaccination campaign started at the end of that year. 

To accomplish this task, two algorithms have been used: Artificial Neural Networks and ARIMA model. 

# ARIMA Model 

An ARIMA model is defined by the values of three parameters (p,d,q). To estiamte these parameters, we built different models and we selected the one that minimizes the Bayesian Information Criterion (BIC). We trained the model using data from 02-01-2021 to 23-05-2022. The permorfances are evaluated on the following week: 24-05-2022 to 31-05-2022.

The model is good in predicting the trend for new infections. In particular, the model predicts new infections in Lazio with a Mean Absolute Error of 64.06, in Lombardia with a Mean Absolute Error of 37.18 and in Sicilia with a Mean Absolute Error of 130.13.

Predictions for new infections in Lazio:
![image](https://github.com/fraromeo/covid_prediction/assets/64698911/9c9b5c5d-8f33-414a-a757-60ed0344455b)

This model will be used to predict new infections and recovered patients, while the neural network to predict deceased and hospitalised.

# Neural Network 


In order to have a meaningful training for our Neural Network, we need to define a training and validation set. The best case scenario would be to consider only the most recent data, since the Omicron variant introduced significant modifications in the magnitude of the reported cases. However, the numerosity of the post-Omicron days is not sufficient for the training: as a consequence we consider data from 01/02/2021 to 05/12/2021 as a pre-peak training set. The training set is completed from the post-peak part, including days from 05/01/2022 to 06/04/2022. The following days create the validation set. The dataset is then created by generating input windows of 14 days, in order to capture a bi-week trend, and choosing as output the prediction for new hospitalized and deceased after seven days. The last step before fitting the network consists in a random resampling of the training set. By choosing to include also older days in our training set we have solved the issue of numerosity, but introduced the one of unbalance. Specifically, we would like more recent training instances to be weighted more during training: as a solution we resample the tuples of our training dataset, with probabilities increased for recent observations.

Moreover, the simple collection of daily deceased and hospitalised is not sufficient to fully represent the phenomenon and proved to be a poor input for our Neural Network. That is why we also provided as input the estimates of first, second and third derivative of these quantities

The performances of the Neural Networks are extremely poor when considering new positives and recovered, while their prediction are good for hospitalized and deceased. The reason is that Omicron changed significantly the evolution of the first two quantities, with a sharp increase in magnitude even after the peak. On the other hand, due to the minor gravity of the infection, the number of hospitalized and deceased remains comparable both before and after the peak.

When trying to predict deceased and hospitalized we chose to consider the daily increments, rather than the cumulative quantities.


<img width="647" alt="Schermata 2023-05-25 alle 18 32 38" src="https://github.com/fraromeo/covid_prediction/assets/64698911/80832730-1c7c-482b-96f5-491f39817d7d">

# Team 
- Davide Carrara [[Github](https://github.com/davidecarrara98)] [[Email](mailto:davide1.carrara@mail.polimi.it)]
- Caterina Leimer Saglio
- Francesco Romeo [[Github](https://github.com/fraromeo)] [[Email](mailto:francesco5.romeo@mail.polimi.it)]

