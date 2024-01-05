# Project4_OSU

## Overview
The purpose of this analysis is to create a model that will predict the median value of homes on a California block, given certain criteria about the block. This process was completed in a Jupyter Notebook file using Python. In addition, a dashboard was created for visualization of the data. This dashboard is held in a Tableau file.

## Data Preprocessing
Historical data is retreived from https://www.kaggle.com/datasets/camnugent/california-housing-prices/data. The dataset contains the following information related to homes within California blocks: 
- longitude
- latitude
- median age of homes
- total rooms
- total bedrooms
- population
- households
- median income
- median house value
- ocean proximity

The dataset is cleaned by removing incomplete rows and outliers. It is then binned based on column values. This changes numerical data to categorical data in new columns. Next, the categorical data is expanded to columns with indicator values using the pandas.get_dummies function.

Target columns are assigned to the variable y. These target columns were created by binning the median house values. Feature columns are assigned to the variable x. These feature columns were created by binning all original columns, excluding the median house values. The feature columns also include the original columns of the dataset.

The target and feature variables are split into testing and training datasets. The testing and training feature variables are then scaled.

## Compile, Train, and Evaluate the Model
The final model is compiled using the following combination of layers, neurons, and activiation functions:
- Hidden Layer 1
    * Neurons: 40
    * Activation Function: ReLu
- Hidden Layer 2
    * Neurons: 40
    * Activation Function: ReLu
- Hidden Layer 3
    * Neurons: 40
    * Activation Function: ReLu
- Output Layer
    * Neurons: 10
    * Activation Function: SoftMax

The model is trained using the scaled feature training data and the target training data, over 100 epochs.

The model is evaluated by applying it to the scaled feature testing data and comparing the results to the target testing data. The model evaluation consistently presents an accuracy score of 88% or higher.

## Tableau Dashboard
The dashboard contains the following visuals:
- A map where the user can select different zipcodes. The zipcodes selected will determine the data to be used for the following bar graphs:
    * Median Income Frequency
    * Median House Value Frequency
- A scatter plot that compares the average median income to the average median household value
- A pie graph that shows the percentage of data that falls into the various ocean proximity categories.
- A bar graph that shows the average median house value based on the various ocean proximity categories.
