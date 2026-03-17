# Capstone : Credit Card Fraud Detection Predictive Models

This dataset is from https://www.kaggle.com/code/gpreda/credit-card-fraud-detection-predictive-models

Dataset Information copied from Kaggle -

The datasets contains transactions made by credit cards in September 2013 by european cardholders. This dataset presents transactions that occurred in two days, where we have 492 frauds out of 284,807 transactions. The dataset is highly unbalanced, the positive class (frauds) account for 0.172% of all transactions.

It contains only numerical input variables which are the result of a PCA transformation.

Due to confidentiality issues, there are not provided the original features and more background information about the data.

Features V1, V2, ... V28 are the principal components obtained with PCA; The only features which have not been transformed with PCA are Time and Amount. Feature Time contains the seconds elapsed between each transaction and the first transaction in the dataset. The feature Amount is the transaction Amount, this feature can be used for example-dependant cost-senstive learning. Feature Class is the response variable and it takes value 1 in case of fraud and 0 otherwise.

**Understanding the Features:** Features V1, V2, ... V28 are the principal components obtained with PCA; The only features which have not been transformed with PCA are Time and Amount. Feature Time contains the seconds elapsed between each transaction and the first transaction in the dataset. The feature Amount is the transaction Amount, this feature can be used for example-dependant cost-senstive learning. Feature Class is the response variable and it takes value 1 in case of fraud and 0 otherwise.

**use CRISP DM Model for this assignment**

<img width="382" height="369" alt="image" src="https://github.com/user-attachments/assets/f7bbd63f-5b5d-4700-aa3a-83410d37438e" />

**DATA Understanding

Class Imbalance Barchart**

<img width="597" height="463" alt="image" src="https://github.com/user-attachments/assets/0bcfd540-42b1-49cf-8d4e-69b29ecf05df" />

**Scatter Plot Amount Vs Fraud**
<img width="593" height="432" alt="image" src="https://github.com/user-attachments/assets/fc34ae06-d917-4b90-84a3-43641b566782" />
Observation : Based on scatter plot above we can see that fraudulant transactions amount is always less than 5000
Based on above scatterplot lets explore transaction amount destribution by class

<img width="597" height="435" alt="image" src="https://github.com/user-attachments/assets/f602e36c-f79b-4a68-8def-49c3cd6fddca" />
