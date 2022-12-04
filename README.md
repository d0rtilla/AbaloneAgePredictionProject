# Abalone Age Prediction with Supervised Machine Learning

## Group 3: Jacob Douthett, Sam Espe, Alan Jallah, Jae Neuharth

## Overview

This project experiments with supervised machine learning in an attempt to produce a model that could determine the age of an abalone based on macroscopic physical characteristics. The age of an abalone is currently determined by cutting the shell open and counting the microscopic growth rings. Finding another way to determine an abalone’s age could lead to better harvesting decisions and prevent its extinction. In order to predict the age of an abalone without the labor-intensive ring-counting process, we sought to create a model that would use characteristics that are easier to measure to predict an abalone's age.

## Data set

We found our data set from Kaggle (https://www.kaggle.com/datasets/hurshd0/abalone-uci), which shared the original data set from the University of California, Irvine Machine Learning Repository (https://archive.ics.uci.edu/ml/datasets/abalone). The UCI data set was compiled and shared in 1995 and contains an extensive account of data about the characteristics of the studied abalone, such as sex, dimensions of the shell, and weights of the abalone at various stages of processing. The data set also includes the number of microscopic growth rings within the shell, which are used to determine an individual's age.

## The Process

### Extraction, Transformation, and Loading
We used Google Colab as our development environment. We used Pandas to import the CSV file, and checked for duplicate entries and missing values to remove any invalid data points that could contaminate our data. In order to change the categorical values of the *`Sex`* column into numerical values that we can use in our models, we used Pandas' `get_dummies()` function to convert them into indicator variables.

With such a large data set to work with, there were bound to be outliers that could cause problems with our prediction models. Using `matplotlib` in the Colab notebook, we graphed every column in the dataframe against the number of rings to visualize our data set. By doing so, we managed to find four outliers in the height parameter. After dropping those row values, we were ready to experiment with machine learning models.

### Approaching the Models
Here is the approach we took to prepare the data for each model:
1. Instantiate the model.
1. Create our features matrix (X) and our target (y) vector.
1. Use SciKit-Learn's `train_test_split` to create a training and a testing set of data.
1. Instantiate a scaler, fit the scaler to the training feature set, and use the fitted scaler to transform the training and testing feature sets.
1. Fit the model to the training data set.
1. Evaluate the model on the training data set. This is to check if a model is overfitting the data.
1. Evaluate the model on the testing data set.
1. Calculate the R<sup>2</sup> value to determine how well the model performed.

### Multiple Linear Regression Models

We started by creating a Multiple Linear Regression model on the full data set (including the height outliers). For this first model, we calculated an R<sup>2</sup> value of 50.785%. This indicates that our model accounts for about half of the variance in the data set.

We then created a second Multiple Linear Regression model on a data set that excludes the four height outliers that were found in the Visualizing Parameters stage. This model produced an R<sup>2</sup> value of 51.986%. This is indicates that removing the four outliers improved the model's performance.

We next tried using the Min-Max Scaler from SciKit-Learn instead of the Standard Scaler. This resulted in an R<sup>2</sup> value of 51.952%. Since it did not produce an appreciable improvement in the model's performance, we returned to using the Standard Scaler for the rest of the models.

Since we weren't obtaining strong R<sup>2</sup> values with the linear regression models, we decided to try other types of supervised regression models. 

### K Nearest Neighbors
The first non-linear model that we tried was a k-Nearest Neighbors Regressor. This regression model requires an additional step of determining the most appropriate value of k to use for the regression. We graphed the testing accuracy for odd values of k from 1 to 19, and the graph appeared to level off around k = 7. We decided to try using k = 5, 7, and 9 to see if any of them produced better results than the multiple linear regressors.

For k = 5, we got an R<sup>2</sup> value of 51.442%. For k = 7, we got an R<sup>2</sup> value of 51.758%. For k = 9, we got an R<sup>2</sup> value of 51.844%. None of the k-Nearest Neighbor models performed better than the multiple linear regression models. Additionally, the k-Nearest Neighbors models appeared to overfit the data, since the R<sup>2</sup> values for the training data set were significantly higher than the R<sup>2</sup> values for the testing data set.

### Support Vector Regression
A score of ***0.5443***. Better, but still not very good.

### Random Forest Regressor
***0.5533***. Getting there, but not something we could work with.

### Neural Network
We ran several tests with a neural network, adding hidden layers and more epochs along the way, but the test scores still ranged from only ***0.5117*** to ***0.5778***.

### Keras Tuner
*TBD*

## Results

The tests proved that our data would be either unable to be tested or would be unreliable to run a linear regression model. Therefore, we are unable to make a proper prediction.

## Recreate The Results
> 1. Clone the repo
> 2. Open Google Colab
> 3. Import the `Abalone_Age_Prediction.ipynb` file
> 4. Run the cells in the colab notebook in order

## Thanks
We would like to thank our instructor, Dom LaBella, for his excellent instruction, patience, and guidance. We would like to thank our TAs, Chris Howard, Colin Barquist, and Nick Buller for their encouragement and troubleshooting expertise. We appreciate the scientists who originally compiled this data set, and we recognize the many abalone who died for the acquisition of the data.