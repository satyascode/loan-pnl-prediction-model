
Loan Profit and Loss Prediction ML model
----------------------------------------------------
This project builds a machine learning model to predict loan profit or loss percentage based on a set of features. 

In this project we will explore various regression models levergaing data analysis, feature engineering, and model tuning methods to achieve high accuracy in profit or loss prediction.  


Project Overview
----------------------------------------------------
The primary goal of this project is to take a raw financial dataset and transform it into a robust machine learning model. 
Objective
Develop a machine learning model to accurately predict the profit or loss (PnL) for individual loan products. 


Dataset
----------------------------------------------------
The process will involve several key stages: 
- Exploratory Data Analysis (EDA): To understand the data and identify patterns.
- Determine the success metrics: To translate the business goals into ML problem

Data Analysis: 
Initial exploration revealed a continuous target variable and all independent variables as continuous, with no missing values.


Methodology
----------------------------------------------------
Approach
An ensemble-based modeling approach using XGBoost was selected due to suitability for structured data, ability to handle non-linear relationships, and robustness to data skewness. 


Feature Selection
----------------------------------------------------
Feature importance analysis was conducted to identify the most impactful variables, resulting in a reduced feature set for the final model.


Model training and evaluation
----------------------------------------------------
Model Training & Tuning: 
A benchmark model was established, followed by hyperparameter tuning using Grid Search to optimize performance.

Model Evaluation: 
Multiple models were evaluated based on key metrics like RMSE (Root Mean Squared Error) and R-squared, with a focus on minimizing prediction error and explaining the variance in PnL.


Results
----------------------------------------------------
observations: 
- All models performs relatively well, both in terms of target percent point and overfitting
- On average, predications are accurate less than 1% points
- Tuned_Model with lowest RMSE and highest r2 
    - gives <u>7.5%</u> better (test set) accuracy than the second-best model
- Tuned_Model has smaller feature list, more trees* 
- *Adaptive tuning could be considered for reducing complexity in terms of trees)

Recommendations:
- For business usecase where profit/loss margin are in the range of 20%(+/-) 
    - less than 1% point could be considered acceptable (pending approval) 
    - business tolerance for margin of error
- The difference between tuned model vs next best could be interpreted in thousands $$  
- Model: Tuned_Model
  - Predictions within 1.02% points 
  - Explains 99.6% of PnL variance
  - Less complex w/ smaller feature set 
  - Optimal choice for production inference full or a/b testing


How to use
----------------------------------------------------
TBD (inference point to be created)

Dependancies
----------------------------------------------------
Install following packages before running (refer to requirements.txt)


Final thoughts
----------------------------------------------------
Follow-up business questions 
- What is the existing model or method's accuracy? 
- How does 1% prediction error in terms of business dollars converts 
- What accuracy level would be considered acceptable 

Model constraints 
- During uncertain micro economics or market conditions
- Retraining after every 6 months would be ideal
