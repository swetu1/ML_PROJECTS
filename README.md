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

## Model Building
The core of this project revolved around building a predictive model with the following approach:

- **Algorithm Selection**: Explored various machine learning algorithms to identify the one most suited for predicting the ROI, considering factors like accuracy and computational efficiency.
- **Hyperparameter Tuning**: Implemented hyperparameter tuning to optimize the model's performance, focusing on minimizing the Root Mean Squared Error (RMSE) to enhance prediction accuracy.
- **Evaluation**: The model was rigorously tested and validated to ensure its reliability and effectiveness in predicting the rate of interest accurately.

The chosen model and preprocessing steps were instrumental in addressing the challenges posed by incomplete data, ultimately leading to improved decision-making for financial institutions regarding loan interest rates.

