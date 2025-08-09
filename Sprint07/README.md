📱 Megaline Subscriber Plan Model
📌 Project Description
Megaline, a mobile carrier, discovered that many of its subscribers are still using outdated legacy plans. To improve customer experience and promote better usage options, the company seeks to develop a classification model that can analyze subscriber behavior and recommend one of its two new plans: Smart or Ultra.

In this project, we build and evaluate models capable of recommending the best plan based on user behavior. The goal is to achieve a minimum accuracy threshold of 0.75 on the test dataset.

🎯 Objective
Use behavior data from subscribers who have already switched to new plans.

Train a machine learning model that can accurately recommend either the Smart or Ultra plan.

Ensure that the model meets or exceeds an accuracy score of 0.75 on the test set.

🛠️ Procedure
Data Loading

Load the prepared dataset from the previous statistical analysis project.

Data Verification

Checked for missing or incorrect values.

No notable issues were found in the dataset.

Data Splitting

Split the data into training, validation, and test sets.

Model Development & Tuning

Built and tuned multiple models to identify the best performer:

Linear Regression

Decision Tree Classifier

Random Forest Classifier

Model Evaluation

Measured accuracy and Root Mean Squared Error (RMSE) on validation and test sets.

📊 Model Results
🔹 Linear Regression
RMSE on validation set: 0.44

🔹 Decision Tree Classifier
Best max_depth: 4

RMSE on validation set: 0.41

RMSE on test set: 0.46

Accuracy on test set: 0.790

🔹 Random Forest Classifier
Best n_estimators: 50

Best max_depth: 8

RMSE on validation set: 0.384

RMSE on test set: 0.42

Accuracy on test set: 0.824

✅ Conclusion
The Random Forest Classifier achieved the highest accuracy of 0.824, outperforming all other models and meeting the required threshold.

RMSE values across validation and test sets were consistent, indicating the model generalizes well.

This model can be confidently used to recommend the most suitable plan to Megaline subscribers.

📦 Tools & Technologies
Python (pandas, scikit-learn, numpy)

Machine Learning: Classification models

Metrics: Accuracy, RMSE

Jupyter Notebook

📁 Repository Structure
bash
Copy
Edit
/megaline-subscriber-plan-model/
│
├── data/                  # Cleaned/preprocessed dataset
├── notebooks/             # Jupyter notebooks for analysis and modeling
├── models/                # (Optional) Saved models or configurations
├── README.md              # Project overview
└── requirements.txt       # Dependencies
💡 Next Steps
Deploy the model as a service for real-time recommendations.

Integrate with Megaline’s customer management system.

Expand the model to include more personalized recommendations.
