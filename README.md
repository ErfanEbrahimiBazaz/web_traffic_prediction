# Intro

This repository includes building timeseries analysis (tsa) models for [kaggle web traffic competition](https://www.kaggle.com/c/web-traffic-time-series-forecasting).
The dataset contains 145063 URLs. Each requires a different tsa. As the methodology is the same, I take the first URL in dataset, "2NE1_zh.wikipedia.org_all-access_spider" and apply all different methods to it.


### Notebook explanation
timeseries_notebook1: Getting to know and cleaning data, transposig, building index and saving into a dataset for furhter analysis.
ARIMA: Buidling an AR (Auto Regressive), MA (Moving Average) and ARIMA (AR Integrated MA) model and using the ARIMA one for making predictions.

