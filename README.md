# 📊 FUTURE_ML_01 – Store Item Demand Forecasting

## 📌 Project Overview

This project was completed as part of the **Future Interns Machine Learning Internship – Task 1**.

The objective is to build a machine learning model that forecasts future store-item sales using historical sales data.

The project includes data preprocessing, exploratory analysis, time-based feature engineering, model training, evaluation, and future sales forecasting.

---

## 🎯 Objective

To develop a machine learning model capable of predicting future sales based on historical store and item sales patterns.

---

## 📊 Dataset

The dataset contains historical daily sales information with the following columns:

- `date` – Date of the sale
- `store` – Store identifier
- `item` – Item identifier
- `sales` – Number of units sold

### Dataset Size

- Training dataset: **913,000 records**
- Test dataset: **45,000 records**

The historical data covers **2013–2017**, while the test data contains dates from **2018**.

---

## 🧹 Data Preprocessing

The following preprocessing steps were performed:

- Loaded the dataset using Pandas
- Checked the dataset structure and data types
- Converted the `date` column to datetime format
- Checked for missing values
- Explored sales statistics
- Analyzed sales by store, item, and month

---

## ⚙️ Feature Engineering

Time-based features were created from the date column:

- `year`
- `month_num`
- `day`
- `day_of_week`

The model also uses:

- `store`
- `item`

These features help the model learn patterns related to time, stores, and products.

---

## ⏳ Time-Based Train/Validation Split

Because this is a forecasting problem, a chronological split was used instead of a random split.

### Training Period

**2013-01-01 → 2016-12-31**

Training records:

**730,500**

### Validation Period

**2017-01-01 → 2017-12-31**

Validation records:

**182,500**

This approach helps evaluate the model on future-like data.

---

## 🤖 Machine Learning Model

### Random Forest Regressor

A **Random Forest Regressor** was trained using the engineered features.

The model learns relationships between:

- Date-related features
- Store
- Item

and the target variable:

- `sales`

---

## 📈 Model Evaluation

The model was evaluated using:

### Mean Absolute Error (MAE)

**10.91**

### Root Mean Squared Error (RMSE)

**16.35**

These metrics were calculated using the validation dataset.

---

## 🔮 Future Sales Forecast

After training and validation, the model was used to generate future sales predictions for the test dataset.

### Forecast Output

- Test records: **45,000**
- Forecast period: **2018**
- Predictions generated: **45,000**

A `submission.csv` file was created containing:

- `id`
- `sales`

---

## 📊 Sample Predictions

| ID | Predicted Sales |
|---:|---:|
| 0 | 13.09 |
| 1 | 13.65 |
| 2 | 14.43 |
| 3 | 12.31 |
| 4 | 14.00 |
| 5 | 14.42 |
| 6 | 17.15 |
| 7 | 10.86 |
| 8 | 13.13 |
| 9 | 13.60 |

---

## 🛠️ Technologies Used

- Python
- NumPy
- Pandas
- Matplotlib
- Scikit-learn
- Google Colab
- Jupyter Notebook
- GitHub

---

## 📁 Project Structure

```text
FUTURE_ML_01/
│
├── FUTURE_ML_01_Sales_Forecasting_(1).ipynb
├── README.md
└── submission.csv
