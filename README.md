# Abalone Age Prediction with Supervised Machine Learning

## Group 3: Jacob Douthett, Sam Espe, Alan Jallah, Jae Neuharth

## Overview
This project experiments with supervised machine learning algorithms to attempt to produce a model that could determine the age of an abalone based on macroscopic physical characteristics. We created a website to display our process and results, hosted on (GitHub Pages)[https://d0rtilla.github.io/AbaloneAgePredictionProject/].

## To Recreate the Models
1. Clone this repository to your local computer.
1. Open (Google Colaboratory)[http://colab.research.google.com)] in a web browser.
1. Upload the `Abalone_Age_Prediction.ipynb` to the Google Colaboratory environment.
1. Run the cells to create the desired model(s).
    - *Note*: All models require the first two sections ("Extract and Transform Data" and "Visualizing Parameters") to be run before the model itself can be run.
    - *Note*: If the model of interest resides within a collapsible segment of similar models, the first group of cells in that segment must be run. These cells set up the infrastructure on which the subsequent models rely.
    - The data is pulled in from an AWS S3 bucket. If that does not work for whatever reason, the CSV of the data is located in the `Resources` folder, or at the following URL: [https://archive.ics.uci.edu/ml/datasets/Abalone].