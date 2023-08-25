# supervised-learning-challenge

## Overview of the Analysis

Factors considered in the analysis included data on:

* The size of the loan
* The interest rate
* The borrower's income
* The debt to income ratio
* The number of accounts the borrower held 
* Derogatory marks against the borrower
* The total debt

The dataset (77,536 data points) was split into training and testing sets. The training set was used to build an initial logistic regression model (Logistic Regression Model 1) using the LogisticRegression module from scikit-learn. Logistic Regression Model 1 was then applied to the testing dataset. The purpose of the model was to determine whether a loan to the borrower in the testing set would be low- or high-risk. This intial model was drawing from a dataset that had 75,036 low-risk loan data points and 2,500 high-risk data points. 

To resample the training data and ensure that the logistic regression model had an equal number of data points to draw from, the training set data was resampled with the RandomOverSampler module from imbalanced-learn. This generated 56,271 data points for both low-risk (0) and high-risk (1) loans, based on the original dataset.

The resampled data was used to build a new logistic regression model (Logistic Regression Model 2). The purpose of Logistic Regression Model 2 was to determine whether a loan to the borrower in the testing set would be low- or high-risk. The results are summarized below.

## Results

Logistic Regression Model 1:
* Precision: In predicting low-risk loans, the model was 100% precise, though the model was only 85% precise in predicting high-risk loans.
* Accuracy: 94%
* Recall: The model had 99% recall in predicting low-risk loans, but 91% recall in predicting high-risk loans.

Logistic Regression Model 2:
* Precision: In predicting low-risk loans, the model was 100% precise, though the model was only 84% precise in predicting high-risk loans.
* Accuracy: 99%
* Recall: The model had 99% recall in predicting both low-risk and high-risk loans.

## Summary

Logistic Regression Model 2 is less likely to predict false negative results. However, based on the confusion matrices for each model, Logistic Regression Model 2 predicted slightly more false positives (low-risk when it was actually high-risk).

Logistic Regression Model 2 had fewer false predictions of the testing data overall and would be the best model to use based on the high accuracy and recall of this model.
