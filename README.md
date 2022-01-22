This repository is just to show ans teach some of the Supervised ML models used to solve Classification problems.

# Customer Segmentation in Banking

In this repository I'll classify the customers of a bank, in order to know who should be targeted by a certain type of marketing. This will allow the company to select precisely to whom they should sell each type of service.

This segmentation will be done through the use of different Machine Learning models, such as the following:
- Logistic Regression
- KNN (K-Nearest Neighbour)
- Naive Bayes
- SVM
- Random Forest
- AdaBoost
- XGBoost

---

### Background:

A banking institution has been running several marketing campaigns through telephone calls for several years. With all the data collected, this company would like to know if they can improve the efficiency of these campaigns by pinpointing more accurately the customers to whom the phone calls are focused.


### Task:

In this project, the objective is to predict which customers are likely to contract the service based on certain attributes.


### [Feature Descriptions](https://archive.ics.uci.edu/ml/datasets/Bank+Marketing):

**Input variables:**
#### Bank client data:

1 - age (numeric)

2 - job : type of job (categorical: 'admin.','blue-collar','entrepreneur','housemaid','management','retired','self-employed','services','student','technician','unemployed','unknown')

3 - marital : marital status (categorical: 'divorced','married','single','unknown'; note: 'divorced' means divorced or widowed)

4 - education (categorical: 'basic.4y','basic.6y','basic.9y','high.school','illiterate','professional.course','university.degree','unknown')

5 - default: has credit in default? (categorical: 'no','yes','unknown')

6 - housing: has housing loan? (categorical: 'no','yes','unknown')

7 - loan: has personal loan? (categorical: 'no','yes','unknown')

#### Related with the last contact of the current campaign:

8 - contact: contact communication type (categorical: 'cellular','telephone')

9 - month: last contact month of year (categorical: 'jan', 'feb', 'mar', ..., 'nov', 'dec')

10 - day_of_week: last contact day of the week (categorical: 'mon','tue','wed','thu','fri')

11 - duration: last contact duration, in seconds (numeric). Important note: this attribute highly affects the output target (e.g., if duration=0 then y='no'). Yet, the duration is not known before a call is performed. Also, after the end of the call y is obviously known. Thus, this input should only be included for benchmark purposes and should be discarded if the intention is to have a realistic predictive model.

#### Other attributes:

12 - campaign: number of contacts performed during this campaign and for this client (numeric, includes last contact)

13 - pdays: number of days that passed by after the client was last contacted from a previous campaign (numeric; 999 means client was not previously contacted)

14 - previous: number of contacts performed before this campaign and for this client (numeric)

15 - poutcome: outcome of the previous marketing campaign (categorical: 'failure','nonexistent','success')

#### Social and economic context attributes

16 - emp.var.rate: employment variation rate - quarterly indicator (numeric)

17 - cons.price.idx: consumer price index - monthly indicator (numeric)

18 - cons.conf.idx: consumer confidence index - monthly indicator (numeric)

19 - euribor3m: euribor 3 month rate - daily indicator (numeric)

20 - nr.employed: number of employees - quarterly indicator (numeric)

**Output variable (desired target):**
21 - y - has the client subscribed a term deposit? (binary: 'yes','no')

---
### Methodology

  - **Data Understanding:** 
    - Check the type of values of each column and shape of the DataFrame 
    - Check if the df has NaN values
    - Plot histograms to check all the numerical features (Distributions and Outliers)
    - Check the number of categories per categorical feature and take a closer look at features with many categories
  
  - **Data preparation and preprocessing:**
    - Drop "duration" feaure (Explained in the notebook)
    - Define X and Y
    - Split the data into train and test data: train_test_split (sklearn.model_selection)
    - Split numerical and categorical features
    - Pipeline: we created pipelines for both the categorical (incl. OneHotEncoder) and the numeric data (incl. StandardScaler) as well as a preprocessor (ColumnTransformer) to combine these two pipelines
    
  - **Superviced Machine Learning Algorithm:**
    - Compare several models, just to check how each of them works.
      - Logistic Regression: Cross validaion with No Penaly, L1 (Lasso) and L2 (Ridge).
      - KNN (K-Nearest Neighbour)
      - Naive Bayes
      - SVM
      - Random Forest
      - AdaBoost
      - XGBoost
      
    Surprisingly the best scoring model was Logistic Regression, and one of the main reasons could be because it was the only one to which Hyperparameter Tuning was applied.
    
    - Feature Importance: 
    
    Trees based models like RandomForest, XGBoost, etc. provide us feature importance based on the training. A very relevant aspect if you want to know more about how each of the features affects.
    
<p align="center">
  <image src="https://github.com/wanaguirre/Customer-Segmentation-in-Banking/blob/main/Notebooks/images/feature_importance.jpg"/>
</p>


---

### Future steps:
- Hyperparameter Tuning
- Feature Interpretation (SHAP)
- Provide a conclusion based on what has been learned, about this business problem.
