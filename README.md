# Credit_Card_Default_Prediction
![The best travel credit cards of February 2022 - The Points Guy](https://user-images.githubusercontent.com/87002524/153152962-68033a26-29bf-41d5-8e52-7dd1bca0f7ac.jpg)
##
##
##
# Project Objective : Predicting whether a customer will default on his/her credit card.
# Problem Description:
This project is aimed at predicting the case of customers default payments in Taiwan. From the perspective of risk management, the result of predictive accuracy of the estimated probability of default will be more valuable than the binary result of classification - credible or not credible clients. We can use the K-S chart to evaluate which customers will default on their credit card payments.
#
# Data Description:
### _Basic User Data._
* ID : Unique ID of each client.
* LIMIT_BAL : Amount of the given credit (NT dollar) : it includes both the individual consumer credit and his/her family (supplementary) credit.
* SEX : Gender (1 = male; 2 = female).
* EDUCATION : Qualifications (1 = graduate school; 2 = university; 3 = high school; 4 = others).
* MARRIAGE : Marital status (1 = married; 2 = single; 3 = others).
* AGE : Age of the client (years)
### _History of Past Payment._
Scale for PAY_0 to PAY_6 : (-2 = No consumption, -1 = paid in full, 0 = use of revolving credit (paid minimum only), 1 = payment delay for one month, 2 = payment delay for two months, ... 8 = payment delay for eight months, 9 = payment delay for nine months and above)

* PAY_0 : Repayment status in September, 2005 (scale same as above)
* PAY_2 : Repayment status in August, 2005 (scale same as above)
* PAY_3 : Repayment status in July, 2005 (scale same as above)
* PAY_4 : Repayment status in June, 2005 (scale same as above)
* PAY_5 : Repayment status in May, 2005 (scale same as above)
* PAY_6 : Repayment status in April, 2005 (scale same as above)
### _Amount of Bill Statement._
* BILL_AMT1 : Amount of bill statement in September, 2005 (NT dollar)
* BILL_AMT2 : Amount of bill statement in August, 2005 (NT dollar)
* BILL_AMT3 : Amount of bill statement in July, 2005 (NT dollar)
* BILL_AMT4 : Amount of bill statement in June, 2005 (NT dollar)
* BILL_AMT5 : Amount of bill statement in May, 2005 (NT dollar)
* BILL_AMT6 : Amount of bill statement in April, 2005 (NT dollar)
### _Amount of Previous Payment._
* PAY_AMT1 : Amount of previous payment in September, 2005 (NT dollar)
* PAY_AMT2 : Amount of previous payment in September, 2005 (NT dollar)
* PAY_AMT3 : Amount of previous payment in September, 2005 (NT dollar)
* PAY_AMT4 : Amount of previous payment in September, 2005 (NT dollar)
* PAY_AMT5 : Amount of previous payment in September, 2005 (NT dollar)
* PAY_AMT6 : Amount of previous payment in September, 2005 (NT dollar)
### _Response Variable._
* default payment next month : Default payment (1=yes, 0=no)

### Project summary and results.
As more and more consumers rely on credit cards to pay their everyday purchases in an online and physical retail store, the amount of issued credit cards and the overwhelming amount of credit card debt by the cardholders have rapidly increased. 
Therefore, most financial institutions must deal with the issues of credit card default in addition to credit card fraud.
 
Our objective is to conduct quantitative analysis on credit card default risk by using machine learning models with accessible customer data to assist in predicting the case of customers' default payments in Taiwan.

After cleaning the data and renaming a few variables, in the next step, we began EDA (Exploratory Data Analysis) to understand the relationship between the dependent and the independent variables better and identify the necessary trends in them.
We then split the data into two sets, the train (70%) and the test (30%), and standardized it using Standard-Scaler.

Then we implemented five machine-learning approaches (Logistic Regression, XGB Classifier, KNeighbors Classifier, Random Forest Classifier, ExtraTrees Classifier) to predict the default cases on the provided data; however, most models encountered challenges to resolve the imbalance problem of default cases in data sets. 
To avoid this, we oversampled the data using SMOTE Tomek and observed an increase in the overall performance of the models. 

XG Boost Classifier with SMOTE Tomek gave the best accuracy of 82% but lacked Recall which is crucial in classifying the defaulters, whereas XG Boost with imbalanced data while applying the scale_pos_weight=3.521 provided the best Recall of 64% approx. 
In terms of overall balance, Random Forest Classifier provided the best results.

We also achieved a higher Recall of 80% (approx.) for XG Boost (on imbalanced data) by moving the threshold value (default threshold value=0.5) to 0.3605385.
