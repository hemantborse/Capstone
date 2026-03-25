# Capstone : Credit Card Fraud Detection Predictive Models
## Problem Statement:
With Didtal operations growing across the globale in finance and telecom sector , bad actors finding their way to commit frauds , finding such a frauds / anomolies is critical for businesses and enterprises.
This is an approch solve this problem by training an efficient AI / ML model which can be trained on an avaiable dataset from https://www.kaggle.com/code/gpreda/credit-card-fraud-detection-predictive-models.
## Dataset
Dataset Information copied from Kaggle -

The datasets contains transactions made by credit cards in September 2013 by european cardholders. This dataset presents transactions that occurred in two days, where we have 492 frauds out of 284,807 transactions. The dataset is highly unbalanced, the positive class (frauds) account for 0.172% of all transactions.

It contains only numerical input variables which are the result of a PCA transformation.

Due to confidentiality issues, there are not provided the original features and more background information about the data.

Features V1, V2, ... V28 are the principal components obtained with PCA; The only features which have not been transformed with PCA are Time and Amount. Feature Time contains the seconds elapsed between each transaction and the first transaction in the dataset. The feature Amount is the transaction Amount, this feature can be used for example-dependant cost-senstive learning. Feature Class is the response variable and it takes value 1 in case of fraud and 0 otherwise.

**Understanding the Features:** Features V1, V2, ... V28 are the principal components obtained with PCA; The only features which have not been transformed with PCA are Time and Amount. Feature Time contains the seconds elapsed between each transaction and the first transaction in the dataset. The feature Amount is the transaction Amount, this feature can be used for example-dependant cost-senstive learning. Feature Class is the response variable and it takes value 1 in case of fraud and 0 otherwise.

**use CRISP DM Model for this assignment**

<img width="382" height="369" alt="image" src="https://github.com/user-attachments/assets/f7bbd63f-5b5d-4700-aa3a-83410d37438e" />
**
**CRISP-DM Phases Completed as below**
**
**DATA Understanding

Class Imbalance Barchart**

<img width="597" height="463" alt="image" src="https://github.com/user-attachments/assets/0bcfd540-42b1-49cf-8d4e-69b29ecf05df" />

**Scatter Plot Amount Vs Fraud**
<img width="593" height="432" alt="image" src="https://github.com/user-attachments/assets/fc34ae06-d917-4b90-84a3-43641b566782" />
Observation : Based on scatter plot above we can see that fraudulant transactions amount is always less than 5000
Based on above scatterplot lets explore transaction amount distribution by class

<img width="629" height="470" alt="image" src="https://github.com/user-attachments/assets/0768fad9-6f73-4be7-ae58-f11469561f3e" />



**Transaction Time Distribution by Class**

<img width="630" height="470" alt="image" src="https://github.com/user-attachments/assets/fcc096b6-e371-46dd-9724-c34b345d4bf1" />


**Box Plots for V1 to V28 (Fraud Vs Legit)**
<img width="1990" height="1190" alt="image" src="https://github.com/user-attachments/assets/5826c58f-b03d-4acf-aa9f-b47c0f0e31f4" />

**Correlation Heatmap**
<img width="549" height="441" alt="image" src="https://github.com/user-attachments/assets/1628eab1-7339-4b5c-b179-8f0aa51e0dbb" />


<img width="989" height="790" alt="image" src="https://github.com/user-attachments/assets/a74e3fb1-00d7-4784-ba05-3123dd75c086" />


<img width="1589" height="2790" alt="image" src="https://github.com/user-attachments/assets/671bb3c6-1bc7-4692-8153-397bd84a033c" />


<img width="844" height="470" alt="image" src="https://github.com/user-attachments/assets/2247d642-66ee-45bb-91eb-b76b505d017b" />

**After Data Analysis below model were trained and aalysed , corrosponding important features and heatmaps were printed and finally below table was generated :**

<img width="623" height="229" alt="image" src="https://github.com/user-attachments/assets/e14d7d3c-b412-48ae-b019-91bf40cac4fa" />

**Based on this table and KFold Validation results conclusion was made as below :** 

**Classification Metrics used for analysis (some details)**
Accuracy: The overall percentage of correct predictions.
Precision: The proportion of positive predictions that were actually correct.
Recall (Sensitivity): The proportion of actual positive cases that the model correctly identified.
F1-Score: The harmonic mean of precision and recall, used to find a balance between the two.
Confusion Matrix: A table summarizing true positives, true negatives, false positives, and false negatives.
AUC-ROC: A curve that visualizes the model's ability to distinguish between classes at various thresholds.
PR-AUC: This is most important for this case as it is a performance metric used in binary classification to evaluate how well a model balances precision and recall. It is particularly effective for imbalanced datasets where the positive (minority) class is the primary focus,
________________________________________
**Analysis**
Dummy: Predicts nothing as fraud. Accuracy looks great at 99.83% — which is exactly why accuracy is useless here. Catches zero fraud. Everything else must beat this.
Logistic Regression: This is the*** most deceptive*** row in the table. Highest ROC-AUC of all models — but PR-AUC is nearly as low as the Dummy. High recall (0.908) means it catches 90% of fraud — but precision of 0.067 means for every 1 real fraud it catches, it falsely flags 14 innocent transactions. This is risk as too many false alarms will be seen in prod.
**Decision Tree: **Decision Tree has **worse performance **than Logistic Regression. It catches fraud but flags 1 in 27 legit transactions as fraud. Hence Decision Tree not usable in this case.
Both Logistic Regression and Decision Tree are Accuracy Trap
AdaBoostClassifier is a "middle-of-the-pack" performer. It is significantly better than the basic Logistic Regression and Decision Tree models for this task, but it doesn't quite reach the performance level of the top-tier models
LightGBM : has the highest F1-Score (0.874), indicating it has the best balance between catching positive cases (Recall) and being correct when it does (Precision).
Random Forest : is a close second. It is slightly more "conservative" than LightGBM (higher precision, lower recall), meaning it’s very reliable when it predicts a positive, but misses a few more than LightGBM

**Conclusion:**
For current Dataset, LightGBM and Random Forest are best performer/ Winners: with Mean Accuracy of 0.996 -Excellent Performance and range 0.00014 which shows high reliability , LightGBM shows it is highly stable (low variance) across all folds( however class imbalance , data leak and overfitting should be checked) Precision, Recall and F1 score mitigate some of those risks. A balance of finding as many cases as possible without too many false alarms, LightGBM best. If avoiding "false positives" is priority then, Random Forest is slightly better



