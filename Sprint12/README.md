🚗 Rusty Bargain Used Car Price Prediction
📌 Project Overview
Rusty Bargain, a used car sales service, is developing a customer-facing app that helps users quickly estimate the market value of their car. To power this feature, we created a machine learning pipeline that predicts car prices based on historical data, including technical specs, trim, and more.

The company is interested in:

✅ Prediction quality

⚡ Prediction speed

⏱️ Model training time

📂 Project Objectives
Import and clean historical car data.

Train and evaluate multiple regression models.

Compare model performance using:

Root Mean Squared Error (RMSE)

Total training and prediction time

Recommend the best-performing model based on speed and accuracy trade-offs.

🔍 Data Preparation
✅ Initial Cleaning & Preprocessing
Step	Description
✅ Removed duplicates	262 exact duplicates removed
✅ Filled missing values	181,077 missing entries imputed
✅ Dropped useless columns	NumberOfPictures (all zeros), RegistrationMonth (invalid months)
✅ Filtered unrealistic years	Excluded RegistrationYear < 1986 or > 2016
✅ Removed poor target values	Excluded prices = 0 or < 100 (3.5% of data)
✅ Standardized data	Replaced "gasoline" with "petrol" in fuelType
✅ Removed incomplete entries	Removed 3,210 rows missing both vehicle type and model
✅ Handled outliers	Removed rare brand/model combinations

📉 Total rows removed: 35,966 (~10% of dataset)

🔧 Future improvements: Consider alternative strategies for missing data imputation and improve upstream data collection processes to ensure standardization.

🧠 Models Trained
We evaluated six regression models for predicting car prices:

Model	Total Time (s)	Training Time (s)	Prediction Time (s)	RMSE
LightGBM	7.01	6.41	0.60	1374.22 ✅ Best RMSE
XGBoost	11.82	11.65	0.16	1434.68
CatBoost	27.82	27.63	0.10	1383.25
Random Forest (Grid Search)	101.34	101.25	0.09	1483.48
Decision Tree	18.66	3.31	0.01	1664.43
Linear Regression	5.20	5.19	0.0012	2051.23 ❌ Worst RMSE

🏁 Results Summary
✅ Best Overall Model: LightGBM

Lowest RMSE: 1374

Fast training and prediction time

⚡ Fastest Model: Linear Regression

Fastest training & prediction

But poor performance (RMSE: 2051)

🔧 Tech Stack
Python

pandas, numpy

scikit-learn

LightGBM

XGBoost

CatBoost

matplotlib / seaborn (for visualization)

📁 Repository Structure
graphql
Copy
Edit
rusty-bargain-price-predictor/
│
├── data/                     # Cleaned & raw datasets
├── notebooks/                # EDA and modeling experiments
├── models/                   # Trained models (optional)
├── scripts/                  # Helper scripts (preprocessing, metrics)
├── README.md                 # Project overview
└── requirements.txt          # Dependencies
✅ Conclusion
Multiple models were tested on both performance and efficiency.

LightGBM provides the best balance between speed and accuracy for Rusty Bargain’s use case.

The model is ready to be integrated into the customer app for real-time car price predictions.

📈 With further optimization and data enrichment, even better results are achievable!


