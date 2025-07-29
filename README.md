# Life-Expectancy-Dataset-EDA-and-ML-Prediction
---

# 📊 Life Expectancy Prediction Project

## 📌 Overview

This project aims to **predict the life expectancy of a country** based on various health, economic, and social factors from the **"Life Expectancy" dataset**.
The project involves a **complete machine learning workflow**, including:

* Exploratory Data Analysis (EDA)
* Data Cleaning & Preprocessing
* Model Training & Selection
* Performance Evaluation

---

## 🔍 Exploratory Data Analysis (EDA)

The initial analysis revealed several **key insights**:

* **Strongest Predictors:**

  * `Adult Mortality` and `HIV/AIDS` have a **strong negative correlation** with life expectancy.
  * `Income Composition of Resources` and `Schooling` have a **strong positive correlation**.

* **GDP Impact:**

  * GDP has a **positive but logarithmic relationship** with life expectancy, showing **diminishing returns** after a certain threshold.

* **Development Gap:**

  * A **significant gap** in life expectancy exists between **Developed** and **Developing nations**.
  * Both groups have improved from 2000–2015, but the gap has only **slightly narrowed**.

---

## 🧹 Data Cleaning & Preprocessing

The dataset was **prepared for modeling** using the following steps:

1. **Column Name Standardization:**

   * Converted column names to lowercase.
   * Replaced spaces with underscores.

2. **Handling Infinite Values:**

   * Replaced all `inf` values with `NaN`.

3. **Preprocessing Pipeline:**

   * **Numerical Features:**

     * Missing values imputed using **median**.
     * GDP was **log-transformed**.
     * Features scaled using **StandardScaler**.
   * **Categorical Features:**

     * `status` column **one-hot encoded**.

---

## 🤖 Modeling & Selection

Two regression models were trained and evaluated to predict life expectancy:

* **1️⃣ Linear Regression:**

  * Used as a **baseline model** to establish initial performance.

* **2️⃣ Random Forest Regressor:**

  * A more complex ensemble model chosen for its ability to **capture non-linear relationships**.

📌 **Data Split:**

* **80% Training** | **20% Testing**

---

## 📈 Model Performance

The models were evaluated based on **R-squared (R²)**, **Mean Absolute Error (MAE)**, and **Root Mean Squared Error (RMSE)**.

| Metric             | Linear Regression | Random Forest |
| ------------------ | ----------------- | ------------- |
| **R-squared (R²)** | 0.7880            | 0.9635        |
| **MAE (years)**    | 3.0892            | 1.2088        |
| **RMSE (years)**   | 4.2864            | 1.7780        |

---

## 🏆 Winning Model

The **Random Forest Regressor** was the **best-performing model**, explaining **96% of the variance** in life expectancy with an **average prediction error of just 1.2 years**.

---

## 🚀 How to Use

### ✅ Prerequisites

Make sure you have Python installed and the following libraries:

```bash
pip install pandas numpy scikit-learn seaborn matplotlib
```

---

### ✅ Training the Model

Run the **Jupyter Notebook or Python script** containing the model training code.
This will:

* Train the `RandomForestRegressor`
* Save the preprocessing and model steps into a **pipeline**.

---

### ✅ Making Predictions

```python
# Load your trained model pipeline
# (Assuming it's stored in 'rf_model_pipeline')

# Load new data from a CSV file
new_data = pd.read_csv('your_new_data.csv')

# Make predictions
predictions = rf_model_pipeline.predict(new_data)
```

---

## ✅ Conclusion

This project successfully developed a **high-accuracy machine learning model** for predicting life expectancy.
The **Random Forest Regressor** proved to be highly effective, demonstrating that **life expectancy is strongly influenced by a combination of health indicators and socio-economic factors**.
