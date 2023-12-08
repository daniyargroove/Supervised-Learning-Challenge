# Module 12 Report Template

## Overview of the Analysis

In this section, describe the analysis you completed for the machine learning models used in this Challenge. This might include:

* Explain the purpose of the analysis.
The purpose of the analysis is to make predictions by using various techniques such as predictions of logistic regression model with original training data and predictions of a Logistic regression model with resampled training Data.

* Explain what financial information the data was on, and what you needed to predict.
There was a csv file from financial institution (bank) with a varios data from its borrowers and given loans.

* Provide basic information about the variables you were trying to predict (e.g., `value_counts`).


* Describe the stages of the machine learning process you went through as part of this analysis.
Machine Learning Process basically divided into 3 following steps:
1. Creation a logistic regression model with the original data. 
Here we instantiate the logistic regression model. (Create the model)

2. Then, we need to fit our model using training data by using "fit" method with train data. (Fit the model)

3. Make a prediction using the testing data by using "predict" method with test data. (Make the predictions)

* Briefly touch on any methods you used (e.g., `LogisticRegression`, or any resampling method).

## Results

Using bulleted lists, describe the balanced accuracy scores and the precision and recall scores of all machine learning models.

* Machine Learning Model 1:
  * Description of Model 1 Accuracy, Precision, and Recall scores.
According to the confusion matrix, classification report, and balanced accuracy score: I can conclude, that logistic regression model performed strongly positive.
1. Precision and Recall values for loan status=1 (the one which we need, when the loan has a high risk of defaulting) are 86% and 92%. That is not quite good, because only 86 percent of all predicted results were correct and 92% of all predicted results were genuinely true.
On the other hand, if we take a look at loan_status=0 (the one when the loan has no risk of defaulting) precision and recall values are practically excellent.
2. Overall, accuracy score is 99, which is a good indication about how well the model is likely to perform in real life.


* Machine Learning Model 2:
* Description of Model 2 Accuracy, Precision, and Recall scores.
According to the confusion matrix of random oversampled data, new classification report, and new balanced accuracy score: 
I can conclude, that logistic regression model with oversampled data performed a bit better and more precise than with original data.

1. Precision value for loan status=1 (the one which we need, when the loan has a high risk of defaulting) are 86% which is almost the same as earlier, but Recall value increased from 92% to 100%.

In conclusion, the model trained with random oversampled data performs slightly better overall. 
It has a similar balanced accuracy score to the original data model, but outperforms in terms of recall and F1-score for class 1, and has fewer false negatives. 

## Summary

Summarize the results of the machine learning models, and include a recommendation on the model to use, if any. For example:
* Which one seems to perform best? How do you know it performs best?
* Does performance depend on the problem we are trying to solve? (For example, is it more important to predict the `1`'s, or predict the `0`'s?) 

If you do not recommend any of the models, please justify your reasoning.


In conclusion, the model trained with random oversampled data performs slightly better overall. It has a similar balanced accuracy score to the original data model, but outperforms in terms of recall and F1-score for class 1, and has fewer false negatives. However, it does have more false positives, which could be a concern depending on the specific application and the cost associated with false positives.

When interpreting these results, it's important to consider the trade-off between precision and recall. If false positives are a major concern, a model with higher precision may be preferred. Conversely, if missing out on true positives could lead to serious consequences, a model with higher recall may be more suitable.

Moreover, the choice of the threshold value for classifying the output probabilities from the logistic regression model can significantly impact the model's performance. This threshold should be selected based on the specific problem context and the relative costs of false positives and false negatives.

Finally, it's worth noting that while accuracy is a commonly used metric, it can be misleading for imbalanced datasets. This is because it does not distinguish between the numbers of correctly classified examples of different classes. Therefore, it can show a high value if the model simply predicts the majority class for all examples. In contrast, the balanced accuracy, precision, recall, and F1-score provide more nuanced information about the model's performance on each class, making them more suitable for evaluating models trained on imbalanced datasets 