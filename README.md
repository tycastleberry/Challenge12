# Credit Risk Analysis Report

## Overview of the Analysis

The purpose of this analysis is to a analyze a dataset of historical lending activity from a peer-to-peer lending services company to build two Logistic Regression models that can identify the creditworthiness of borrowers. The first model will use the original dataset, and the second model will use an oversampled version of the original dataset to increase the number of high-risk loan labels in an attempt to give more accurate predictions. The ultimate goal of both models is to predict whether a loan should be classified as healthy or high-risk, which is given in the "loan_status" column of the dataset. This column is the labels for the Logistic Regression algorithm. The rest of the columns serve as the features for the model. 

After loading the data and instantiating the features and labels of the dataset, the first step was to check the value_counts for the labels. The original data was found to have only 2500 instances of high-risk loans vs 75036 instances of healthy loans. After splitting the data into a training set and a test set using train_test_split, the next step is to instantiate a model and fit the model to the training data. After the model has been fit, it is then used to make predictions based on the test data. The results are then analyzed by generating an accuracy score, a confusion matrix, and a classification report that contains metrics such as precision and recall. 

After the first model is built, a second model was then started to investigate if a dataset with more balanced labels would create a more accurate model. To balance the labels, RandomOverSampler was used on the training data. This produced labels that contained 56271 instances of both healthy and high-risk loans, thus "balancing" the value_counts of each label compared to the original dataset. The Logistic Regression model is then fit to the resampled training data and predictions are made using the test data. To conclude, the accuracy score, confusion matrix, and classification report are generated for the second model to use in comparison to the original model.

## Results

Using bulleted lists, describe the balanced accuracy scores and the precision and recall scores of all machine learning models.

* Machine Learning Model 1:
  * Description of Model 1 Accuracy, Precision, and Recall scores.



* Machine Learning Model 2:
  * Description of Model 2 Accuracy, Precision, and Recall scores.

## Summary

Summarize the results of the machine learning models, and include a recommendation on the model to use, if any. For example:
* Which one seems to perform best? How do you know it performs best?
* Does performance depend on the problem we are trying to solve? (For example, is it more important to predict the `1`'s, or predict the `0`'s? )

If you do not recommend any of the models, please justify your reasoning.
