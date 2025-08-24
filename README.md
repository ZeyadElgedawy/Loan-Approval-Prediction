# Loan Approval Prediction

## Overview

This project implements a **Loan Approval Prediction System** that performs two tasks:

1. **Loan Amount Prediction** – Uses **Linear Regression** to estimate the maximum loan amount a customer may receive.
2. **Loan Status Classification** – Implements **Logistic Regression from scratch** to determine whether a loan will be approved or not.

The pipeline covers **data preprocessing, feature encoding, scaling, model training, evaluation, and prediction on new data**.

---

## Dataset

The model uses two datasets:

* **`loan_old.csv`** – Historical loan data for training and testing.
* **`loan_new.csv`** – New loan applications for prediction.

The datasets contain both **numerical** and **categorical** features, as well as missing values that are handled during preprocessing.

---

## Project Workflow

### 1. Data Loading & Exploration

* Read CSV files into Pandas DataFrames.
* Identify **categorical** and **numerical** columns.
* Check for **missing values** and remove incomplete rows.
* Perform **basic descriptive statistics** and **pairplots** for numerical features.

---

### 2. Data Preprocessing

* **Drop ID columns** (`Loan_ID`) as they are not predictive.
* Apply **One-Hot Encoding** for categorical variables (`drop='first'` to avoid multicollinearity).
* Scale **numerical features** using `StandardScaler` for better model convergence.
* Encode target variables:

  * **Loan\_Status** → Label Encoding (`Y` = 1, `N` = 0)
  * **Max\_Loan\_Amount** remains numeric.

---

### 3. Model Training

#### **Loan Amount Prediction**

* Trained a **Linear Regression** model from scikit-learn.
* Evaluated using **R² score** to measure how well the model explains variance.

#### **Loan Status Prediction**

* Implemented **Logistic Regression manually**:

  * **Sigmoid function** to map outputs to probabilities.
  * **Binary cross-entropy loss** for optimization.
  * **Gradient Descent** to update weights and bias.
  * **Prediction threshold** of 0.5 for classification.

---

### 4. Evaluation

* **Loan Amount**:

  * Metric: **R² score**
* **Loan Status**:

  * Metric: **Accuracy**
  * Predictions compared with test labels.

---

### 5. Prediction on New Data

* Preprocess new dataset (`loan_new.csv`) in the same way as training data.
* Predict:

  * **Loan Amount** → Linear Regression.
  * **Loan Status** → Logistic Regression.
* Output results to `predictions.csv` containing:

  * Loan ID
  * Predicted Loan Amount
  * Predicted Loan Status (`Y` or `N`)

---

## Key Features

* **Custom Logistic Regression** (no ML library for classification model).
* End-to-end **data preprocessing** pipeline for mixed data types.
* Handles **both regression and classification** in a single workflow.
* Consistent preprocessing for both training and new prediction data.
* Output saved in **CSV format** for external use.

---

