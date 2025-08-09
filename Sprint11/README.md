🔐 Sure Tomorrow Insurance — Machine Learning Evaluation
📌 Project Overview
Sure Tomorrow, an insurance company, is exploring how machine learning can enhance their business. This project investigates the feasibility and effectiveness of ML models in addressing four real-world business challenges:

Find similar customers for targeted marketing.

Classify whether a new customer is likely to receive an insurance benefit.

Predict the number of insurance benefits a customer may receive.

Protect client data through obfuscation without reducing model performance.

🎯 Project Objectives
Task	Objective
Task 1	Help agents identify similar customers for targeted marketing using similarity metrics.
Task 2	Build a classification model to predict the likelihood of a customer receiving an insurance benefit.
Task 3	Use linear regression to predict the number of benefits a customer may receive.
Task 4	Obfuscate customer data to protect personal information while preserving model performance.

📊 Data Preparation
✅ Cleaning & Preprocessing:
Standardized column names for consistency:

Gender → gender, Age → age, Salary → income, Family members → family_members, Insurance benefits → insurance_benefits

Converted age from float to integer.

Found 153 duplicate rows — these may represent unique customers with identical demographics but were retained for modeling.

Created scaled and unscaled versions of the dataset to compare model performance with and without feature scaling.

🔍 Task Summaries
🧭 Task 1: Find Similar Customers
Applied Euclidean and Manhattan distance metrics.

Observations:

Scaled data tends to group customers by number of family members.

Unscaled data emphasizes income, due to its wider range.

Conclusion: Scaling significantly impacts similarity-based groupings and should be considered depending on business priorities.

✅ Task 2: Classify Insurance Benefit Eligibility
Used K-Nearest Neighbors (KNN) for binary classification.

Evaluation metric: F1 Score (due to class imbalance).

Scaling	Neighbors	F1 Score
Unscaled	1	0.61
Unscaled	10	0.00
Scaled	1	0.97
Scaled	10	0.88

Conclusion: Scaling dramatically improves KNN performance.

📈 Task 3: Predict Number of Benefits (Regression)
Used Linear Regression to predict insurance_benefits.

Data Version	RMSE	R² Score
Unscaled	0.34	0.66
Scaled	0.34	0.66

Conclusion: Scaling had no impact on linear regression results — expected, as linear regression isn’t sensitive to feature scale.

🔐 Task 4: Data Obfuscation
Applied a data transformation algorithm to mask personal information.

Re-ran the linear regression model on obfuscated data.

Data Version	RMSE	R² Score
Obfuscated Unscaled	0.34	0.66
Obfuscated Scaled	0.34	0.66

Conclusion: The obfuscation technique did not degrade model performance, proving its effectiveness for privacy-preserving ML.

🧠 Key Learnings
Scaling is essential for distance-based models like KNN or clustering.

Linear models are robust to feature scaling but still benefit from clean, normalized data.

Data obfuscation can be implemented without harming predictive performance, making it viable for real-world privacy needs.

🧰 Technologies Used
Python: pandas, numpy, scikit-learn

ML Algorithms:

KNN (Classification)

Linear Regression (Regression)

Metrics:

F1 Score

RMSE, R²

📁 Project Structure
bash
Copy
Edit
sure-tomorrow-ml/
│
├── data/                     # Raw and processed datasets
├── notebooks/                # Task-specific notebooks
├── models/                   # Trained models (optional)
├── utils/                    # Data transformation & helper functions
├── README.md                 # Project overview
└── requirements.txt          # Dependencies
✅ Conclusion
Machine learning can provide real value to Sure Tomorrow across multiple areas, including:

Customer segmentation

Risk prediction

Forecasting

Privacy-preserving data analysis

The results validate the feasibility of adopting ML-driven solutions in insurance with attention to data preprocessing, model selection, and data security.


