# Marketing-Campaign-Analysis

# Predict Marketing Campaign Analysis by using Machine Learning

## Problem
Customer response rate to campaigns that has been done too low.

## Goals
Make marketing campaigns that are right on target (response rate and high profits).

## Objective
Create a machine learning model that is able to predict whether a customer will respond to the next campaign or not.

## Steps
1.  Exploratory Data Analysis (Descriptive, Univariate, Multivariate)
2.  Data Preprocessing
 
    a. Handle Missing Value 
    
    b. Feature Extraction;
    - Create Age column from Year_birth column 
    - Created the Dependents column from the Kidhome and Teenhome columns
    
    c. In the Education column, the 2n Cycle category is changed to Master 
    d. Perform Label Encoding in the Education column 
    e. In the Marital Status column, Change multiple categories that are ambiguous and have the same meaning. 
    f. Perform One Hot Encoding (OHE) on the Marital Status column  
    g. Feature Selection h. Handle outliers with Yeo-Johnson transformation 
    i. Split Data Train and Test 
    j. Handle Class Imbalance with Random Oversampling
3.  Train model with 5 different algorithms classification
4.  Business Recommendation

## Analisis Data
1.Most of the customers who received the Response (last marketing campaign) came from the year of birth 1970-1975.
![alt text](fig/insight1.png?raw=true)

2.the newer the customer makes a purchase, the more likely the customer is to receive the company's last marketing campaign (Response).
![alt text](fig/insight2.png?raw=true)

## ML Modeling
Before train the model, split the data into train set & test set (size is 30%). Trained the model with 5 different algorithms and evaluated them with ROC AUC score because the data is imbalanced and focuses on positive and negative labels.
![alt text](fig/modelling.png?raw=true)

The result we choose the Random Forest model as the best model because the data is non-linear and the gap between train and test from the ROC AUC score is the smallest among the other models. Then, because the ROC AUC score still indicates overfitting, hyperparameter tuning will be performed on the Random Forest model.

Following are the results after hyperparameter tuning:
![alt text](fig/model after tuning.png?raw=true)

## Business Insight & Recomendations
The features that most influenced customers in responding to the last campaign were:
- Low recency: customers who have recently made a purchase
- High MntGoldProducts: customers who buy gold products in large quantities
- High NumWebVisitsMonth: customers who frequently visit the company's website, where customers can make purchases through the company's website

Recommendation:
- Target campaigns at customers who have recently made a purchase
- Target campaigns at customers who buy a lot of gold products or conduct campaigns related to gold products
- Conducting campaigns through the company's website
