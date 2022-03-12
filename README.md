# Credit Risk Analysis Report

## Overview of the Analysis

The purpose of this analysis is to a analyze a dataset of historical lending activity from a peer-to-peer lending services company to build two Logistic Regression models that can identify the creditworthiness of borrowers. The first model will use the original dataset, and the second model will use an oversampled version of the original dataset to increase the number of high-risk loan labels in an attempt to give more accurate predictions. The ultimate goal of both models is to predict whether a loan should be classified as healthy or high-risk, which is given in the "loan_status" column of the dataset. This column is the labels for the Logistic Regression algorithm. The rest of the columns serve as the features for the model. 

After loading the data and instantiating the features and labels of the dataset, the first step was to check the value_counts for the labels. The original data was found to have only 2500 instances of high-risk loans vs 75036 instances of healthy loans. After splitting the data into a training set and a test set using train_test_split, the next step is to instantiate a model and fit the model to the training data. After the model has been fit, it is then used to make predictions based on the test data. The results are then analyzed by generating an accuracy score, a confusion matrix, and a classification report that contains metrics such as precision and recall. 

After the first model is built, a second model was then started to investigate if a dataset with more balanced labels would create a more accurate model. To balance the labels, RandomOverSampler was used on the training data. This produced labels that contained 56271 instances of both healthy and high-risk loans, thus "balancing" the value_counts of each label compared to the original dataset. The Logistic Regression model is then fit to the resampled training data and predictions are made using the test data. To conclude, the accuracy score, confusion matrix, and classification report are generated for the second model to use in comparison to the original model.

## Results

* Model 1 Using Original Data:
  * The model did a great job of predicting the healthy loans and a decently good job of predicting the high-risk loans. The overall balanced accuracy score was 95%. The healthy loans have near perfect predictions for both the precision and recall metrics. The predictions for the high-risk loans had 85% precision and 91% recall. So, for every 100 predictions the model made that a loan would be high-risk, 85 of the predictions were correct to get an 85% precision score. Of the 619 high-risk loans, the model correctly predicted 563 to get a recall score of 91%. Both of these scores are decently good for the model's predictions concerning high-risk loans.

* Model 2 Using Resampled Data:
  * The metrics with the oversampled data improved compared to the model with the original data. The balanced accuracy score is now at 99%. The oversampled model still does a near perfect job of predicting healthy loans. The precision score for predicting high-risk loans was about the same as the original model as it only dropped 1% to 84%, but there was drastic improvement in the recall score for predicting high-risk loans. The model is now predicting the actual high-risk loans at a 99% recall rate, a great improvement over the 91% recall rate with the original data. 

## Summary

Summarize the results of the machine learning models, and include a recommendation on the model to use, if any. For example:
* Which one seems to perform best? How do you know it performs best?
* Does performance depend on the problem we are trying to solve? (For example, is it more important to predict the `1`'s, or predict the `0`'s? )

I would recommend using the second model that utilizes resampled data. Oversampling the data produced a model that increased recall from 91% to 99%, while only sacrificing a 1% decrease in precision from 85% to 84%. With so few of the loans being high-risk, it's crucial for the model to be correct when identifying an actual high-risk loan. By predicting 99% of the high-risk loans correctly, we can be confident that almost all of the high-risk loans are being properly identified. I'd like the model to be tweaked to improve the precision score so that it's correct a higher percentage of the time when identifying a loan as high-risk. However, I don't mind the tradeoff of the model identifying a loan as high-risk when it's not, because the recall score tells me that the model is catching 99% of the actual high-risk loans. The tradeoff of sacrificing some healthy loans to ensure that almost all of the high-risk ones are identified is justified. 