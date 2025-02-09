# Diabetes Risk Prediction: via SEMMA Stats Framework
A exploration with Regularized Logistic Regression

This repository documents a project where I explore statistical machine learning concepts, focusing on binary classification using regularized logistic regression. The project serves as means of gaining experience with the SEMMA (Sample-Explore-Modify-Model-Assess) methodology in a real-world dataset.

## Dataset
The dataset used in this project comes from the [UCI Machine Learning Repository](http://archive.ics.uci.edu/ml/datasets/Early+stage+diabetes+risk+prediction+dataset). It contains 520 observations and 17 columns, collected via direct questionnaires from patients at Sylhet Diabetes Hospital in Bangladesh. The target variable (`class`) indicates whether a patient has a positive diabetes diagnosis.

## Workflow
This side project loosely follows the SEMMA framework and involves the following steps:

### 1. Exploratory Data Analysis (EDA)
- Inspecting Variable types, possible outliers, descriptive statistics, and other possible concerns.
- Checking the frequency distribution of the target variable, Diabetes Risk: `class`. And inspecting if this this an unbalanced dataset.
- Checking for missing values.

### 2. Variable Screening
- Explore the marginal (bivariate) relationships between the predictors and the target variable (`class`), the exact type of tool depends on predictor type:
  - continuous predictors will need a parametric two-sample t-test.
  - categorical predictors will use the Chi-squared test of independence.
Note: I'm setting high threshold of alpha = 0.25 in order to try and remove some unimportant predictors.

### 3. Data Partitioning
Split dataset into sets with a 2:1 ratio. So, the training set will constitute ~67% and testing ~33%.

### 4. Logistic Regression Modeling
- Train a regularized logistic regression model (LASSO) on the training data. Using 10-fold cross validation, I will find the 'best' tuning parameter lambda.
- Find the most important variables that result from the 'best' model.

### 5. Model Performance Assessment
- Evaluate the final logistic regression model on the test dataset.
- Present an ROC curve and calculate the area under the curve (AUC) to accurately assess performance on unseen data.

## Results
- You can see the results in the rendered .pdf file of my r script.