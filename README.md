# Credit-Card-Fraud-Detection

## Dataset
https://www.kaggle.com/datasets/mlg-ulb/creditcardfraud

## What is Credit Card Fraud?
Credit card fraud is when someone uses another person's credit card or account information to make unauthorized purchases or access funds through cash advances. Credit card fraud doesn’t just happen online; it happens in brick-and-mortar stores, too. As a business owner, you can avoid serious headaches – and unwanted publicity – by recognizing potentially fraudulent use of credit cards in your payment environment.

## Three challenges surrounding credit card fraud
It's not always easy to agree on ground truth for what "fraud" means.
Regardless of how you define ground truth, the vast majority of charges are not fraudulent.
Most merchants aren't experts at evaluating the business impact of fraud.

## Problem Statement:
The Credit Card Fraud Detection Problem includes modeling past credit card transactions with the knowledge of the ones that turned out to be a fraud. This model is then used to identify whether a new transaction is fraudulent or not. Our aim here is to detect 100% of the fraudulent transactions while minimizing the incorrect fraud classifications.

## Observations
Very few transactions are actually fraudulent (less than 1%). The data set is highly skewed, consisting of 492 frauds in a total of 284,807 observations. This resulted in only 0.172% fraud cases. This skewed set is justified by the low number of fraudulent transactions.
The dataset consists of numerical values from the 28 ‘Principal Component Analysis (PCA)’ transformed features, namely V1 to V28. Furthermore, there is no metadata about the original features provided, so pre-analysis or feature study could not be done.
The ‘Time’ and ‘Amount’ features are not transformed data.
There is no missing value in the dataset.

## Why does class imbalanced affect model performance?
In general, we want to maximize the recall while capping FPR (False Positive Rate), but you can classify a lot of charges wrong and still maintain a low FPR because you have a large number of true negatives.
This is conducive to picking a relatively low threshold, which results in the high recall but extremely low precision.

## What is the catch?
Training a model on a balanced dataset optimizes performance on validation data.
However, the goal is to optimize performance on the imbalanced production dataset. You ultimately need to find a balance that works best in production.
Resampling the dataset
Essentially this is a method that will process the data to have an approximate 50-50 ratio.
  1. One way to achieve this is by *OVER-sampling*, which is adding copies of the under-represented class (better when you have little data)
  2. Another is *UNDER-sampling*, which deletes instances from the over-represented class (better when he have lot's of data)

## Business questions to brainstorm:
Since all features are anonymous, we will focus our analysis on non-anonymized features: Time, Amount

   1. How different is the amount of money used in different transaction classes?
   2. Do fraudulent transactions occur more often during a certain frames?
   
   
# METHOD
We first fit the following models to the skewed data and compare them -
   1. Random Forest
   2. Artifical Neural Networks
   3. XGBoost
   4. CatBoost
   5. LightGBM
