# 🌦️ Rainfall Prediction in Australia

![Python](https://img.shields.io/badge/Python-3.8%2B-blue)
![Scikit-Learn](https://img.shields.io/badge/Library-Scikit--Learn-orange)
![XGBoost](https://img.shields.io/badge/Library-XGBoost-red)
![Status](https://img.shields.io/badge/Status-Completed-success)

## 📌 Project Overview
This project was developed as the final assignment for the **IBM Machine Learning with Python** course. The goal is to predict whether it will rain tomorrow in Australia based on historical weather data (10 years of daily observations).

## 📂 Dataset
The dataset contains daily weather observations from numerous Australian weather stations.
* **Source:** [Kaggle - Rain in Australia](https://www.kaggle.com/datasets/jsphyg/weather-dataset-rattle-package)
* **Target Variable:** `RainTomorrow` (Yes/No)

## 📊 Results

| Model | Accuracy | Precision (Yes) | Recall (Yes) | F1-Score (Yes) |
| :--- | :---: | :---: | :---: | :---: |
| **Logistic Regression** | 0.83 | 0.68 | 0.51 | 0.58 |
| **XGBoost (Tuned)** | **[0.86]** | **[0.71]** | **[0.68]** | **[0.70]** |

*(Note: The XGBoost model significantly improved the detection of rainy days compared to the baseline.)*

