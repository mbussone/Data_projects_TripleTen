# Interconnect Telecom - Customer Churn Prediction

## Project Overview

Interconnect, a telecom operator, aims to forecast client churn in order to proactively offer promotional codes and special plans to customers likely to leave. This project involves building and evaluating machine learning models to predict churn based on client personal data, plans, and contracts.

---

## Business Problem

- **Goal:** Predict which users are planning to leave (churn).
- **Business Value:** Retain customers by targeting those likely to churn with offers and promotions.

---

## Data Description

The dataset consists of multiple files from different sources:

- `contract.csv`: Contract details (monthly or 1-2 year contracts, payment methods, invoice preferences).
- `personal.csv`: Client personal information.
- `internet.csv`: Internet services info (DSL or fiber optic, plus add-ons like DeviceProtection, OnlineSecurity, TechSupport, OnlineBackup, StreamingTV, StreamingMovies).
- `phone.csv`: Telephone services info (landline communication and lines).

Each file contains a `customerID` column for unique client identification.

---

## Data Preprocessing

- Imported all datasets and standardized column names and data types.
- Created new features:
  - Contract length (calculated using contract end date or current date if ongoing).
  - Year and month extracted from contract start date.
  - Number of add-on services purchased by each customer.
- Merged datasets on `customerID`.
- Handled missing data resulting mainly from customers without certain services.
- Defined `Churn` as the target variable for modeling.

---

## Exploratory Data Analysis (EDA)

- Identified some class imbalance in churn data.
- Recommended further analysis on why customers leave, considering their services and other features.

---

## Modeling

- **Target:** `Churn` (binary classification).
- **Primary metric:** AUC-ROC.
- **Secondary metric:** Accuracy.
- **Assessment criteria:**

| AUC-ROC Score       | SP Score  |
|---------------------|-----------|
| < 0.75              | 0         |
| 0.75 ≤ AUC-ROC < 0.81 | 4       |
| 0.81 ≤ AUC-ROC < 0.85 | 4.5     |
| 0.85 ≤ AUC-ROC < 0.87 | 5       |
| 0.87 ≤ AUC-ROC < 0.88 | 5.5     |
| ≥ 0.88              | 6         |

- Models trained and evaluated:
  - Logistic Regression (with/without sampling)
  - Random Forest Classifier (with/without sampling)
  - Decision Tree Classifier (with/without sampling)
  - LightGBM

---

## Results Summary

| Model                               | ROC AUC  | Accuracy  |
|-----------------------------------|----------|-----------|
| Dummy Regressor                   | 0.500    | -0.0007   |
| Logistic Regression               | 0.846    | 0.808     |
| Random Forest Classifier          | 0.892    | 0.844     |
| Decision Tree Classifier          | 0.904    | 0.892     |
| Logistic Regression - Upsampling  | 0.850    | 0.847     |
| Random Forest - Upsampling        | 0.918    | 0.886     |
| Decision Tree - Upsampling        | 0.915    | 0.912     |
| Logistic Regression - Downsampling| 0.838    | 0.843     |
| Random Forest - Downsampling      | 0.876    | 0.860     |
| Decision Tree - Downsampling      | 0.807    | 0.840     |
| LightGBM                        | **0.998** | **0.978** |

- All models outperformed the baseline dummy regressor.
- LightGBM showed the highest ROC AUC (0.998) and accuracy (0.978).
- Upsampled Random Forest and Decision Tree classifiers also performed well.
  
### Final Testing on Selected Models

| Model                             | ROC AUC  | Accuracy  |
|---------------------------------|----------|-----------|
| Decision Tree Classifier - Upsampling | 0.866 | 0.698     |
| Random Forest Classifier - Upsampling | 0.889 | 0.643     |
| LightGBM                        | **0.990** | **0.965** |

LightGBM demonstrated the best predictive power on the test set.

---

## Conclusions

- LightGBM is the most effective model for predicting customer churn.
- These predictions can be leveraged by marketing to retain customers at risk of leaving.
- Further investigation is recommended to understand the causes of churn, especially related to customer services and demographics.
- Sampling techniques (upsampling/downsampling) improve model performance in imbalanced datasets.

---

## Repository Structure

interconnect-churn-prediction/
├── data/
│ ├── contract.csv
│ ├── personal.csv
│ ├── internet.csv
│ └── phone.csv
├── notebooks/
│ ├── data_preprocessing.ipynb
│ ├── exploratory_data_analysis.ipynb
│ └── modeling.ipynb
├── models/
│ └── lightgbm_model.pkl
├── scripts/
│ ├── preprocess.py
│ ├── train.py
│ └── evaluate.py
└── README.md

yaml
Copy
Edit

---

## How to Use

1. Load and preprocess the data using the scripts/notebooks.
2. Train models using the provided scripts or notebooks.
3. Evaluate model performance using AUC-ROC and accuracy.
4. Use the trained LightGBM model for churn prediction in production.

---

## License & Contributions

Feel free to contribute improvements or open issues to discuss further enhancements.

---

*Developed for Interconnect Telecom's customer retention strategy.*



Ask ChatGPT

