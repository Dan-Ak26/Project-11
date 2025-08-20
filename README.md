## Predicting Exercise Quality with Random Forests
## Overview

This project is part of the Johns Hopkins University Data Science Certification (Machine Learning).
The objective is to build a machine learning model that predicts the manner in which participants performed a weight lifting exercise.
The dataset comes from accelerometer sensors on the belt, forearm, arm, and dumbbell of study participants.

Our goal is to accurately classify the exercise quality into five classes (A–E) using sensor data and submit predictions for the test set.

## Data

Training data: pml-training.csv

Testing data: pml-testing.csv

These datasets include motion sensor readings and the target variable classe (exercise classification) in the training set.

## Methods

1. Data Cleaning

Removed columns with near-zero variance and excessive missing values.

Dropped irrelevant identifiers (timestamps, usernames, etc.).

2. Data Splitting

Partitioned the training data into:

80% training set

20% validation set

3. Modeling

Used Random Forests (ranger + caret) with 200 trees.

Evaluated using confusion matrix and accuracy on the validation set.

4. Variable Importance

Ranked predictors by importance to better understand which sensor measurements contributed most.

5. Prediction

Applied the trained model to the 20-case test dataset.

Exported predictions for submission in .txt files (one per case).

## Results

Validation Accuracy: >99%

Top predictors: roll_belt, yaw_belt, pitch_forearm, magnet_dumbbell_z

Test Set Predictions: Generated successfully and submitted in the required format.

## Conclusion

Random Forests provided a robust and accurate model for this classification problem. The high validation accuracy indicates strong generalization, 
and the test predictions were produced with high confidence.

This project demonstrates the full data science workflow:

data acquisition,

preprocessing,

model training & tuning,

evaluation,

and final prediction generation.

## Repository Structure
Project-11/
│
├── pml-training.csv      # Training dataset
├── pml-testing.csv       # Test dataset
├── Pred_train_test.Rmd   # R Markdown analysis
├── README.md             # Project documentation
└── submissions/          # Prediction text files for test cases

## Requirements

R (≥ 4.0)

Packages: caret, ranger, tidyverse, dplyr, readr

Install with:

install.packages(c("caret", "ranger", "tidyverse", "dplyr", "readr"))
