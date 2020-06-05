# Machine Learning Engineer Nanodegree
## Capstone Proposal
Pawel Wisniewicz  
05-06-2020

## Proposal

### Domain Background



### Problem Statement
The main question is how to accquire new clients more efficiently

### Dataset and Inputs

This dataset in a real life customer's data delivered by Alvato Financial Solutions. They provide 4 datasets:
- demographics information about general population in Germany. 891,211 samples with 366 features.
- demographics informations about customers of the sales company in Germany. 191,652 samples with 369 features.
- demographics informations about people targeted with the campaign. 42,982 samples with 367 features.
- demographics informations about people targeted with the campaign. 42,833 samples with 366 features.

The general population dataset includes different informations such as: age, gender, personal profile, purchase information, 
state of possesion and many other features provided for all individuals.  
In the customers dataset there are exactly the same features plus 3 additional 'CUSTOMERS_GROUP', PRODUCT_GROUP' and 'ONLINE_PURCHASE'.
These extra columns provide more precise information about each individual's customer profile.  
Third datast contains informations about targeted people along with additional column 'RESPONSE' indicating whether each person was
attracted by the compaign or not. Remaining features are exactly the same.  
The last dataset includes test data, without 'RESPONSE' column, for which we need to predict how likly each person is 
to become a new customer.
