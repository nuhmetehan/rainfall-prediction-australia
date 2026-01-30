# 🌦️ Rainfall Prediction in Australia

![Python](https://img.shields.io/badge/Python-3.8%2B-blue)
![Scikit-Learn](https://img.shields.io/badge/Library-Scikit--Learn-orange)
![XGBoost](https://img.shields.io/badge/Library-XGBoost-red)
![Status](https://img.shields.io/badge/Status-Completed-success)

## 📌 Project Overview
This project was developed as the final assignment for the **IBM Machine Learning with Python** course. The goal is to predict whether it will rain tomorrow in Australia based on historical weather data (10 years of daily observations).

While the course curriculum required building a **Logistic Regression** model using Pipelines and GridSearchCV, I extended the project by implementing an **XGBoost Classifier** to address class imbalance and improve recall performance.

## 📂 Dataset
The dataset contains daily weather observations from numerous Australian weather stations.
* **Source:** [Kaggle - Rain in Australia](https://www.kaggle.com/datasets/jsphyg/weather-dataset-rattle-package)
* **Target Variable:** `RainTomorrow` (Yes/No)
* **Key Features:** Temperature, Humidity, Wind Speed, Pressure, Sunshine, etc.

## ⚙️ Methodology & Tech Stack

### 1. Data Preprocessing
* **Handling Missing Values:** Used `SimpleImputer` (Mean for numerical, Most Frequent for categorical).
* **Feature Engineering:** Converted categorical variables using `OneHotEncoder` and scaled numerical variables using `StandardScaler`.
* **Date Processing:** Mapped dates to seasons (Summer, Autumn, Winter, Spring) relevant to the Southern Hemisphere.

### 2. Machine Learning Pipeline
I utilized Scikit-learn's `Pipeline` and `ColumnTransformer` to prevent data leakage and ensure reproducibility.

* **Baseline Model:** Logistic Regression (optimized via GridSearchCV).
* **Challenger Model:** XGBoost Classifier.

## 🚀 Key Improvements: Why XGBoost?
The dataset is **imbalanced** (~76% No Rain, ~24% Rain).
* The initial **Logistic Regression** model achieved high accuracy (~84%) but suffered from low **Recall (0.50)** for the positive class. It struggled to detect actual rainy days.
* To solve this, I implemented **XGBoost** with the `scale_pos_weight` parameter to penalize false negatives and capture non-linear relationships in weather data.

## 📊 Results

| Model | Accuracy | Precision (Yes) | Recall (Yes) | F1-Score (Yes) |
| :--- | :---: | :---: | :---: | :---: |
| **Logistic Regression** | 0.83 | 0.68 | 0.51 | 0.58 |
| **XGBoost (Tuned)** | **[0.86]** | **[0.71]** | **[0.68]** | **[0.70]** |

*(Note: The XGBoost model significantly improved the detection of rainy days compared to the baseline.)*
