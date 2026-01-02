# Calgary-Rent-Prediction-Using-Machine-Learning
A machine learning model that predicts average rent prices in Calgary using economic, demographic, and housing‑market indicators from 2000–2024.

# 📘 1. Introduction
Understanding how rent prices evolve is essential for renters, policymakers, developers, and analysts. Calgary’s housing market has experienced significant shifts over the past two decades, influenced by economic cycles, population growth, construction activity, and vacancy trends.
This project applies machine learning techniques to analyze historical housing and economic data and predict average rent prices in Calgary. The goal is to build an interpretable, data‑driven model that captures the key factors influencing rent and provides a foundation for future predictions.

# 📊 2. Project Objectives
This project aims to:
- Build a clean, reproducible machine learning workflow for rent prediction
- Engineer meaningful features that reflect supply, demand, and economic pressure
- Compare multiple regression models (Linear, Ridge, Lasso, Random Forest)
- Select the best model based on performance and interpretability
- Package the final model into a scalable pipeline
- Visualize historical vs predicted rent trends
- Extract insights about the drivers of rent changes in Calgary

# 📂 3. Dataset Description
The dataset used in this project is a custom-compiled time series covering Calgary’s housing and economic indicators from 2000 to 2024. It includes:
- Average rent prices (target variable)
- Residential vacancy rates
- Housing starts
- Median family income
- Population estimates
- Building permit values
- Starts per 1,000 residents
- Engineered features such as rent lag and vacancy pressure

All data was sourced from publicly available municipal and provincial datasets, cleaned and reshaped into a wide-format DataFrame for modeling and machine learning analysis.

The raw data was sourced from:
Alberta Regional Dashboard – Calgary
https://regionaldashboard.alberta.ca/region/calgary/custom-dashboard/25-3gFPLza0O3w-8uawPuZ5x4s/#/

# 🧪 4. Feature Engineering
To improve model performance and interpretability, several domain-driven features were engineered:
- rent_lag1: Previous year’s rent, capturing trend persistence
- vacancy_pressure: Inverse of vacancy rate, highlighting market tightness
- starts_per_1000: Housing starts normalized by population
These features reflect economic theory around supply, demand, and affordability, and were critical in improving model accuracy.

# 🤖 5. Modeling Approach
Multiple regression models were evaluated to predict average rent:
- Linear Regression
- Ridge Regression
- Lasso Regression
- Random Forest Regressor

Each model was trained on historical data (2000–2019) and tested on the last 5 years (2020–2024). Performance was evaluated using:
- Mean Absolute Error (MAE)
- Root Mean Squared Error (RMSE)
- R-squared (R²)
Lasso regression emerged as the best model, balancing predictive accuracy with interpretability. It effectively selected the most relevant features while minimizing overfitting.

# ⚙️ 6. Final Model Pipeline
To ensure a clean, reproducible workflow, the final model was packaged into a Scikit‑Learn pipeline. This pipeline standardizes all features using StandardScaler and then applies Lasso Regression with optimized hyperparameters.
The pipeline ensures:
- consistent preprocessing
- reduced risk of data leakage
- improved model stability
- easy reuse for future predictions
The final pipeline was trained on historical data (2000–2019) and saved as a .pkl file for deployment and forecasting.

# 📈 7. Results
The final Lasso Regression model achieved strong performance on the 2020–2024 test period:
- MAE: ~119
- RMSE: ~143
- R²: ~0.54

These results indicate that the model captures over half of the variation in Calgary’s rent prices (~54%) using only a small set of interpretable economic and housing indicators.

Actual vs Predicted Rent (2020–2024 Test Set)
A zoomed‑in view showing the model’s performance on unseen years.

<img width="859" height="547" alt="5_year_test_set" src="https://github.com/user-attachments/assets/49b1a015-db15-488f-a041-7276e122ef3c" />

Actual vs Predicted Rent (Full Timeline)
A line chart comparing historical rent values with model predictions.

<img width="1014" height="547" alt="full_time_line_comparison" src="https://github.com/user-attachments/assets/088b4768-1712-4cc0-bffd-1a7ff7ae3920" />

# 🔍 8. Insights
The final Lasso model selected a small set of influential features and excluded others by shrinking their coefficients to zero. This reflects Lasso’s strength in feature selection and interpretability.
Key Drivers of Rent:
- Building permit values: A strong positive coefficient (~11.26) suggests that higher construction investment correlates with rising rent, possibly due to increased housing demand or delayed supply effects.
- Median family income: A positive coefficient (~5.58) indicates that income growth supports higher rent levels, reflecting affordability and economic strength.
- Population: A moderate positive coefficient (~3.24) shows that population growth contributes to rent increases, likely due to demand pressure.
- Residential vacancy: A strong negative coefficient (~–11.85) confirms that higher vacancy rates are associated with lower rents, a classic supply‑demand signal.
  
<img width="1118" height="637" alt="lasso_pipeline_coefficients" src="https://github.com/user-attachments/assets/c0bd9b83-82a2-4200-bb9b-6471feeff6ad" />

# Interpretation
- Calgary’s rent dynamics appear to be driven more by economic strength and construction investment than by raw housing start counts or engineered vacancy pressure metrics.
- Lasso’s selection emphasizes macro‑level indicators (income, population, investment) over lagged or normalized features.
- The model’s simplicity and interpretability make it suitable for communicating insights to non‑technical stakeholders.

# 9. Future Work
This project lays the foundation for rent forecasting using interpretable machine learning. Future enhancements could include:
- Forecasting future years (2025+) using the saved pipeline
- Adding more granular data (e.g., monthly rent, neighborhood-level indicators)
- Incorporating external factors like interest rates, inflation, or migration trends
- Deploying the model via a web app or dashboard for public use

# 🛠️ 10. How to Run the Project

To run this project locally:

1.  Clone the repository

git clone https://github.com/cmtzpechir/Calgary-Rent-Prediction-Using-Machine-Learning.git cd Calgary-Rent-Prediction-Using-Machine-Learning

2.  Install dependencies

pip install -r requirements.txt

3.  Run the notebook

Open Cleaning.ipynb in Jupyter and run all cells to reproduce the analysis.

4.  Use the saved model

import joblib

loaded_pipeline = joblib.load('calgary_rent_lasso_pipeline.pkl') 

future_pred = loaded_pipeline.predict(future_data) 

# 📁 11. Project Structure

Calgary-Rent-Prediction-Using-Machine-Learning/

 - data/                     # Raw and cleaned datasets
 - images/                   # Visualizations for README
 - final_rent_model.pkl      # Saved pipeline model
 -  Cleaning.ipynb            # Main notebook with full workflow
 - README.md                 # Project documentation
 - requirements.txt          # Python dependencies



