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
    
-  Performed a quick overview about the dataset like the dataset shape , data types, and detected any missing values. Therefore, if there were any problems associated within the dataset, it should be handled before any kind of investigations.

   * within this dataset, there are some data issues need to be fixed :

     1- inconsistent values in item fat : by replacing any lower-case or shortcuts values by uniform correct format for both kinds of fat.

     2- handling the missing/null values in the outlet size column : by observing any kind of patterns that are related to the missing values.

     3- remove unnecessary variables in the dataset that didn't add any value to the analysis like identifiers columns.

### **Feature Engineering** since machine learning designed to accept only the numeric values, we replaced the outlet establishment year by outlet age.
Also, that will help us to reduce the categorical dimensions that we need to handle in the dataset.

- Performed exploratory data analysis (EDA) : univariate analysis, and bivariate analysis that will help us to describe and summarize the dataset characteristics,
  identify relationships between the  variables (which really crucial to the regression), or recognize any patterns within the dataset, and uncover insights.
- Prepared data before modeling by : define the independent variables and target variable, encoding categorical variables by creating dummy variables, Scaling the numerical variables
  to have the same range, and finally split dataset into train-test datasets
  **(train dataset size : 70% - test dataset size : 30%)**.

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

  ### **Before that we need to checking the linear regression assumptions**
  
  1. No Multicollinearity.
     - We will use variance inflation factor VIF to check if there is multicollinearity (strong correlation between two independent variables) in the data,
       variables that have a VIF score >5 will be dropped and it will be treated as we progress till all the variables have a VIF score <5.
  3. Mean of residuals should be 0 (or close to 0).
  4. No Heteroscedasticity.
  5. Linearity of variables.
  6. Normality of error terms.
     - Residuals should be normally distributed, otherwise, confidence intervals may become too wide or narrow. Once the confidence interval becomes unstable, it leads to
       difficulty in estimating coefficients based on the minimization of least squares.

## Performance Evaluation 

In terms of determining which of the models have the best performance results which will be our consideration as the final solution, and since evaluate a performance
for the regression problem, we will use the following metrics that embedded with sklearn or we will use our user-defined function to compute the results:
1. **RMSE** (Root Mean Squared Error): the value must be as small as possible.
2. **MSE** (Mean Squared Error) : the value must be as small as possible.
3. **MAPE** (Mean Absolute Percentage Error) : the value must be as small as possible.
4. **R-Squared** : it shows how much of the variance we can explain of the target variable (Sales). Therefore , the value should be as high as possible.
5. **Adj. R-Squared** :it's almost the same as the R-Squared and it should be as high as possible. The small difference between these two metrics is: every time you add a new feature to a model, the R-squared increases, even if the newly added feature is insignificant. It never declines. Whereas Adjusted R-squared increases only when the new feature is significant and affects the target variable.

### **Some models need to hypertuning its parameters to avoid overfitting the training dataset when we train our model before making any predictions, and to accomplish this task we used GridSearch within sklearn.**

   **This the final performance metrics table for the seek of comparison between those multiple models :**
   
   ![reg perf](https://github.com/hayasalman/Supermarkets-Sales-Predictions-Regression/assets/71796909/0b8d5153-1fb3-4b08-92a2-36f5c4389f79)

   ## Draw Conclusions & Business Recommendations

   

   


    
