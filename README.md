# Abalone Age Prediction Project

## Group 3: Jacob Douthett, Sam Espe, Alan Jallah, Jae Neuharth

## Overview

This project would produce a model that would attempt to determine the age of abalone based on macroscopic physical characteristics. The age of an abalone is currently determined by cutting the shell open and counting the microscopic rings. Finding another way to determine an abalone’s age could lead to better harvesting decisions and prevent its extinction. In order to try and determine how to predict the age of an abalone without damaging the shell/endangering the creature, we wanted to use a Linear Regression model to predict the best abalone based on physical characteristics.

## Data set

We found our data set from Kaggle (https://www.kaggle.com/datasets/hurshd0/abalone-uci) that shared the original data set from the UC Irvine Machine Learning Repository: (https://archive.ics.uci.edu/ml/datasets/abalone). The UCI data set was compiled and shared in 1995 and contains an extensive account of data about the characteristics of the studied abalone, such as sex, shell length/width/height, weight, etc. The most important value that the data set shares is the number of microscopic rings within the shell, which are used to determine its age, and that will be important for measuring our predictions.


# The Process

## Extraction, Transformation, and Loading
We downloaded the data, imported it into Google Colabs, and began the process of cleaning it. We used Pandas to import the CSV file from a Google Drive and checked for duplicate entries and missing values to remove any invalid data points that could contaiminate our data. In order to change the categorical values of the *`Sex`* column into numerical values that we can use more efficiently in our models, we used `get_dummies()` to convert them into dummy/indicator variables and then were ready to run our models. We then created the dataframe.

With such a large data set to work with, there were bound to be outliers that could cause problems with our prediction models. Using `matplotlib` in the colab notebook, we graphed every column in the dataframe on the y-axis against the number of rings on the x-axis to visualize our data set and by doing so managed to find four outliers in the height column. After dropping those row values, we had successfully completed the ETL process and were ready to begin running our model.

## Linear Regression Model Process

We started by running a **Multiple Linear Regression** by spliting our data into training and testing sets and using train_test_split to prep the data for analysis. The end result of the test resulted in a score of ***0.5459***, which was not good enough, so the test was ran again with the outliers removed and resulted in a score of ***0.5199*** which was worse than the initial test. Finally, we used a MinMax Scaler instead of a Standard Scaler which resulted in ***0.5195***, the worst score of the tests so far. It was evident that a multiple linear regression was not going to work, so we tested other models to try and find one that did work.

## K Nearest Neighbors
We got a score of ***0.5144***. Not good.

## Support Vector Regression
A score of ***0.5443***. Better, but still not very good.

## Random Forest Regressor
***0.5533***. Getting there, but not something we could work with.

## Neural Network
We ran several tests with a neural network, adding hidden layers and more epochs along the way, but the test scores still ranged from only ***0.5117*** to ***0.5778***.

## Keras Tuner
*TBD*

# Results

The tests proved that our data would be either unable to be tested or would be unreliable to run a linear regression model. Therefore, we are unable to make a proper prediction.

# Recreate The Results

> 1. Clone the repo
> 2. Open Google Colabs
> 3. Import the `Abalone_Age_Prediction.ipynb` file
> 4. Run the cells in the colab notebook in order

