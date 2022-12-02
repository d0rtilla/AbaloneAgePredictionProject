# Abalone Age Prediction Project

## Group 3: Jacob Douthett, Sam Espe, Alan Jallah, Jae Neuharth

## Overview

This project would produce a model that would attempt to determine the age of abalone based on macroscopic physical characteristics. The age of an abalone is currently determined by cutting the shell open and counting the microscopic rings. Finding another way to determine an abalone’s age could lead to better harvesting decisions and prevent its extinction. 

## Data set

We found our data set from Kaggle (https://www.kaggle.com/datasets/hurshd0/abalone-uci) that shared the original data set from the UC Irvine Machine Learning Repository: (https://archive.ics.uci.edu/ml/datasets/abalone). The UCI data set was compiled and shared in 1995 and contains an extensive account of data about the characteristics of the studied abalone, such as sex, shell length/width/height, weight, etc. The most important value that the data set shares is the number of microscopic rings within the shell, which are used to determine its age, and that will be important for measuring our predictions.

# The Process

## Extraction, Transformation, and Loading
We downloaded the data, imported it into Google Colabs, and began the process of cleaning it. We used Pandas to import the CSV file from a Google Drive and checked for duplicate entries and missing values to remove any invalid data points that could contaiminate our data. In order to change the categorical values of the *`Sex`* column into numerical values that we can use more efficiently in our models, we used `get_dummies()` to convert them into dummy/indicator variables and then were ready to run our models.
