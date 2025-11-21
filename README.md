# Logistic Regression for Financial Data

## Project overview

This repository contains a set of **logistic regression** and **linear regression** experiments applied to real and simulated **financial datasets**.  
The goal is to demonstrate end-to-end workflows for:

- Building classification models for **stock market direction** and **credit default risk**
- Building a regression model for **credit card balance**
- Performing exploratory analysis, feature preprocessing, model training, evaluation, and basic sensitivity analysis 
All examples are implemented in Python (Jupyter Notebook style) using standard data-science libraries.

---

## Datasets and problems

### 1. S&P 500 stock market data

Daily S&P 500 index data is downloaded using `yfinance`. The notebook:

- Computes **lagged returns** (`Lag1`–`Lag5`) and **Volume**
- Defines a binary target variable **Direction** (`Up` / `Down`) based on the sign of the next-day return
- Trains a **logistic regression classifier** to predict next-day direction from the lagged features
- Evaluates performance using:
  - Confusion matrices (train / test)
  - Classification reports (precision, recall, f1-score, accuracy)
  - **ROC curve** and **AUC** for both train and test sets

---

### 2. Default of credit card clients

A credit-card default dataset is used to model whether a client will **default next month**.

The workflow includes:

- Cleaning and renaming columns
- Feature scaling with `MinMaxScaler`
- Splitting into train / test sets
- Training a **logistic regression** model with class weighting
- Evaluating performance with:
  - Confusion matrices (train / test)
  - Classification reports
  - ROC curves and AUC
- Exploring **classification threshold tuning** to trade off false positive rate (FPR) and true negative rate (TNR)

---

### 3. Credit card balance regression

A third dataset models **credit card balance** as a continuous target.

The notebook:

- Loads and preprocesses the data (including categorical encoding and dummy variables)
- Computes correlations and visualizes them with a heatmap
- Fits an **ordinary least squares (OLS)** linear regression model using `statsmodels`
- Reports:
  - Regression coefficients and standard statistics (R², p-values, etc.)
  - A simple **sensitivity analysis** of feature contributions
- Visualizes predicted vs. actual balance values on the test set

---

## Main concepts demonstrated

Across these three examples, the project demonstrates:

- Data loading and cleaning with **pandas**
- Feature engineering (lags, scaling, dummy variables)
- **Logistic regression** for binary classification
- **Linear regression (OLS)** for continuous outcomes
- Train / test split and basic model validation
- Confusion matrices, classification reports, ROC curves, and AUC
- Threshold selection for classifiers
- Interpretation of regression coefficients and sensitivity analysis

---

## Dependencies

The notebook uses standard Python data-science libraries, including:

- `pandas`
- `numpy`
- `matplotlib`
- `seaborn`
- `scikit-learn`
- `statsmodels`
- `yfinance`

---

## How to use this project

1. Open the provided Jupyter Notebook (or the exported Python script) in your environment.  
2. Make sure the required CSV files (e.g., S&P 500 data, credit default data, credit balance data) are available in the working directory.  
3. Run the notebook cells from top to bottom to:
   - Download / load the data
   - Build and evaluate the models
   - Generate plots (confusion matrices, ROC curves, correlation heatmaps, etc.)

You can adapt the code to your own datasets by:

- Replacing the input data
- Modifying the feature engineering steps
- Changing model parameters or evaluation metrics

---

## Possible extensions

- Try different classifiers (e.g., Random Forest, XGBoost) on the same datasets  
- Add cross-validation and hyperparameter tuning  
- Experiment with more financial features (technical indicators, macro variables, etc.)  
- Deploy the trained models as simple APIs or dashboards
