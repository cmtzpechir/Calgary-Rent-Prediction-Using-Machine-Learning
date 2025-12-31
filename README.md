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

