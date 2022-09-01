# Credit Risk Analysis:

We are helping a company called Fast Lending which is asking us to help create a machine learning model to predict credit risk on credit card loans. They want us to accurately predict non-performing loans(NPL), which occur when the borrower has not made a scheduled payment for a specified period. These loans attain this status usually when there is no payment made within a 90 to 180-day period, depending on the company's policy. From prior experience, we are aware that once a loan goes into NPL status the likelihood of the debtor repaying it in full goes down substantially. In most cases, financial companies have a lot more loans in good standing, or else the company would go under and would not be able to operate. The same applies to our company Fast Lending, we have a lot more loans in good standing in comparison to non-performing loans. This will mean that our machine learning model will have to deal with an unbalanced dataset. In order to accomplish this request, I will be using various machine learning models to find the most accurate prediction, summary statistics, and data processing techniques. In the image below I wanted to give an example of various ways that non-performing loans can hurt the economy. 

![NPL](https://i.ibb.co/5X0LR3N/NPL.png)

----
## Results: 

I used 6 different types of machine learning algorithms in order to provide an accurate response. I analyzed the models' balanced accuracy, precision, and recall scores. We will be using a chart that incorporates the confusion matrix as well as the classification metrics in all 6 machine learning models. The confusion matrix is a technique that is used to summarize the effectiveness of a classification algorithm. The reason we use a confusion matrix is that the classification model can often be misleading, for example, if we have an unequal number of observations in each class or if we have more than 2 classes. A classification metric is a number that will measure the performance of our machine learning model and it usually ranges from 0 to 1 (1 being a perfect model).


The image below shows what a confusion matrix and classification metric look like. The boxes with a white background are the confusion matrix and the pink boxes with formulas in them are the classification metrics. We will use this information throughout all six machine learning models. 

![ConfusionMatrix](https://i.ibb.co/XS5zV1z/Confusion-Matrix.png) 

### What are TP, FP, FN, TN? 

#### True Positive 
- occurs when the classification model predicts positive and the actual class was positive. This means that the classification model has been predicted correctly. 

#### False Positive 
- occurs when the classification model predicted positive, but in reality, the actual class was negative. These cases are usually referred to as Type I Errors in statistics. 

#### False Negative: 
- occurs when the classification model predicted negative, however, the actual class was positive. These types of cases are usually referred to as Type II errors in statistics

#### True Negative: 
- occurs when the classification model predicted negative and the actual class was negative. This means that the classification model has predicted correctly

###  Models: 
We will use the classification report to produce the following percentages for both High-Risk loans and Low-Risk loans. 

**(1) Naive Random Sampling:**
![Naive RS](https://i.ibb.co/jfS8fSw/Naive-Random-Oversampling.png)

High-Risk Loans: 
- Balanced Accuracy = 65%
- Precision/Positive Predicted Value = 2% 
- Recall/Sensitivity = 61% 

Low-Risk Loans:
- Balanced Accuracy = 65%
- Precision/Positive Predicted Value = 82% 
- Recall/Sensitivity = 69% 

**(2) SMOTE Oversampling:** 
![Smote](https://i.ibb.co/Rzr5XZk/SMOTE-Oversampling.png)
High-Risk Loans: 
- Balanced Accuracy = 65% 
- Precision/Positive Predicted Value = 1%
- Recall/Sensitivity = 61% 

Low-Risk Loans:
- Balanced Accuracy = 65%
- Precision/Positive Predicted Value = 100%
- Recall/Sensitivity = 69% 

**(3) Undersampling using Cluster Centroids Algorithm:**
![ClusterCentroids](https://i.ibb.co/y5CLBd7/Undersampling-with-Cluster-Centroids-Algorithm.png)
High-Risk Loans: 
- Balanced Accuracy = 52% 
- Precision/Positive Predicted Value = 1%
- Recall/Sensitivity = 69% 

Low-Risk Loans:
- Balanced Accuracy = 52%
- Precision/Positive Predicted Value = 100%
- Recall/Sensitivity = 40% 

**(4) Combination of oversampling and undersampling using SMOTEENN:**
![Smoteenn](https://i.ibb.co/K72TnGr/Combination-over-and-under-Sampling-with-SMOTEENN.png)
High-Risk Loans: 
- Balanced Accuracy = 67% 
- Precision/Positive Predicted Value = 1% 
- Recall/Sensitivity = 80% 

Low-Risk Loans:
- Balanced Accuracy = 67% 
- Precision/Positive Predicted Value = 100%
- Recall/Sensitivity = 56% 

**(5) Balanced Random Forest Classifiers:**
![BRFC](https://i.ibb.co/yVkYgBD/Balanced-Random-Forest-Classifier.png)
High-Risk Loans: 
- Balanced Accuracy = 78% 
- Precision/Positive Predicted Value = 3% 
- Recall/Sensitivity = 70% 

Low-Risk Loans:
- Balanced Accuracy = 78%
- Precision/Positive Predicted Value = 100%
- Recall/Sensitivity = 87% 

**(6) Easy Ensemble AdaBoost Classifier:**
![AdaBoost](https://i.ibb.co/PrkFXnt/Easy-Ebseb-nbke-Adabiist-Ckassufuer.png)
High-Risk Loans: 
- Balanced Accuracy = 93% 
- Precision/Positive Predicted Value = 9%
- Recall/Sensitivity = 92%

Low-Risk Loans:
- Balanced Accuracy = 93%
- Precision/Positive Predicted Value = 100%
- Recall/Sensitivity = 94% 
--------

## Summary:
With respect to this specific scenario, I must say that sensitivity is more important than precision. The reason I came to this conclusion is that it would be catastrophic for the company if we have a large number of NPLs (Non-performing Loans) that went undetected. With a high sensitivity percentage this means that people who default on their repayment (high-risk loans) will be identified correctly. However, due to such an aggressive algorithm, we will also deny loan applications for people who are low risk as well. This is the cost of doing business, it is better to lose a few low-risk clients, rather than having high-risk clients receive loans inadvertently. If we were to focus on perfect precision, we would be accepting numerous high-risk clients. With this in mind, it is obvious that the Easy Ensemble Adaboost classifier will be the most preferable machine learning algorithm that would be of use for our clients with a sensitivity percentage of 93% for high-risk loans. Our next best machine learning model for this scenario would be the Balanced Random Forest classifier with a sensitivity percentage of 70% for high-risk loans. In order to determine the rate of success on the Easy Ensemble Adaboost classifier in terms of denying high-risk loans, one could take the following year's dataset and compare the actual number of defaulted loans. This would provide valuable insight for the company for the following year and it gives us a chance to see how well our machine learning algorithm has performed. 
