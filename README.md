# Project Description

Hello there :wave:
I hope this project finds you well!

In this project, I will create a machine learning model using the kNN algorithm. I will not choose the best model; instead, I will demonstrate that my algorithm works accurately. Furthermore, I will compare the RMSE and R-square values of unmasked and masked data using Linear Regression.


**Objective**

To confirm whether masking data will result in no alteration of the RMSE and R-square values.

**Used Model**
1. Linear Regression

# Steps

1. Data Overview
2. Data preprocessing
3. Exploratory Data Analysis
4. Testing Linear Regression with Masking Data

## 1. Data Overview

- `Gender` - Gender
- `Age` - Age
- `Family Members` - Number of Family Members
- `Insurance Benefits` - Clients who made claims.

**Conclusion of Data Exploration Stage**

1. The column names are not standardized.
2. The Age column has a float data type. This column will be converted to an integer data type.

## 2. Pre-Processing Data

In general, `gender` does not seem to influence `insurance_benefits`, but `age` and `family_members` appear to have a correlation with `insurance_benefits`.

## 3. Exploratory Data Analysis
#### 1. Identify clients similar to a specific client's criteria. This task will facilitate the company's marketing efforts.

**Analysis Result**
1. Does non-scaled data affect the kNN algorithm? If it does, how does it affect it?
- Yes, when data is not scaled, the results will be the same (regardless of the metric used). Therefore, the results might be inaccurate due to differences in the scales used in each column. For example: age and income have different scales (age = years, income = dollars). In calculations, it is important to maintain a consistent scale as much as possible.

2. How similar are the results you obtained from the Euclidean metric compared to when you used the Manhattan distance metric (regardless of whether there is scaling)?
- The results are quite similar when using both distance metrics (whether scaling the data or not). More specifically, with scaled data, the results are more different.

#### 2. Predict whether new clients are likely to file an insurance claim. Is the predictive model better than a dummy model's predictions?

**Analysis Result**
The kNN model has a better F1 score compared to the dummy model.

#### 3. Predict the potential amount of insurance claims a new client might receive using a linear regression model.

**Analysis Result**
1. The RMSE and R2 values in both the `MyLinearRegression` and `LinearRegression` (sklearn library) models are the same.
2. By applying the linear regression formula, Sure Tomorrow can create its own custom class with accurate results.
3. A good RMSE value is close to 0. With a value of 0.36, it can be considered that both models have good performance (below 0.5).
4. The R2 value is categorized as strong if it's greater than 0.67. With a result of 0.65, the R2 value falls into the moderate (fair) category.

#### 4. Protect clients' personal data (data masking) without compromising the model from previous tasks

**Analysis Result**
There are differences between the data before transformation (masking data) and the data after transformation. This is because the process of creating the variable P (as a constant) uses random values. If the process is good, then the original data and the data restored to its original state should be the same.

#### 4. Proving the Functionality of Masking Data with LR Model

**Analysis Result**
1. The way to relate $w$ and $w_P$ is by multiplying them by the same matrix.
2. The significance of regression quality when measured with RMSE is that RMSE is usually used for data with fluctuating values, making it suitable for comparing various regression models. Additionally, RMSE is used when the magnitude of the error has significant implications.

## 4. Testing Linear Regression with Masking Data

**Result:**
The RMSE value in the LinearRegression model with or without masking is the SAME.

This proves that certain data masking will not affect the prediction of linear regression values, and the predicted values will remain unchanged from the original results.
