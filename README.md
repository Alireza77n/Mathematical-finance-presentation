# Logistic and Regularized Regression for Financial Data

## Project info

This repository contains two small but complete projects that apply
**statistical learning methods** to financial data:

1. **S&P 500 Direction Prediction** using logistic regression  
2. **Credit Card Balance Regression** using multi–feature regression with
   regularization (Lasso, Ridge, Elastic Net)

The focus is on building models end-to-end, performing feature
engineering, controlling overfitting, and evaluating model performance
with appropriate metrics.

---

## Project 1: S&P 500 Direction Prediction

In the first project, the goal is to predict the **direction of the
S&P 500 index** (up or down) for the next period.

The workflow includes:

- Loading historical S&P 500 data
- Constructing features such as **lagged returns** and other
  market-related variables
- Defining a binary target variable for **next-period direction**
- Fitting a **logistic regression classifier**
- Evaluating performance with:
  - Confusion matrix
  - Accuracy and related classification metrics
  - Train / test comparison

This project illustrates how logistic regression can be used for
directional prediction in a simple financial setting.

---

## Project 2: Credit Card Balance Regression

The second project focuses on modeling **credit card balance** as a
continuous variable.

### Modeling approach

To capture more complex relationships between the predictors and the
balance, the project uses:

- **Multi-regression feature construction**  
  (e.g., transformations / combinations of original variables to create
  richer feature sets)
- Regularization methods to control overfitting:
  - **Lasso regression**
  - **Ridge regression**
  - **Elastic Net**

After generating the extended feature space, each of these models is
trained and evaluated.

### Overfitting control and results

Because the multi-feature representation can easily overfit, the
regularization strength is tuned and different methods are compared.
Among the tested models, **Ridge regression on the multi-feature
representation** achieves the best performance, with an
approximate **R² ≈ 0.94** on the credit card balance data.

This project highlights:

- The trade-off between model complexity and generalization
- How regularization (especially Ridge) can stabilize multi-regression
  models in practice
- How to interpret regression performance in a financial context

---

## Main methods and concepts

Across both projects, the repository demonstrates:

- **Logistic regression** for binary classification (market direction)
- **Multiple linear regression** for continuous targets (balance)
- **Feature engineering** and multi-feature construction
- **Regularization techniques**:
  - Lasso
  - Ridge
  - Elastic Net
- Model evaluation using:
  - Confusion matrices and accuracy (classification)
  - R² and error metrics (regression)
- Basic handling of financial data and interpretation of results

---

## How to use this repository

Each project is implemented in its own script or notebook. To work with
the code:

1. Open the corresponding file for the **S&P 500 direction** project.  
   - Run all cells / code blocks to:
     - Load the data
     - Build features
     - Train the logistic regression model
     - Inspect classification results

2. Open the corresponding file for the **Credit Card Balance** project.  
   - Run the workflow to:
     - Build the multi-feature dataset
     - Fit Lasso, Ridge, and Elastic Net models
     - Compare their performance
     - Reproduce the **R² ≈ 0.94** Ridge result

You can adapt the code to other financial datasets by changing the input
data and adjusting the feature engineering steps.

---

## Possible extensions

- Add more advanced classifiers (e.g., Random Forest, Gradient Boosting)  
- Perform cross-validation and hyperparameter tuning for all models  
- Experiment with additional financial features or macroeconomic
  variables  
- Package the best models as simple APIs or interactive dashboards
