# Machine Learning Engineer Nanodegree
## Capstone Proposal
Pawel Wisniewicz  
05-06-2020

## Proposal

### Domain Background

Nowadays by paying by card, by online shopping, by using our smartphones, by surfing the internet we are leaving a digital footprint. More and more data is collected, due to that, there are new possibilities for businesses to explore that data and find some insights which can boost their effectiveness. Marketing is one of the fastest-growing fields utilizing big data opportunities.

### Problem Statement

The main challenge is to improve the selection of people for targets of a marketing campaign.

### Dataset and Inputs

This dataset in a real-life customer's data delivered by Alvato Financial Solutions. They provide 4 datasets:
-	Demographics information about the general population in Germany. 891,211 samples with 366 features.
-	Demographics information about customers of the sales company in Germany. 191,652 samples with 369 features.
-	Demographics information about people targeted with the campaign. 42,982 samples with 367 features.
-	Demographics information about people targeted with the campaign. 42,833 samples with 366 features.

The general population dataset includes different information such as age, gender, personal profile, purchase information, state of possession, and many other features provided for all individuals.  
In the customers' dataset, there are the same features plus 3 additional 'CUSTOMERS_GROUP', PRODUCT_GROUP', and 'ONLINE_PURCHASE'. These extra columns provide more precise information about every customer profile.  
The third dataset contains information about targeted people along with additional column 'RESPONSE' indicating whether each person was attracted by the campaign or not. The remaining features are the same.  
The last dataset includes test data, the same columns like in the third dataset except for 'RESPONSE' column, for this portion of data we need to predict how likely each person is to become a new customer.  

There are also two excel files:
-	List of attributes and descriptions segmenting them by the type of attribute e.g. Person, Household, etc.
-	A detailed list of attributes with their values described.

### Solution Statement

Utilizing available data about each person will help to identify prospective customers more efficiently, reducing the number of failures.

### Benchmark Model

The best model will be selected based on the k-fold cross-validation results. This way data is trained and tested on various observations, so the best model must perform good enough on all test sets to reduce bias.
<p align="center">
  <img src="https://render.githubusercontent.com/render/math?math=Err(x) = Bias^{2} %2BVariance %2BIrreducible Error">
</p>

### Evaluation Metrics

Model performance is measured using AUC which results in the ratio between True positive and False positive rates. The data is unbalanced because there are many more individuals who were targeted and did not respond.
<p align="center">
  <img src="image/roc_auc.png">
</p>

### Project Design

First, I will start with data exploration, I will use lists of attributes to understand demographics information. Then I will analyze each column to explore the scale of measurements whether this is a nominal, ordinal, or numeric (interval, ratio) scale. It is also worth to check how much missing values are there.  

Then using unsupervised machine learning techniques, I will perform clustering on the general population dataset before that I need to use various techniques for dimensionality reductions such as PCA. After segmentation, I will select the most important features which can help to determine which individuals of the general population are more likely to become a new customer.  

Then I will apply supervised machine learning techniques to find the best model which will be used to predict the probability of becoming a new customer for each individual in the test dataset.  
Before selecting the best model I will perform features engineering to reduce noise. Then checking the correlation between features and using recursive feature elimination I will select the most important features to input into models. Too many features may lead to the model being less accurate, particularly on unseen data. This is because the model can be overfitted. Next, I will perform k-fold cross-validation to select the best performing model. Then using grid search I will train several models across different hyperparameters and select the model with the highest AUC.
