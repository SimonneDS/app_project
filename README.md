Aquí tienes un README completo y profesional en **inglés** para tu proyecto de **Predicción de Precios de Coches Usados** (Rusty Bargain), listo para copiar y pegar.

***

# 🚗 Used Car Price Prediction Project: Rusty Bargain Service

## 📜 Project Description

This project focuses on developing a high-performance **regression model** for the used car sales service **Rusty Bargain**. The goal is to provide customers with a **fast and highly accurate** market value estimate for their vehicle, delivered directly through a mobile application.

The focus was placed on balancing two critical criteria for the application environment: **prediction quality** and **inference speed**.

## 🎯 Key Objectives

The Machine Learning model was designed to meet the following business and technical requirements:

1.  **Prediction Quality (Primary Goal):** Minimize the **Root Mean Squared Error (RMSE)**. A lower RMSE is the main priority to ensure customer trust in the estimated value.
2.  **Prediction Speed:** Ensure the inference time is fast enough for a smooth user experience in a mobile application.
3.  **Comparative Modeling:** Evaluate and compare multiple models, including Gradient Boosting approaches (CatBoost, LightGBM, XGBoost) and Linear models.

## 🛠️ Methodology and Modeling

### 1. Preprocessing and Feature Engineering

* **Missing Value Handling:** Missing values in key columns (e.g., `model` and `registration_year`) were imputed based on the mode of the categories or assigned an "Unknown" value.
* **Outlier Cleansing:** Extreme or outlier values, such as zero or unrealistically high prices, and erroneous data (e.g., vehicles registered in the future), were filtered out to ensure training quality.
* **Encoding:** **One-Hot Encoding** was used for categorical features (like `vehicle_type`, `gearbox`) to make them compatible with both linear and tree-based models.

### 2. Model Training and Evaluation

An exhaustive comparison was performed across various algorithms, paying close attention to *Boosting* methods known for their high precision:

| Model | RMSE (Absolute Value) | Prediction Time (Seconds) |
| :--- | :--- | :--- |
| **XGBoost Regressor** | **1721.58** | 0.39 |
| CatBoost Regressor | 1856.32 | **0.25** |
| LightGBM Regressor | 1850.15 | 0.35 |
| Linear Regression | 2928.10 | 0.01 |

## 📈 Results and Conclusion

### Winning Model Selection

The **XGBoost Regressor** was selected as the final and recommended model for application deployment:

* **Accuracy Justification:** XGBoost achieved the **lowest RMSE (1721.58)**, most effectively meeting the project's primary goal of maximizing prediction quality.
* **Acceptable Speed:** Although CatBoost was marginally faster, XGBoost's prediction time (0.39 seconds) is **sufficiently fast** for a mobile application environment where an instant estimate is required.
* **Business Impact:** By providing the most accurate value estimation, the implementation of XGBoost ensures that Rusty Bargain builds strong customer trust and maximizes its commercial success.

## 💻 Technologies Used

* **Language:** Python
* **Key Libraries:**
    * `pandas`, `numpy`
    * `sklearn.preprocessing` (`OneHotEncoder`)
    * `sklearn.metrics` (`mean_squared_error`)
    * `lightgbm`, `catboost`
    * `xgboost`
    * `time` (for measuring inference speed)