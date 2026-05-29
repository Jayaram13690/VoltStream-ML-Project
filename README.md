# ⚡ VoltStream Smart Energy Prediction System

## 📌 Project Overview

This project develops the 'VoltStream Smart Energy Prediction System,' designed to help users manage and predict energy consumption and associated costs. It addresses two primary problems: predicting future energy bills (regression) and classifying days as high or low energy usage (classification).

This project solves two real-world machine learning problems:

1. **Regression Problem**: Next Month Energy Bill Prediction. 
- **Goal**: To accurately predict the next month's energy bill.
- **Models Used**: Linear Regression, Random Forest Regressor, Lasso Regression, Ridge Regression, Support Vector Regressor (SVR), XGBoost Regressor, Decision Tree Regressor.
2. **Classification Problem**: High/Low Usage Day Prediction
- **Goal**: To classify whether a given day will be a 'High Usage Day' or a 'Low Usage Day'.
- **Models Used**: Logistic Regression, K-Nearest Neighbors (KNN) Classifier, Support Vector Classifier (SVC), Random Forest Classifier, XGBoost Classifier, Decision Tree Classifier.

The system leverages energy consumption data, weather conditions, solar generation, battery status, and appliance usage to generate meaningful predictions that can help users optimize energy usage and reduce electricity costs.

---

# 🎯 Problem Statements

## Problem 1: Electricity Bill Prediction (Regression)

Predict future electricity bills based on energy consumption behavior and environmental conditions.

### Target Variable

`predicted_bill`

## Problem 2: High Usage Day Prediction (Classification)

Predict whether a day belongs to:

- 1 → High Usage Day
- 0 → Low Usage Day

---

# 📊 Dataset

Data Generation
The dataset for this project is synthetically generated and includes a variety of features that influence energy consumption and billing. Key features include:

- Timestamp: Hourly records over two years.
- Time-based features: Hour, day of week, month.
- Environmental factors: Weather conditions (sunny, cloudy, rainy), temperature.
- Energy-related features: Solar generation, HVAC usage, EV charger usage, kitchen usage, battery level, peak hour status, grid usage, daily consumption.
- Target Variables: predicted_bill (for regression) and high_usage (for classification, derived from the 75th percentile of predicted_bill).

## Features

- hour
- day_of_week
- month
- weather
- temperature
- solar_generation
- battery_level
- hvac_usage
- ev_charger_usage
- kitchen_usage
- peak_hour
- grid_usage
- daily_consumption

---

# 🧹 Data Preprocessing

**Data Preprocessing**
- **Missing Values**: Handled by imputing with the mean for hvac_usage and ev_charger_usage.
- **Duplicates**: Removed to ensure data integrity.
- **Feature Encoding**: Categorical features (weather, peak_hour) were converted into numerical representations using Label Encoding.
- **Feature Scaling**: Numerical features were scaled using StandardScaler to normalize their ranges, which is crucial for many machine learning algorithms.
- **Data Splitting**: Data was split into training and testing sets for both regression and classification tasks, with stratification for the classification target to maintain class balance.
---

# 🤖 Machine Learning Models

## Regression Models

- Linear Regression
- Random Forest Regressor
- Ridge Regression
- Lasso Regression
- Support Vector Regressor (SVR)
- Decision Tree Regressor
- XGBoost Regressor

### Evaluation Metrics

- MAE
- RMSE
- R² Score
- TimeSeries Cross Validation

---


## Classification Models

- Logistic Regression
- K-Nearest Neighbors (KNN)
- Support Vector Classifier (SVC)
- Decision Tree Classifier
- Random Forest Classifier
- XGBoost Classifier

### Evaluation Metrics

- Accuracy
- Precision
- Recall
- F1 Score
- ROC-AUC
- Confusion Matrix

---

# 📈 Visualizations

- Correlation Heatmap
- Actual vs Predicted Bills
- Feature Importance Analysis
- Confusion Matrix
- Precision-Recall Curve
- ROC Curve

---
## Results and Predictions

The notebook provides a comparative analysis of model performance for both regression and classification tasks. It also includes examples of future predictions using the trained models, demonstrating their practical application in a smart energy prediction system.

### Regression Model Comparison

| Model                   | R2 Score | RMSE      |
|:------------------------|:---------|:----------|
| Random Forest           | 0.826779 | 18.332614 |
| XGBoost Regressor       | 0.821707 | 18.599067 |
| Lasso Regression        | 0.816250 | 18.881566 |
| Ridge Regression        | 0.816109 | 18.888788 |
| Linear Regression       | 0.816088 | 18.889884 |
| SVR                     | 0.811820 | 19.107827 |
| Decision Tree Regressor | 0.657222 | 25.788783 |

### Classification Model Comparison

| Model                    | Accuracy | Precision (Class 1) | Recall (Class 1) | F1-Score (Class 1) | ROC-AUC  |
|:-------------------------|:---------|:--------------------|:-----------------|:-------------------|:---------|
| Logistic Regression      | 0.878883 | 0.727823            | 0.823261         | 0.772606           | 0.945241 |
| SVC Classifier           | 0.884298 | 0.761958            | 0.781072         | 0.771396           | 0.938311 |
| Random Forest Classifier | 0.872043 | 0.709804            | 0.825542         | 0.763310           | 0.940163 |
| XGBoost Classifier       | 0.873183 | 0.726891            | 0.789054         | 0.756698           | 0.937077 |
| KNN Classifier           | 0.847250 | 0.658017            | 0.809578         | 0.725971           | 0.898457 |
| Decision Tree Classifier | 0.843260 | 0.690338            | 0.676169         | 0.683180           | 0.787552 |


# 🔮 Future Predictions

### Future Bill Prediction Output

*   **Scenario 1:** Predicted future electricity bill: $119.35
*   **Scenario 2:** Predicted Future Electricity Bill: $159.99

### High Usage Prediction Output

*   **Scenario 1:** Predicted: High Usage Day (Probability: 98.48%)
*   **Scenario 2:** High Usage Probability: 100.00 % Predicted Usage Day: High Usage Day
*   **Scenario 3:** High Usage Probability: 10.54 % Predicted Usage Day: Low Usage Day
