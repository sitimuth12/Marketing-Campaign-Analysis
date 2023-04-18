# Marketing-Campaign-Analysis

# Predict Marketing Campaign Analysis by using Machine Learning

## Problem
Customer response rate to campaigns that has been done too low.

## Goals
Make marketing campaigns that are right on target (response rate and high profits).

## Objective
Create a machine learning model that is able to predict whether a customer will respond to the next campaign or not.

## Steps
1. Exploratory Data Analysis (Descriptive, Univariate, Multivariate)
2. Data Preprocessing 
    a. Handle Missing Value
    b. Feature Extraction;
        - Create Age column from Year_birth column
        - Created the Dependents column from the Kidhome and Teenhome columns
    c. In the Education column, the 2n Cycle category is changed to Master
    d. Perform Label Encoding in the Education column
    e. In the Marital Status column, Change multiple categories that are ambiguous and have the same meaning.
    f. Perform One Hot Encoding (OHE) on the Marital Status column    
    g. Feature Selection
    h. Handle outliers with Yeo-Johnson transformation
    i. Split Data Train and Test
    j. Handle Class Imbalance with Random Oversampling
3. Train model with 5 different algorithms classification
4. Evaluation with confussion matrix
5. Business Recomendation

## Analisis Data
1.Most of the customers who received the Response (last marketing campaign) came from the year of birth 1970-1975.
![alt text](?raw=true)

2.the newer the customer makes a purchase, the more likely the customer is to receive the company's last marketing campaign (Response).
![alt text](?raw=true)

## ML Modeling
Before train the model, split the data into train set & test set (size is 30%). Trained the model with 5 different algorithms and evaluated them with ROC AUC score because the data is imbalanced and focuses on positive and negative labels.
![alt text](?raw=true)

The result we choose the Random Forest model as the best model because the data is non-linear and the gap between train and test from the ROC AUC score is the smallest among the other models. Then, because the ROC AUC score still indicates overfitting, hyperparameter tuning will be performed on the Random Forest model.

Following are the results after hyperparameter tuning:
![alt text](?raw=true)

## Model Evalutaion
![alt text](?raw=true)

By using the confusion matrix, it is obtained that the resulting Random Forest model is very good. We can see the prediction error (purple cells) is very small (top right and bottom left).

## Business Insight & Recomendations
Insight:
- Recency rendah: customer yang baru-baru ini melakukan pembelian
- MntGoldProducts tinggi: customer yang membeli produk emas dalam jumlah yang besar
- NumWebVisitsMonth tinggi: customer yang sering mengunjungi website perusahaan, dimana customer dapat melakukan pembelian melalui website perusahaan

Rekomendasi:
- Menargetkan campaign kepada customer yang baru-baru ini melakukan pembelian
- Menargetkan campaign kepada customer yang banyak melakukan pembelian produk emas atau melakukan campaign yang berhubungan dengan produk emas
- Melakukan campaign melalui website perusahaan
