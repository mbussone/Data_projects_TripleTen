🛢️ Oil Region Profitability Analysis
📌 Project Overview
The goal of this project is to identify the most promising oil region for investment based on machine learning predictions and profit analysis. Three regions are analyzed using data on oil well reserves. A regression model is used to predict the volume of oil reserves, and statistical techniques are applied to estimate profit and risk.

Beta Bank (fictional) is preparing to develop new oil wells and must decide which region offers the best return with minimal risk.

🎯 Objectives
Build a predictive model for estimating oil reserves.

Evaluate prediction performance using RMSE and compare predictions to actual values.

Calculate potential profits based on predictions and well selection.

Estimate risks and expected returns using bootstrapping.

Recommend the most viable region for oil development.

🛠️ Procedure
1. 📥 Data Preparation
Downloaded and inspected the dataset for all three regions.

Verified data types and integrity.

No significant issues were found in the dataset.

2. 🤖 Model Training and Validation (per region)
For each region:

Split the dataset into training and validation sets (75:25 ratio).

Trained a linear regression model on the training data.

Predicted reserve volumes on the validation set.

Calculated RMSE and printed the average predicted reserve volume.

Stored both predictions and actual values for further analysis.

3. 💰 Profit Calculation Preparation
Defined constants for budget, number of selected wells, and revenue per unit.

Computed the minimum reserve volume required for a well to break even.

Compared this threshold with the average reserve volume in each region.

4. 💹 Profit Calculation Function
Wrote a function to:

Select the top 200 wells by predicted reserve volume.

Calculate the total profit based on actual reserves.

Suggest the most promising region based on projected profit.

5. 📊 Risk Analysis via Bootstrapping
Applied bootstrapping with 1000 iterations for each region to simulate profit outcomes.

Calculated:

Average profit

95% confidence interval

Risk of loss (i.e., chance of negative profit)

📈 Results Summary
Region	Actual Volume	Actual Profit	Avg. Profit	95% Confidence Interval	Risk of Loss
0	29,601	$33,208,260.43	$3,734,300.00	-$1,516,589.96 to $8,918,520.78	7.60%
1	2,758	$24,150,866.97	$4,550,879.75	$367,345.72 to $8,544,400.13	1.30%
2	28,245	$27,103,499.64	$3,975,076.75	-$1,571,284.12 to $9,367,518.11	7.20%

✅ Conclusion
Although Region 0 appeared promising due to its high actual profit, the large discrepancy between predicted and actual reserve volumes, coupled with a 7.6% risk of loss, raises concerns.

✅ Region 1 is the most stable and reliable investment choice:

Lowest risk of loss (1.3%)

Narrow and entirely positive confidence interval

Consistent performance in predictions and actual values

💡 Recommendation: Invest in Region 1 for oil well development to maximize profit with minimal risk.

🧰 Tools & Technologies Used
Python (Pandas, NumPy, Scikit-learn)

Linear Regression Modeling

Bootstrapping (Monte Carlo simulation)

Statistical metrics (RMSE, confidence intervals)

Matplotlib / Seaborn for visualization

📁 Project Structure
graphql
Copy
Edit
oil-profit-analysis/
│
├── data/                     # Raw and processed data
├── notebooks/                # EDA and model building
├── results/                  # Stored predictions and reports
├── README.md                 # Project documentation
└── requirements.txt          # Python dependencies
