# Salary-Predictions-of-Data-Professions
Salaries in the field of data professions vary widely based on factors such as experience, job role, and performance. Accurately predicting salaries for data professionals is essential for both job seekers and employers.


## Introduction

This project involves predicting salaries for employees based on various features such as experience, age, designation, etc. The approach includes rigorous data preprocessing, feature engineering, model comparison, and deployment into an interactive application.

## Project Objectives

- **Exploratory Data Analysis**
- **Data Preprocessing**
- **Feature Engineering**
- **Feature Selection**
- **Model Training and Evaluation**
- **Model Comparison and Selection**
- **Pipeline Building**
- **Deployment**

## Data Preprocessing

- **Removed Duplicates:** Duplicate entries were identified and eliminated.
- **Checked for Missing Values:** All null values were filled using appropriate strategies.
  - **Mode Imputation:** For `DOJ`, `AGE`, and `RATINGS`.
  - **Median Imputation:** For `LEAVES USED` and `LEAVES REMAINING`.
- **Dropped Irrelevant Columns:** Removed columns `FIRST NAME` and `LAST NAME`.

## Feature Engineering

- **Date Conversion:** Transformed `DOJ` and `CURRENT DATE` into datetime format.
- **New Feature Creation:** Added `years_experience` based on `DOJ` and `CURRENT DATE`.
- **Feature Dropping:** Dropped date columns after feature creation.

## Model Training and Evaluation

- Developed helper functions to calculate and store regression metrics.
- Trained models using various regression techniques.
- Evaluated models by comparing training and test metrics including MAE, MSE, RMSE, and R² score.

## Model Comparison and Selection

We evaluated multiple models:

- **Lasso Regression**
- **Random Forest Regression**
- **Gradient Boosting Regression**
- **XGBoost**
- **Support Vector Regression**

**Selected Model:** Random Forest Regressor with the following metrics:

- **MAE:** 4251.34
- **RMSE:** 7688.52
- **MSE:** 59,113,352.64
- **R² Score:** 0.9535

## Pipeline Building

- Constructed a preprocessing pipeline using `ColumnTransformer`.
- Integrated `SelectKBest` for feature selection within the pipeline.
- Incorporated the Random Forest Regressor into the pipeline.
- The final pipeline includes preprocessing, feature selection, and model for deployment.

## Deployment

Implemented an interactive widget-based application using `ipywidgets`:

- Developed a `predict_salary()` function to make real-time salary predictions based on user inputs.
- Interactive inputs include features like `SEX`, `DESIGNATION`, `AGE`, `UNIT`, `RATINGS`, `PAST EXP`, and `years_experience`.

## Results

The Random Forest Regressor demonstrated superior performance with a high R² score and lower error metrics, making it the chosen model for salary prediction.
