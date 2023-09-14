# Report

## Overview of the Analysis

#Purpose 
The purpose of this analysis was to build a machine learning model that can predict whether a loan is healthy(0) or has a high risk of defaulting(1) based on finacial features. The analysis aims to assess the performance of a logistic regression model and address class imbalance in the dataset. My process consisted of:

1. Importing Required Modules: 
2. Reading the data 
3. Data Serparation 
4. Checking the Target Class Balance 
5. Train-Test Split 
6. Shaping of Training Data 

Data

The data consists of loan_status as our labels and loan_size, interest_rate, borrower_income, debt_to_income, num_of_accounts, derogatory_marks total_debt for our features. The aim for our data was to predict creditworthiness of borrorwers. A value of 0 under loan_status indicates a healthy loan, where as a 0 indicates a high risk of defaulting.

Variables

The variable being predicted is loan_status as a binary classification task, where:
    - 0 typically represents healthy loan(low risk of defaulting)
    - 1 typically represents high-risk loans(high risk of defaulting)
To assess the class distribution, the code uses 'y.value_counts()', which provides information about how many loans fall into these two categories 

Processes

- Data Loading: The dataset is loaded into a pandas DataFrame
- Data Preprocessing: The data is seperated into features(X) and the target variable(y).
- Train-Test Split: The dataset is split into training and testing sets to evaluate model performance 
- Model Building: A logistic regression model is built and tranined on the training data. 
- Model Evaluation: The model's performance is evaluated using various metrics, including accuracy and confusion matrix
- Class Imbalance Handling: Random oversampling is applied to address class imbalance 
- Rebuilding and Retraining Model: A logistic regression model is re-instantiated  and trained on the resampled training data 
- Reevaluation: The performance of the updated model is assessed using the same evaluation metrics

Methods and Tools 

- Logistic Regression: A logistic regression model is used for binary classifiation. It's a common choice for such tasks
- Train-Test Split: The dataset is split into training and testing subsets to evaluate the model's generalization performance 
- Random Oversampling: Random oversampling is applied using the 'RandomOverSampler' from the 'imblearn' library to address class imbalance. This technique generates synthetic c.   samples for the minority class to balance the class distribution 
- Model Evaluation Metrics: The code uses various metrics to ealuate model performance, including accuracy, balanced accuracy, confusion matrix, and a classification report 


In summary, the analysis aims to build a logistic regression model to predict loan status based on finacial informatio, evaluate its performance, and handle class imbalance using random oversampling. It follows standard machine learning steps, including data preprocessing, model building, evaluation and addressing class imbalance. 

## Results

Machine Learning Model 1

Accuracy Score

The accuracy score for Model 1 is approximately 0.9924. This score represents the overall accuracy of the modelin classifying both healthy and high-risk loans. An accuracy score of 0.99 indicates that the model correctly predicts the loan status for approximately 99% 

Precision Score

Precision is provided for both classes:
  - Precision for "Actual 0" (healthy loans) is 1.00. This means that when the model predicts a loan as healthy, it is corrected 100% of the time for this class
  - Precision for "Actual 1" (high-risk loans) is 0.87. This indicates that when the model predicts a loan as high-risk, it is correct about 87% of the time for this class.

Recall Score

Recall is provided for both classes:
  - Recal for "Actual 0" (healthy loans) is 1.00. This means that the model correctly identifies 100% if all actual healthy loans
  - Recall for "Actual 1" (high-risk loans) is 0.98. This indicates that the model correclty identifies about 89% of all actual high-risk loans. 


Machine Learning Model 2
Accuracy Score

The accuracy score for model 2 is approximately 0.9952. This score represents the overall accuracy of the modelin classifying both healthy and high-risk loans. An accuracy score of 0.9952 indicates that the model correctly predicts the loan status for approximately 99% and performed slighly better than model 1.  

Precision Score

Precision is provided for both classes:
  - Precision for "Actual 0" (healthy loans) is 1.00. This means that when the model predicts a loan as healthy, it is corrected 100% of the time for this class
  - Precision for "Actual 1" (high-risk loans) is 0.87. This indicates that when the model predicts a loan as high-risk, it is correct about 87% of the time for this class. Model 2 performed the same as model 1 when it came to Percision. 

Recall Score

Recall is provided for both classes:
  - Recal for "Actual 0" (healthy loans) is 1.00. This means that the model correctly identifies 100% if all actual healthy loans
  - Recall for "Actual 1" (high-risk loans) is 1.00. This indicates that the model correclty identifies about 89% of all actual high-risk loans. Model 2 performed better than model 1 in this aspect. 

 
## Summary
Both Model 1 and Model 2 show strong overall performance. Model 2 had a higher balanced accuracy as well as better reacll for high-risk loans. 

Performance does in fact depend on the problem we are trying to solve and we have to take into consideration the costs or consequences associated with misclassification. If our shareholder finds it more cirtical to correctly predict high-risk loans (minimizing false neagatives) while accepting false positives, Model 2 with higher recall (0.89) for high-risk loans may be prefered. If a balance between minimizing false positives and false negatives, Model 1 could be considered due to slighly higher percision of (0.8747) for high-risk loans 

Considerations

Model 1 may be more conservative in flagging high-risk loans, reducing the number of potentially risky loans that are missed (false negatives). 
Model 2 may be more agressive in flagging high-loans, which could lead to identifying more risky loans but may also be a result of more false positives. The tradeoff beterrn precision and recall should be carefully  considered when deciding which model is best for practical implications of false positives and false negatives 

In conclusion, the choice between Model 1 and Model 2 depends on the problem context and the relative importance of correctly predicting high-risk loans. Both models exhibit strong performance overall, and the final decision should be made considering the specific goals and consequences associated with the task. 
