# Classification -- Predicting Customer Churn

## Introduction

Customer Churn Prediction for a Telco

![newplot (5)](https://user-images.githubusercontent.com/57757966/232258075-b343ede6-f017-4c0f-b4b5-02aceb7bc9f6.png)

Introduction
It is a common phenomenon for customers to leave one company for another due to one reason or the other. This is referred to as customer churning or turnover. Business operators have become conscious of the project and therefore are taking measures to deal with the situation. This is a classification problem that requires the services of a data professional to analyze and predict the churn rate in the company and the possible churn in the future. That is the aim of this project.

Data Overview
The dataset contained 7043 rows and 21 columns. The columns are (a) the customer ID — for identifying the individual customer of the company. (b) gender — whether a customer is a male or female. (c) Senior Citizen — if a customer is aged or young. (d) Partner — if a customer has a life partner or is single. (e) Dependent — if the customer has a dependent or not. (f) tenure — the total month a customer has been with the company. (g) Phone Services— if the customer enjoys phone services or not. (h) Multiple Lines — if a customer uses more than one line. (i) Internet Services — Customer has internet services at his disposure or not. (j) Online Security — whether or not online services are at a customer's disposal. (k) Online Backup — if a customer has backup services or not. (l) Device Protection — if a customer has device protection services or not. (m) Tech Support — whether or not a customer use tech support service. (n) Streaming TV — if a customer has TV streaming services. (o) Streaming Movies — if a customer streams a movie or not. (p) Contract — whether a month or year’s term of service the customer has with the company. (q) Paperless Billing — whether the customer has paper billing or not. (r) Payment Method — the kind of payment method the customer uses. (s) Monthly Charges — the amount of month the customer pays to the company every month. (t) Total charges — the total amount the company has charged a customer. (u) Churn — if a customer has left the company or not.

Collection of Data
This section talks about the dataset — how it was manipulated to obtain quality data for better analysis. The process includes.

(a) modules importation: we imported different modules and libraries for; the performance of mathematical operations, data manipulations, graphs, and visualizations, handling missing values, Feature Encoding and scaling, class imbalance, and Machine learning modeling

(b) The Data

The shape of the dataset is 7043 rows representing the number of customers and 21 columns. The data type has 1 float, 2 integers, and 18 objects. The total memory used by the dataset is 1.1 megabytes.

Issues identified with the dataset include.

The Total Charges column is expected to be either an integer or float, but it was an object datatype.
The Total Charges column has 11 missing values.
gender and tenure started with a small letter making them look different from the other column names.
How to handle the issues

We will convert Total Charges to float data type.
We will replace non-numeric characters with the appropriate values.
impute the missing values with the mean.
convert Senior Citizen to object.
Rename gender to Gender and tenure to Tenure.
After the issues are resolved,

Numerical columns = {Tenure, Monthly Charges, Total Charges}
Categorical columns = {gender, Senior Citizen, Partner, Dependents, Phone Service, Multiple Lines, Internet Service, Online Security, Online Backup, Device Protection, Tech Support, Streaming TV, Streaming Movies, Contract, Paperless Billing, Payment Method}
Target column = Churn (we are targeting churn because the project seeks to predict customers in the future)

Hypothesis and Questions
Hypothesis helps us to investigate the relationship that exists between different variables in our dataset and guides us on the path to predict factors that cause customer churn in the company. We formulated the following hypothesis to guide us in our analysis.

Null Hypothesis H0: Customer satisfaction directly affects customer churning rate.

Alternative Hypothesis H1: Customer satisfaction has no direct effect on customer churn.

Based on the hypothesis we came up with the following questions

What is the churn rate of Telco?
Which category of customers is likely to churn?
Do Senior Citizens pay fewer monthly charges than younger Citizens?
Are customers with Dependents likely to churn?
How do Dependents affect multiple lines?
What is the churn rate of the Telco by gender?
How many customers use different payment methods?
Data processing

This part of the analysis process is about making available clean, quality data so that the accuracy of the prediction will not negatively be affected. We carried the following on the data.

Dropped irrelevant columns.
Misplaced characters were replaced.
Some column names were renamed.
Some columns were converted to their appropriate data type.
Answering the questions
This section answers the questions asked based on the formulated hypothesis.

The Telco’s churn rate

Pie showing the percentage of customers’ churn and Non-churn.
From the graph above, the Telco’s customer churn rate is 27%

2. Which category of customers is likely to churn?





From the numeric columns;

Senior citizens: Customers who are not senior citizens are more likely to churn than customers who are senior citizens.

Tenure: customers who are in their first five months and those that have stayed with the company for about five years have a higher churn rate than those in the mid-tenure.

Monthly charges: Customers who are charged higher monthly charges are less likely to churn than those who have fewer monthly charges.

Total Charges: the higher a customer’s Total Charges the lesser chance of churning and the reverse is also true.

3. Senior Citizen’s monthly charges against younger Citizens


From the graph, Senior Citizens are paid more Monthly Charges than Non-Senior Citizens. Senior Citizens pay around 80 million monthly charges while Non-Senior Citizens pay a little above 60 million Month Charges.

4. Are customers with Dependents likely to churn?


From the graph, a little above 15000 customers of the Telco without Dependents churn while those with Dependent churn below 500. This means that the likelihood of a customer churning is not based on having Dependents.

5. How Dependents affect multiple lines


From the graph, 3390 customers have dependents but do not have Multiple lines. 2971 of the customers have dependents and also have multiple lines and 682 of the customers have dependents but have no phone services. We can conclude that there is no likelihood that customers with dependents will have multiple lines.

6. Churn rate of the Telco by gender?


The above graph shows that 50% of Males and 50% percent of Females make up the total customers of Telco. The rate at which they churn each is around 27%. This shows that both males and females have approximately, equal chances of leaving the Telco for another.

7. Customers with partners and churn


It can be seen from the graph that customers with no partners (1200) churn more than those with partners (669).

8. How many customers use the different payment methods


In the above graph, the different payment methods by the telco and the rate at which customers use them are 22.8% for Mailed checks, Electronic Check is at 33.65%, Bank transfers (automatic) made up 21.6% and credit cards were 21.9%. It means that a slight majority of the customers preferred the electronic check payment method over the other method.

Feature Processing & Engineering
Under this sub-section, our data is further processed to prepare it for modeling.

we checked for duplicated values in the dataset.
imputed the missing values (numerical columns with the mean and most frequent for categorical columns).
split the data set into feature and target variables and then split it into train, and validation datasets.
encoded the categorical features using One Hot Encoder.
Feature Scaling
We Scaled the target value (Churn) to make it easy for models to learn and understand the problem. We fitted and transformed both train and validation datasets.

Machine learning Modeling
Six models were trained on the data to select the model that performed best on the data. Model 1 — Decision Tree, Model 2 — Random Forest, Model 3 — Logistic Regression, Model 4 — K Nearest Neighbor, Model 5 — Support Vector Machine, Model 6 — Naive Bayes.

Model Comparison

0 DecisionTreeClassifier 0.482759

1 RandomForestClassifier 0.518405

2 KNNeighbor 0.600293

3 LogisticRegression 0.553476

4 SVC 0.550769

5 GaussianNB 0.593928

Among the six models trained, K Nearest Neighbor was the best-performing model on the given data with an f1_score of 60%.

Feature Importance


Important features for the decision tree model

The important features of the random forest model

Important features of the entire data sets.
Model Interpretation

Model interpretation
The graph shows that Internet Service Fiber optic has mostly influenced the model positively with a Shapley value of +0.44, followed by the Contract Month to Month with a Shapley value of +0.36. Monthly Charges and Streaming TV Yes, on the other hand, have negatively influenced the model by scoring -0.36 and 0.16 Shapley values respectively. Monthly Charges are however among the top three. The remaining services and factors have a positive influence on customer churning according to Shapley values.

Hyperparameter tuning.
By performing hyperparameter tuning on the models, KNeighbor came out as the best model with an f1_score of 0.6101 or 61%.

Conclusion
In a nutshell, prediction confirms our Null Hypothesis, which states ‘customer satisfaction has a direct effect on customer churning. Proving this, the model prediction using the Shapley plot shows that all the services provided by Telco have positive Shapley values except Monthly Charges and Streaming TV, indicating a positive effect on customer churn rate.
