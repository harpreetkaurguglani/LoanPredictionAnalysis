# LoanPredictionAnalysis
Classification problem where we have to predict whether a loan would be approved or not.

## Problem Statement
A company wants to automate the loan eligibility process(Y/N) on real time basis on the detail provided while filling online application form.
These details are Gender, Marital Status, Education, Number of Dependents, Income, Loan Amount, Credit History and others.

## Identification of Problem Type
It is a classification problem where we have to predict whether a loan would be approved or not. In a classification problem, we have to predict discrete values based on a given set of independent variable(s). Since the problem involves a huge amount of risk the selection of an appropriate model is crucial not only with respect to the high accuracy but also the ease in the level of understanding the model and the inferential segment.

## Data Preprocessing
Overall 614 rows and 13 columns in train_df dataset and 367 rows and 12 columns in test_df dataset.
There are certain interesting figures in the dataset. We can see that the maximum amount for which the loan has been applied is 700k and the minimum been 9k. The applicants have a little surprising level of income of minimum 150k and maximum 81000k.

There are missing values in the dataset which needs careful attention. There are 86 missing values. We first fill up the categorical missing values by sub stituting the highest occurence value from the categorical values.There are blank fields in Gender, Married, Dependents and Self_Employed. There are NAs in LoanAmount, Loan_Amount_term and Credit_History.

Furthermore, the average value of Credit_history variable is 0.8422. That's unbelivable to know as the variable has value of 1 for customers who have credit history and 0 otherwise. The response variable, loan status is not balanced with a ratio of about 2:1

The glm shows that the model is not just an intercept model as the Null deviance is reduced a lot as depicted from the residual deviance.

## Summary
Logistics Regression was able to give us an accuracy of 78.87%, which means that we can expect our model to classify correct about 8 observations in every 10.
The best accuracy on public test set is 0.8216216. Applicants with credit history not passing guidelines mostly fails to get approved, probably because that they have a higher probability of not paying back. Most of the time, applicants with high income, loaning low amount is more likely to get approved, which makes sense, those applicants are more likely to pay back their loans.

The Random Forest suggests that the variable Credit_History, totalincometrain, LoanAmount are crucial variables. The variables Married, Education, Gender and Self_Employed can be omitted from the analysis. The Lasso model also concludes by evaluating 5variables for low MSE. The error rate with Random forest is 19.11% and the accuracy for the validation set is 81%.

Chosen Model & Scoring
Although the accuracy for the decision tree is better, I'm choosing the random forest tree model. The reason is that the difference in accuracy slightly differ between the two models. 
