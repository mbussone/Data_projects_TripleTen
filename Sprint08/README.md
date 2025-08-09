🏦 Beta Bank Customer Churn - Supervised Learning Analysis
📌 Project Description
Beta Bank is experiencing a gradual loss of customers every month. In an effort to reduce churn and retain existing clients, the bank wants to predict which customers are likely to leave soon. Since retaining a customer is significantly more cost-effective than acquiring a new one, this model will help support proactive customer retention strategies.

Using historical data on customer behavior and churn, the goal is to develop a supervised learning model that predicts whether a customer will terminate their contract. The success criterion is a model that achieves an F1 score of at least 0.59 on the test set.

🎯 Objectives
Understand and prepare the customer behavior dataset.

Identify and resolve any class imbalance issues.

Train and evaluate several models to find the best-performing one.

Measure performance using F1 score and AUC-ROC.

Deploy the final model with validated performance on the test set.

🛠️ Procedure
1. Data Preparation
Loaded customer data and performed an initial inspection.

Cleaned the data: verified types, handled missing values, and ensured data integrity.

No major issues were found requiring complex preprocessing.

2. Initial Modeling (Without Handling Class Imbalance)
Trained multiple models on the unbalanced data.

The highest F1 score achieved in this stage was 0.56, which was below the target threshold of 0.59.

3. Addressing Class Imbalance
Applied two methods to correct for class imbalance:

Random Oversampling (Upsampling)

Balanced Class Weighting (used within the model training process)

4. Model Training and Evaluation
Multiple models were trained and tuned using the training and validation sets.

The Random Forest Classifier consistently performed the best.

Evaluation metrics focused on F1 score and ROC AUC.

📊 Final Results
✅ Validation Results
Model	F1 Score	ROC AUC
Random Forest (balanced class)	0.6168	0.8635
Random Forest (upsampled data)	0.6203	0.8567

🧪 Test Set Performance
Model	Test F1 Score
Random Forest (balanced class)	0.609
Random Forest (upsampled data)	0.608

Both models met the required F1 threshold of 0.59 on the test set, confirming their robustness and generalization ability.

🔧 Tools & Technologies
Python (Pandas, NumPy, Scikit-learn)

Machine Learning Algorithms:

Random Forest

Logistic Regression

Decision Tree

Evaluation Metrics:

F1 Score

AUC-ROC

Techniques for Imbalance Handling:

Upsampling (Synthetic increase of minority class)

Class weight balancing

📁 Project Structure
bash
Copy
Edit
beta-bank-churn/
│
├── data/                   # Source data files
├── notebooks/              # Jupyter notebooks for EDA and modeling
├── models/                 # Trained models and configurations
├── README.md               # Project overview
└── requirements.txt        # Environment dependencies
✅ Conclusion
Two Random Forest models successfully met the project's F1 requirement, each using a different strategy to handle class imbalance.

These models can now be integrated into Beta Bank’s operations to predict customer churn and improve retention efforts proactively.
