# Predicting The Sales In Retail Business 

![Shutterstock_2011099340](https://github.com/hayasalman/Supermarkets-Sales-Predictions-Regression/assets/71796909/eb33196a-bce0-4ede-9573-68a22bf1657f)

## Overview 

In today's world, understanding what role certain properties of a product play and how they affect the sales is imperative to any retail business.
The essential aim of this project is to predict the future sales and help in getting an idea about future demands that can help with inventory management, 
and answering questions such as : which branches generate most of the sales. also, hopefully the data will help us to figure out the reasons that leads to such good sales in that market type, 
while we find out which the branches need more of our attention and how we could possibly improve them, and what’s the aspect (or the feature) that directly influences the sales for all the market.

## About The Dataset

- In total, this dataset has 8523 observations and 12 features, except it has some missing/nulls that need to be handled before doing any kind of analysis/modeling.
- Data source stored as CSV file and can be reached through this link : [Dataset](https://github.com/hayasalman/Supermarkets-Sales-Predictions-Regression/blob/main/SupermarketSalesData.csv)

## Coding
-  Integrated Development Environment (IDE) : Python Jupyter Notebookes

   **Packeges used** 
  * **pandas - numby** : used for data manipulation.
  * **matplotlib - seaborn** : used for data visualtion.
  * **statsmodels** : used for any kind of statitistical analysis (hypothesis tests).
  * **sklearn** : used to any preprocessing steps required before feeding the dataset into the machine learning algorithm,
    training the dataset in ML models, and to evaluate the performance of the models.

    ## Approches & Methodologies
    
-  Performed a quik overview about the dataset like the dataset shape , data types, and detect any missing values, therefore, if there were any problems associated within the dataset,
  it should be handled before any kind of investigations.

   * within this dataset, there are some data issues need to be fixed :

     1- inconsistent values in item fat : by replacing any lower-case or shortcuts values by uniform correct format for both kinds of fat.

     2- handling the missing/null values in the outlet size column : by observing any kind of patterns that are related to the missing values.

     3- remove unnecessary variables in the dataset that didn't add any value to the analysis like identifiers columns.

**Feature Engineering** since machine learning designed to accept only the numeric values, we replaced the outlet establishment year by outlet age.
Also, that will help us to reduce the categorical dimensions that we need to handle in the dataset.

- Performed exploratory data analysis (EDA) : univariate analysis, and bivariate analysis that will help us to describe and summarize the dataset characteristics,
  and identify relationships between the  variables (which really crucial to the regression), or recognize any patterns within the dataset.
- Prepared data before modeling by : define the independent variables and target variable, encoding categorical variables by creating dummy variables, Scaling the numerical variables
  to have the same range, and finally split dataset into train-test datsets.

  ## Modeling
  
In order to solve this regression problem that consist of predicting the future sales, we need training our data on machine learning 
algorithms for regression.Thus, we called out for sklearn functions: 
  
  1. Linear Regression.
  2. Ridge Regression.
  3. Decision tree regressor.
  4. Random Forest regressor.
  5. Bagging regressor.
  6. Adaboost Regressor.
  7. Gradient Boosting Regressor.

  ### **But before that we should checking the linear regression assumptions**
  
  1. No Multicollinearity.
  2. Mean of residuals should be 0 (or close to it).
  3. No Heteroscedasticity.
  4. Linearity of variables.
  5. Normality of error terms.
    
