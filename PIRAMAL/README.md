# Predicting Rate of Interest (ROI) from Bureau Data

## Description
This project aims to address the challenge of predicting the rate of interest (ROI) for various types of loans using data provided by financial bureaus. Financial institutions often face the challenge of incomplete data when making decisions or predictions about loan interest rates. Our project leverages mathematical models and machine learning techniques to estimate the ROI accurately, focusing on loans such as Housing Loans, Property Loans, Business Loans, and Personal Loans.

## Objective
The primary objective of this project is to develop a machine learning model capable of predicting the rate of interest for loans using a dataset that includes loan details and demographic data of customers. This involves handling incomplete data and extracting valuable insights to inform the prediction model.

## Dataset Overview

### Structure
Briefly describe each file in the dataset:

- `train_main_loan.csv`: Main loan details for the training set, including demographic information.
- `train_all_loan.csv`: Complete credit history for training set IDs.
- `test_main_loan.csv`: Main loan details for the test set.
- `test_all_loan.csv`: Complete credit history for test set IDs.
- `sample_submission.csv`: Format for submitting predictions.


## Data Preprocessing
Data preprocessing was a critical step in preparing the dataset for modeling. The process involved:

- **Handling Missing Values**: Techniques were applied to impute missing values, ensuring no data point was ignored due to incompleteness.
- **Feature Engineering**: Vital features were extracted and created, such as date components from loan opening dates and aggregated statistics from credit history, to provide the model with comprehensive insights into each customer's credit behavior.
- **Normalization**: Numeric features were normalized to ensure that the scale of values did not bias the model, allowing for equal consideration of all features.
- 
## Model Building

The core of this project revolved around building a predictive model with a meticulous approach:

### Algorithm Selection
We explored various machine learning algorithms and identified XGBoost as the most suited for predicting the ROI, considering its proven track record for accuracy and computational efficiency in regression tasks.

### Hyperparameter Tuning
To optimize the model's performance and ensure the highest level of prediction accuracy, we employed RandomizedSearchCV for hyperparameter tuning. This approach allowed us to efficiently search through a vast parameter space to find the best combination. The parameters explored included:

- `n_estimators`: Number of trees. [100, 200, 500, 1000]
- `max_depth`: Maximum depth of the trees. [6, 10, 15, 20]
- `min_child_weight`: Minimum sum of instance weight (hessian) needed in a child. [1, 2, 5, 10]
- `learning_rate`: Step size shrinkage used to prevent overfitting. [0.01, 0.05, 0.1, 0.2]
- `subsample`: Subsample ratio of the training instances. [0.6, 0.7, 0.8, 0.9, 1.0]
- `colsample_bytree`: Subsample ratio of columns when constructing each tree. [0.6, 0.7, 0.8, 0.9, 1.0]
- `gamma`: Minimum loss reduction required to make a further partition on a leaf node. [0, 0.1, 0.2, 0.5, 1, 1.5, 2]
- `reg_alpha`: L1 regularization term on weights. [0, 0.1, 0.5, 1, 2]
- `reg_lambda`: L2 regularization term on weights. [0.1, 1, 5, 10]
- `scale_pos_weight`: Balancing of positive and negative weights. [1, 2, 5]
- `max_delta_step`: Maximum delta step we allow each tree's weight estimation to be. [0, 1, 2, 5]

To harness the power of modern hardware, we utilized the `tree_method='hist'` and `device='cuda'` settings in XGBoost, enabling GPU acceleration for faster computation.

```python
xgb = XGBRegressor(tree_method='hist', device='cuda')
xgb_random = RandomizedSearchCV(estimator=xgb, param_distributions=param_distributions, n_iter=100, cv=3, verbose=2, random_state=42, n_jobs=-1)


The chosen model and preprocessing steps were instrumental in addressing the challenges posed by incomplete data, ultimately leading to improved decision-making for financial institutions regarding loan interest rates.


