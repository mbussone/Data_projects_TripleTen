🧪 Zyfra Prototype Gold Recovery Machine Learning Model
📌 Project Overview
Zyfra is developing intelligent efficiency solutions for heavy industry. This project supports their initiative by building a machine learning model to predict gold recovery from ore during the extraction and purification process.

The model will be used to:

Optimize production efficiency.

Eliminate unprofitable configurations and parameters.

Support decision-making in mining operations.

🎯 Objective
To prepare a prototype of a supervised machine learning model that accurately predicts:

Rougher output recovery

Final output recovery

Performance is evaluated using the symmetric Mean Absolute Percentage Error (sMAPE).

🛠️ Procedure
1. 📥 Data Preparation
Loaded and examined data files for training and testing sets.

Verified the rougher.output.recovery calculations using the formula:

recovery
=
𝐶
⋅
(
𝐹
−
𝑇
)
𝐹
⋅
(
𝐶
−
𝑇
)
⋅
100
recovery= 
F⋅(C−T)
C⋅(F−T)
​
 ⋅100
MAE between computed and given values was within acceptable limits, indicating correctness.

Identified features missing in the test set — primarily output features not available at prediction time. These were dropped or handled appropriately during preprocessing.

Preprocessed the data:

Replaced NaN values using forward fill (ffill), based on the assumption that adjacent time steps have similar process values.

Removed zero values deemed to be measurement errors.

2. 📊 Data Analysis
Analyzed concentration changes of gold (Au), silver (Ag), and lead (Pb) across processing stages:

Observed expected increases in Au concentration in later stages.

Compared particle size distributions between train and test sets — found to be consistent, supporting valid evaluation.

Calculated total concentrations at various stages (feed, rougher, final):

Removed rows with abnormal total concentrations indicating potential data corruption.

3. 🤖 Model Building
Wrote a custom function to calculate sMAPE, the main evaluation metric.

Trained multiple regression models:

Due to compute constraints, limited hyperparameter tuning and model variations.

Used Linear Regression as a baseline.

📈 Results
Final evaluation metrics for the best-performing model (Linear Regression) on training data:

Target	MAE	RMSE	sMAPE
rougher.output.recovery	4.13	5.57	4.96
final.output.recovery	5.32	7.47	7.92

⚠️ Limitations
To ensure manageable runtime, the following simplifications were made:

Reduced number of charts during exploratory analysis.

Used simpler fill methods (ffill) for missing values instead of correlation- or group-based approaches.

Limited the variety of models and hyperparameter tuning.

🧰 Technologies Used
Python (pandas, numpy, scikit-learn)

Matplotlib / Seaborn (data visualization)

Custom functions for metric evaluation (sMAPE)

Regression models (Linear Regression, Dummy Regressor for baseline)

📁 Project Structure
graphql
Copy
Edit
zyfra-gold-recovery/
│
├── data/                   # Raw and cleaned datasets
├── notebooks/              # EDA and modeling notebooks
├── models/                 # Trained models and results
├── utils/                  # Custom metric functions
├── README.md               # Project documentation
└── requirements.txt        # Dependencies
✅ Conclusion
The prototype model successfully predicts gold recovery values with reasonable accuracy. While performance can be further improved through deeper feature engineering and more advanced models, the current version provides a solid foundation for production optimization at Zyfra.

🔍 Next Steps:

Add ensemble models (e.g., Random Forest, Gradient Boosting)

Perform feature selection and engineering

Tune hyperparameters for better accuracy

Explore real-time model deployment options


