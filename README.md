# Udacity Machine Learning Engineer Nanodegree
## Capstone Project: Kaggle competition: M5 Forecasting - Accuracy

### Overview
The goal of this competition is to predict ‘the unit sales of various products sold in the USA by Walmart.’ (All citations in this document if not stated overwise are from the M5 Forecasting - Accuracy challenge https://www.kaggle.com/c/m5-forecasting-accuracy/overview/description) 
Link to the Kaggle competition: https://www.kaggle.com/c/m5-forecasting-accuracy/
Link to the competition website with guidelines: https://mofc.unic.ac.cy/m5-competition/


### Domain Background
‘Walmart Inc. is an American multinational retail corporation that operates a chain of hypermarkets, discount department stores, and grocery stores’. A good forecasting model helps retailers to plan marketing companies, manage cash flow, manage their inventory and optimize their supply chain leading to increase of profit, whereas ‘inaccurate business forecasts could result in actual or opportunity losses.’  Forecasting is an active area of research, in this project I concentrate on quantitative methods, such as time series analysis and regression methods.  

### Problem statement
The goal of this competition is to ‘to forecast daily sales for the next 28 days’ based on the data from ‘stores in three US States (California, Texas, and Wisconsin)’ . The data ‘includes item level, department, product categories, and store details. In addition, it has explanatory variables such as price, promotions, day of the week, and special events. Together, this robust dataset can be used to improve forecasting accuracy.’

### Datasets and Inputs
The data provided by the Kaggle platform contain five files. 
calendar.csv - Contains information about the dates on which the products are sold.
sales_train_validation.csv - Contains the historical daily unit sales data per product and store [d_1 - d_1913]
sample_submission.csv - The correct format for submissions.
sell_prices.csv - Contains information about the price of the products sold per store and date.
sales_train_evaluation.csv - Available once month before competition deadline. Will include sales [d_1 - d_1941]

### Solution
I am going to explore time series forecasting models (like ARIMA) and tree based algorithms like RandomForest and XGboost to make the predictions.

### Benchmark
For a selected item  sold on a particular day the benchmark forecast is the average number of items sold at the same day of the week.

### Evaluation Metric
The accuracy of the point forecasts will be evaluated using the Root Mean Squared Scaled Error (RMSSE), which is a variant of the well-known Mean Absolute Scaled Error (MASE) proposed by Hyndman and Koehler (2006). 

### Project design
An excellent exploratory data analysis is presented at https://www.kaggle.com/headsortails/back-to-predict-the-future-interactive-m5-eda. 
The project contains three notebooks:
- 00_data_preparation: data formating for ML algorithms and feature enhancement 
- 01_naive_predictors: two naive predictors are calculated:
  1. items sold 364 days ago 
  2. average items sold on the same weekday
- 03_lightGBM: lightGBM model is fit to data
