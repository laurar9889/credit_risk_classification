# Module 20 Report

## Overview of the Analysis

In this section, describe the analysis you completed for the machine learning models used in this Challenge. This might include:

* Explain the purpose of the analysis.
The purpose of this analysis was to evaluate a model based on loan risk, using the historical lending activity that can identify the creditworthiness of borrowers.
* Explain what financial information the data was on, and what you needed to predict.
The financial information of each user had the size of the loan, what was its interest rate, what the borrower income was per year, the percentage of debt to income, number of accounts, derogatory marks against the borrower and the total debt.
I needed to predict the loan risk status of each borrower, using the logistics regression model which will have 0 or 1 as an outcome (0 for "low-risk", 1 for "high-risk" status)

* Provide basic information about the variables you were trying to predict (e.g., `value_counts`).
I was trying to predict the loan status: high-risk, low-risk. This is a combination of different analysis and comparisons, such as total income versus total debt, how much of that income the user actually owe (loan size and interest rate combined), how well the borrower perform with the financial institution(s) by analyzing the derogatory marks and what are the number of accounts that exist for each individual.

* Describe the stages of the machine learning process you went through as part of this analysis.
This model had 4 main steps:
1. Ensure the data was cleaned and preprocessed before applying any model. There was no need to clean-up the dataset as it was given in a dataframe structure. a dataframe was created using Pandas library, followed by sseparating labels and variables.
2. train the dataframe: I split the data into 2; first part for training the data, second part for  testing the data. 
3. Validate: Using the test data, I could validate how well the model was able to predict the labeled data.
4. Predict: Using logistic regression model, I was able to predict the  creditworthiness of borrowers and check with the classification report, how relaible my model was. 

* Briefly touch on any methods you used (e.g., `LogisticRegression`, or any other algorithms).
Sklearn was  the library mainly used for this analysis, working with confusion matrix, classification report, train test split and linear regressionLogistic regression module was used, as part of the sklearn library.


## Results

Using bulleted lists, describe the accuracy scores and the precision and recall scores of all machine learning models.

* Machine Learning Model 1:
    * Description of Model 1 Accuracy, Precision, and Recall scores.
    * Precision: the model can predict 100% of the low-risk borrowers, supported by 18,759 rows of information analyzed. the level of precision on the high-risk borrowers is lower, with 87%. 
    * Accuracy: We have an accuracy of 94% on loan risk prediction. 
    * recall score: for class 0, the model shows that it captures 100% of the actual low-risk loans. for class 1, the model captures 89% of the actual high-risk loans.



## Summary

Summarize the results of the machine learning models, and include a recommendation on the model to use, if any. For example:

* Which one seems to perform best? How do you know it performs best?
* Does performance depend on the problem we are trying to solve? (For example, is it more important to predict the `1`'s, or predict the `0`'s? )

If you do not recommend any of the models, please justify your reasoning.

The Logistic regression model seems to perform really well for predicting the low-risks loans, as shown by the classification results. (100% precision). I would recommend it if the user runs the model and has a "low-risk" result.
However, it does not perform at the same accuracy ratio with the high-risk loans. That ratio is at 87%. I would not recommend the model to be used as loan decision maker if the result that is throwing is at "high-risk". I would recommend further analysis (case by case) because there are other variables that need to be consider, which is not being considered with 100% accuracy, causing the model to be less than 100% precise. There could be a big impact of running the model itself and letting the model make decisions on its own. I personally would not appreciate to be evaluated by algoritms only, and not have the opportunity to be have a human being addressing my case, checking the other 13% of chances that I have to be right, as the algoritm is capturing a recall of 89% in those cases.
