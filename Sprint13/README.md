🚖 Sweet Lift Taxi Demand Forecasting
📌 Project Overview
Sweet Lift Taxi, a ride-hailing service, has collected historical data on hourly taxi orders at airports. To better manage driver allocation during peak hours, the company aims to develop a machine learning model to predict the number of orders for the next hour.

🎯 Goal: Build a time series prediction model with a test RMSE ≤ 48.

🧠 Project Objectives
Resample and prepare the time series data.

Engineer features that reflect temporal patterns.

Train and evaluate multiple models.

Choose the best model based on Root Mean Squared Error (RMSE).

Achieve a test RMSE ≤ 48.

🗃️ Dataset
File: taxi.csv

Column of interest: num_orders (Number of taxi orders per time unit)

🔧 Workflow
1. Data Preparation
✅ Imported and examined data — no integrity issues found.

✅ Data was already sorted chronologically.

✅ Resampled data by 1-hour intervals.

✅ Detected clear hourly and weekly seasonality.

✅ Observed a positive trend in order volume from March to August.

✅ Outliers were retained — potentially caused by unknown factors like weather or holidays.

2. Feature Engineering
Created new time-based features:

month, day, hour

day_of_week, is_weekend

lag features (previous hour’s orders)

rolling_mean (average orders over past hours)

3. Modeling
Models tested:

Model	Notes
Baseline - Constant	Used the average as a prediction
Baseline - Previous	Used the previous hour's value
Linear Regression	Simple regression on engineered features
Random Forest	Best-performing model
CatBoost	Performed well, but slightly below RF

✅ All models outperformed the baselines, confirming the approach is effective.

🏁 Results
✅ Best model: Random Forest Regressor

🏆 Best RMSE (Train): 12

🧪 Test RMSE: 43.6

✅ Target Achieved: Test RMSE ≤ 48

📈 Key Takeaways
Feature engineering (especially lag and rolling features) significantly boosted model performance.

The time series showed clear seasonal and trend-based behavior, making ML-based prediction viable.

Despite outliers and potential external factors (e.g., weather, events), the model performed reliably.

🧰 Tech Stack
Python

pandas, numpy

scikit-learn

CatBoost

matplotlib, seaborn (for EDA)

📁 Repository Structure
bash
Copy
Edit
sweet-lift-taxi-demand/
│
├── data/                   # taxi.csv and resampled data
├── notebooks/              # EDA and model training notebooks
├── models/                 # Trained models (optional)
├── scripts/                # Feature engineering and preprocessing
├── README.md               # Project overview
└── requirements.txt        # Dependencies
✅ Conclusion
The project successfully met the prediction goal:

Built multiple models for hourly taxi order forecasting.

Achieved a test RMSE of 43.6, below the required threshold.

Random Forest proved to be the most effective approach for this time series regression task.

📦 This model is ready for deployment in Sweet Lift's app to improve driver allocation during peak demand periods.


