# Forecast-Green-Energy-Job-A-Thon

## Objective

My task at hand is to build a machine learning/deep learning approach to forecast the total energy demand on an hourly basis for the next 3 years based on past trends.

## My Approach

Given the wide range of approaches and hyperparameters available, time series forecasting can be challenging. I applied the Prophet model to forecast future data. Prophet is an open-source library developed by Facebook for univariate (one variable) time series forecasting. The "Facebook Prophet" is another name for this type. It is easy to use and designed to automatically find a good set of hyperparameters for the model in an effort to create accurate forecasts for data with trends and seasonal structure by default.

## Tech Stack

1. Language - Python

2. Libraries - Pandas, NumPy, Sklearn, Prophet, Plotly, Math, Matplotlib.

## My Approach

1. Importing the required libraries and reading the dataset.

2. Data pre-processing

    a. Finding the missing data points

    b. Replaced the Null values with the energy attribute's mean value

    c. DateTime column was changed from ‘object’ type to ‘datatime’ type format.

    d. Data points of the energy attribute against time over a ten-year period were plotted on graphs, and conclusions were derived.

3. Performing train test split

    a. I divided the provided train data into train and validation datasets, since it is a time series dataset, I used data from 2008 to 2017 as the train data and 2018 as my validation data.

4. Model building

    a. Prophet() objects must first be defined and configured before being fitted to a dataset by performing the fit() function and providing the dataset.

    b. The Prophet() object accepts arguments to configure the desired model's growth, seasonality, and other parameters. By default, the model will put a lot of effort on automating practically everything.

    c. A DataFrame of time series data is passed to the fit() function. There must be a particular format for the DataFrame. Date-time information must be in the first column, which must be named "ds." The observations must be in the second column, named "y."

6. Model Validation

    a. Calling the predict() function on a Validation DataFrame with a single column named "ds" and rows containing date times for each interval to be predicted produces a forecast.

    b. The predict() function produces a DataFrame with numerous columns as its output. The projected date and time ('ds'), the expected value ('yhat'), and the lower and upper boundaries on the predicted value ('yhat lower' and 'yhat upper') that indicate prediction uncertainty are likely to be the most crucial columns.

7. Model Performance

    a. Root Mean Square Error: 234.101
    
    b. Plot for actual and predicted values and we can see that the predicted 2018 year matches the actual observations rather well.

8. Model Future Predictions

    a. Predictions were done for the next 3 years i.e 2019, 2020 (leap year), and 2021. Here, I created three years' worth of data on an hourly basis 
        
        2019, 2020 (leap), 2021 --> 365 + 366 + 365 = 1096 days
        
        1 day = 24 hours  -->  24 x 1095 = 26304 hours 
