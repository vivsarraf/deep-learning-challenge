### 21. deep-learning-challenge # AlphabetSoupCharity Funding Predictor

## Overview
### The goal of this project is to create an algorithm using machine learning and neural networks to predict whether applicants will be successful if funded by the fictional non-profit foundation, Alphabet Soup.
----------------------------
----------------------------

## Process
We were given a CSV file which contained more than 34,000 organizations that have received funding from the fictional foundation along with several columns of metadata about each organization. I read the csv file into Jupyter note book using pandas.

## PREPROCESSING<br>
I preprocessed the data by:
* dropping non-beneficial columns,
* finding the number of data points for each unique value for each of the columns that had more than 10 unique values - APPLICATION_TYPE and CLASSIFICATION,
* choosing a cutoff point of 528 and 1883, respectively, to bin rare categorical values together into a new value called "Other",
* using `pd.get_dummies()` to convert categorical data to numeric,
* dividing the data into a target array (IS_SUCCESSFUL) and features arrays,
* applying the `train_test_split` to create a testing and a training dataset,
* and finally, using `StandardScaler` to scale the training and testing sets

The resulting data included 44 features. The target variable (y) was IS_SUCCESSFUL. The data was split into training and test subsets.

## COMPILING, TRAINING, AND EVALUATING THE MODEL<br>
The model was required to achieve a target predictive accuracy higher than 75%. I made three official attempts using machine learning and neural networks. They all resulted in the same accuracy rate – right around 73.31-73.40%, so a little short of the required target accuracy.

Results from each model attempt are detailed below:

# ATTEMPT 1<br>
The first attempt resulted in an <b>accuracy score of 73.32%. This was the highest accuracy score of the three models.</b> This means that 73.32% of the model’s predicted values align with the dataset’s true values.

The hyperparameters used were:
* layers = 2
  * layer1 = 8 neurons : activation function = ‘relu’
  * layer2 = 5 neurons : activation function = ‘relu'
* epochs = 100

![Model 1 Accuracy Plot](Resources/Model1_accuracy.png)

# ATTEMPT 2<br>
 This attempt resulted in an <b>accuracy score of 73.40%.</b> This means that 73.40% of the model’s predicted values align with the dataset’s true values.

The hyperparameters used were:
* layers = 2
  * layer1 = 10 neurons : activation function = ‘relu’
  * layer2 = 10neurons : activation function = ‘relu’
 
* epochs = 100

![Model 2 Accuracy Plot](Resources/Model2_accuracy.png)

# ATTEMPT 3<br>
For my third and final attempt.Changed the activation function for second layer.This attempt resulted in an <b>accuracy score of 73.31%.</b> This means that 73.31% of the model’s predicted values align with the dataset’s true values.

The hyperparameters used were:
* layers = 2
  * layer1 = 20 neurons : activation function = ‘relu’
  * layer2 = 20 neurons : activation function = ‘tanh’
 
* epochs = 100

![Model 3 Accuracy Plot](Resources/Model3_accuracy.png)


## Summary
In the three attempts I made, the model was unable to achieve a target predictive accuracy higher than 75%. Hypertuning resulted in virtually no improvement. I would consider using another classification model to see if it is better at predicting whether applicants will be successful if funded by Alphabet Soup.


