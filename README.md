# Predicting The Sales In Retail Business 

![Shutterstock_2011099340](https://github.com/hayasalman/Supermarkets-Sales-Predictions-Regression/assets/71796909/eb33196a-bce0-4ede-9573-68a22bf1657f)

## Overview 

In today's world, understanding what role certain properties of a product play and how they affect the sales is imperative to any retail business. The essential aim of this project is to predict the future sales and help in getting an idea about future demands that can help with inventory management, and answering questions such as : which market types that contribute most of the sales and figures out which  potential reasons led to such good sales in that market type, while we find out which the market types need more attention and how we can possibly improve it, and what’s the aspect (or the feature) that directly influences the sales for all the market.

## About The Dataset

- In total, this dataset has 8,523 observations and 12 features, except it has some missing/nulls that need to be handled before doing any kind of analysis/modeling.
- Data source stored as CSV file and can be accessed through this link : [Dataset](https://github.com/hayasalman/Supermarkets-Sales-Predictions-Regression/blob/main/SupermarketSalesData.csv)

## Coding
-  Python Integrated Development Environment (IDE) : Jupyter Notebooks.

   **Packeges used** 
  * **pandas - numby** : used for data manipulation.
  * **matplotlib - seaborn** : used for data visualtion.
  * **statsmodels** : used for any kind of statistical analysis (hypothesis tests).
  * **sklearn** : used to any preprocessing steps required before feeding the dataset into the machine learning algorithm,
    training the dataset in ML models, and to evaluate the performance of the models.

    ## Approaches & Methodologies
    
-  Performed a quick overview about the dataset like the dataset shape , data types, and detected any missing values. Therefore, if there were any problems associated within the dataset, it 
   should be handled before any kind of investigations.

   * within this dataset, there are some data issues need to be fixed :

     1- inconsistent values in item fat column: by replacing any lower-case/shortcuts values by uniform correct format for both kinds of fat.

     2- handling the missing/null values in the outlet size column : by observing any kind of patterns that are related to the missing values.

     3- remove unnecessary variables in the dataset that don't add any value to the analysis like identifiers columns.

### **Feature Engineering** since machine learning designed to accept only the numeric values, we replaced the outlet establishment year by outlet age.Also, that help us to reduce the categorical dimensions that we need to handle in the dataset.

- Performed exploratory data analysis (EDA) : univariate analysis, and bivariate analysis that will help us to describe and summarize the dataset characteristics, identify associations between 
  the variables (which really crucial to the regression), recognize any patterns within the dataset, reveal insights, or even detect the if there are any abnormalities in this dataset .
  
- Prepared data before modeling by : define the independent variables and target variable, encoding categorical variables by creating dummy variables, scaling the numerical variables
  to be in the same range, and finally split our dataset into train-test datasets
  **(train dataset size : 70% - test dataset size : 30%)**.

  ## Modeling
  
In order to solve this regression problem which consist of predicting the future sales, we need training our data on machine learning 
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
     - Error terms/residuals should be normally distributed, otherwise, confidence intervals may become too wide or narrow. Once the confidence interval becomes unstable, it leads to
       difficulty in estimating coefficients based on the minimization of least squares.

## Performance Evaluation & Draw Conclusions

In terms of determining which of the models have the best performance results and will be used as a final solution.
And as it's regression task we will be using these following metrics that embedded within sklearn package or we can use user-defined function to compute the results:

1. **RMSE** (Root Mean Squared Error): the value must be as small as possible.
2. **MSE** (Mean Squared Error) : the value must be as small as possible.
3. **MAPE** (Mean Absolute Percentage Error) : the value must be as small as possible.
4. **R-Squared** : it shows how much of the variance we can explain of the target variable (Sales). Therefore , the value should be as high as possible.
5. **Adj. R-Squared** :it's almost the same as the R-Squared and it should be as high as possible. The small difference between these two metrics is: every time you add a new feature to a model, the R-squared increases, even if the newly added feature is insignificant. It never declines. Whereas Adjusted R-squared increases only when the new feature is significant and affects the target variable.

### **Some models need to hypertuning its parameters to avoid overfitting the training dataset when we train our model before making any predictions, and to accomplish this task we used GridSearch within sklearn.**

   **This screenshot of the final performance metrics table :**
   
   ![reg perf](https://github.com/hayasalman/Supermarkets-Sales-Predictions-Regression/assets/71796909/0b8d5153-1fb3-4b08-92a2-36f5c4389f79)

   **Conclusion : after comparison between these multiple models performance results** 

   - In terms of accuracy measurement of the predictions, the best RMSE measure is for the tuned random forest regressor model
   and gradient boosting regressor which have the lowest RMSE.
   - In terms of variation, the best models are the tuned random forest regressor and gradient boosting regressor which are able
     to ***explain ~74% of the variation in the data***.

     So, we conclude that : **Tuned Random Forest Regressor and Gradient Boosting Regressor** give the best performance for this dataset so far.
 
   ##  Business Insights & Recommendations 

  **Linear Model Equation**
  
  log (item_outlet_sales) = 4.6357 + 1.9438 item_market_price + 1.9600 * outlet_type_Supermarket Type1 + 1.7918 * outlet_type_Supermarket Type2 + 2.5030 * outlet_type_Supermarket Type3

  ### **interpreting the linear equation**

  *From the above equation, we can interpret that, with one unit change in the variable **item_market_price**,the outcome variable, i.e., log of **item_outlet_sales** 
  increases by 1.9438 units. So, if we want to increase the sales, we may want to store higher market price items in the high visibility area.*
  
  *On average, keeping other factors constant, the log sales of stores with type Supermarket type 3 are 1.4 (2.5030/1.7918) times the log sales of stores with type 2 and 1.27 (2.5030/1.9600) 
   times the log sales of those stores with type 1.*
  
  - **Insight 1 discovered from the linear models**
    
     - It becomes clear to us that large stores of supermarket type 3 have more sales than other types of outlets.
       So, we want to maintain these good sales and for the remaining outlets we may want to make strategies to improve the sales, such as : providing better
       customer service, better training for store staff, providing more visibility of the items that have high market price , etc.

- **Insight 2 discovered from the non-linear models**
  
  ![DT improtance](https://github.com/hayasalman/Supermarkets-Sales-Predictions-Regression/assets/71796909/3ea93f38-6786-463f-85ee-b64ed662c3c1) ![bagging_importance](https://github.com/hayasalman/Supermarkets-Sales-Predictions-Regression/assets/71796909/2d74904c-e4fe-43a0-b569-7e2407eeaa3b)

*As seen above, the market price of items is the most important variable which affects the sales of the outlets, as outlets where the high item market prices tend to have a higher sales.*
  
- With the linear models we observed that the outlets in the supermarket type 3 have higher sales than the other outlets. However, with non-linear models we also came up with another interesting insight that is that the outlets of type supermarket type 1 where the outlet size is small have sales from items of the high market prices than other types of outlets. Known that: high market prices of the items can lead to increase the sales volume, hence, in order to improve the sales or maintain a good sales we suggest to pay attention to give more visibility of the items that have high market price to attract the customers to buy it.


### **Reference**
[Predicting The Sales In Retail Business Project File](https://github.com/hayasalman/Supermarkets-Sales-Predictions-Regression/blob/main/Supermarkets%20Sales%20Predictions%20.ipynb)
  
   

   


    
