🚕 Zuber Ride Sharing Analysis
📌 Project Description
This project analyzes ride-sharing data for Chicago with the aim of uncovering passenger behavior, company performance, and the influence of external factors like weather on ride frequency and duration.

The analysis helps Zuber, a ride-sharing company, better understand the competitive landscape and customer preferences. It also tests whether weather significantly affects ride duration from central Chicago (Loop) to O'Hare International Airport.

🛠️ Objectives
Identify patterns in taxi ride data.

Understand how different companies perform in terms of ride volume.

Analyze which neighborhoods receive the most rides.

Investigate the impact of weather conditions on ride duration.

Test the hypothesis:
"Ride durations from the Loop to O’Hare are longer on rainy Saturdays."

📂 Datasets Used
The following datasets were utilized in the analysis:

taxi_df.csv
company_name: Name of the taxi company

trips_amount: Number of rides on November 15–16, 2017

dropoff_df.csv
dropoff_location_name: Neighborhood where the ride ended

average_trips: Average number of rides that ended in each neighborhood in November 2017

loop_ohare_df.csv
start_ts: Pickup timestamp

weather_conditions: Weather at pickup time

duration_seconds: Ride duration in seconds

🧭 Procedure
Data Mining

Initial extraction and filtering of ride-sharing data using SQL queries.

Data Loading

Read all datasets into Python using pandas.

Data Cleaning

Standardized company_name by removing phone numbers.

Cleaned dropoff_location_name by removing special characters.

Converted start_ts to datetime format.

Found 197 duplicate rows in loop_ohare_df based on hour-level grouping — retained as they represent distinct rides.

Exploratory Data Analysis (EDA)

Visualized number of rides by company.

Examined average trip volume by neighborhood.

Analyzed ride durations from the Loop to O’Hare based on weather and time.

Hypothesis Testing

Performed statistical testing to validate if rainy Saturdays affect ride duration.

📊 Key Findings
Flash Cab had the highest number of rides — nearly double that of the second-ranking company.

A small number of neighborhoods accounted for a majority of drop-offs, with a steep drop in volume after the top few.

The hypothesis was confirmed:
➤ Ride durations from the Loop to O’Hare are significantly longer on rainy Saturdays.

🔧 Tools & Technologies
SQL – Data extraction and preparation

Python – Data analysis and visualization

Pandas / NumPy – Data manipulation

Matplotlib / Seaborn – Charts and visualizations

SciPy / Statsmodels – Hypothesis testing

✅ Conclusion
The analysis provides actionable insights into rider behavior and the competitive landscape of Chicago's ride-sharing industry. Flash Cab dominates in volume, while ride durations are impacted by weather, especially on rainy weekends. These findings can help Zuber optimize service availability, pricing, and marketing efforts in Chicago.

Feel free to explore the data and run the analysis notebooks to dive deeper into the results!
