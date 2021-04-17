# Intro

This repository includes building timeseries analysis (tsa) models for [kaggle web traffic competition](https://www.kaggle.com/c/web-traffic-time-series-forecasting).
The dataset contains 145063 URLs. Each requires a different tsa. As the methodology is the same, I take the first URL in dataset, "2NE1_zh.wikipedia.org_all-access_spider" and apply all different methods to it.


### Notebook explanation
+ timeseries_notebook1: Getting to know and cleaning data, transposig, building index and saving into a dataset for furhter analysis.
+ ARIMA: Buidling an AR (Auto Regressive), MA (Moving Average) and ARIMA (AR Integrated MA) model and using the ARIMA one for making predictions.
+ LSTM_For_TSA: Data is prepared for feeding an LSTM model. The model is built by using Keras. Different architectures are checked by using different number of neurons and different number of layers with different dropout rates to see which model results the lowest MSE and therefore is the most accurate one.
+ 4-multivariate_tsa notebook: This is quite a big notebook. It contains preparing a dataframe from the timeseries to feed an XGBoost, a lightgbm, and a catboost model. In fact we have changed the timeseries problem from a univariate to a multivariate problem and like my other repositories for making ensemble models, I use that dataframe to train a model. Later an ensemble of models is trained with this data structure. I trained 5 xgboost, 5 lightgbm and 5 catboost models. Lightgbm requires large number of data to be trained well. As we only have 550 records (after creating the dataframe from timeseries), lightgbm performs poorly. 


I used pickle to dump each trained model. I weighted each catboost and xgboost trained model twice as a lightgbm one. Later on I made a hard voter to calculate the mean of the prediction of each model. To calculate the score of the ensemble voter I used MSE.




