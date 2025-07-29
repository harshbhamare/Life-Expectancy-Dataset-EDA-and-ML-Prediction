# Life-Expectancy-Dataset-EDA-and-ML-Prediction


Life Expectancy Prediction Project
Overview
This project aims to predict the life expectancy of a country based on various health, economic, and social factors from the "Life Expectancy (WHO)" dataset. The project involves a complete machine learning workflow, including exploratory data analysis (EDA), data preprocessing, model training, and selection.

Exploratory Data Analysis (EDA)
The initial analysis revealed several key insights:

Strongest Predictors: Adult Mortality and HIV/AIDS have a strong negative correlation with life expectancy. Income Composition of Resources and Schooling have a strong positive correlation.

GDP Impact: GDP has a positive but logarithmic relationship with life expectancy, showing diminishing returns after a certain threshold.

Development Gap: A significant gap in life expectancy exists between "Developed" and "Developing" nations. While both groups have seen improvements from 2000-2015, the gap has only slightly narrowed.

Data Cleaning & Preprocessing
To prepare the data for modeling, the following steps were taken:

Column Name Standardization: Column names were converted to lowercase and spaces were replaced with underscores for easy access.

Handling Infinite Values: All inf values in the dataset were replaced with NaN (Not a Number).

Preprocessing Pipeline: A ColumnTransformer was used to apply specific transformations to different columns:

Numerical Features: Missing values were imputed using the median. GDP was log-transformed, and all numerical features were scaled using StandardScaler.

Categorical Features: The status column was one-hot encoded to be used in the models.

Modeling & Selection
Two regression models were trained and evaluated to predict life expectancy.

Linear Regression: Served as a baseline model to establish initial performance.

Random Forest Regressor: A more complex ensemble model chosen for its ability to capture non-linear relationships.

The dataset was split into 80% for training and 20% for testing.

Model Performance
The models were evaluated based on their R-squared (R²), Mean Absolute Error (MAE), and Root Mean Squared Error (RMSE) on the unseen test set.

Metric	Linear Regression	Random Forest
R-squared (R²)	0.7880	0.9635
MAE (years)	3.0892	1.2088
RMSE (years)	4.2864	1.7780

Export to Sheets
Winning Model 🏆
The Random Forest Regressor was the clear winner. It significantly outperformed the Linear Regression model, explaining over 96% of the variance in life expectancy with an average prediction error of just 1.2 years.

How to Use
Prerequisites: Ensure you have Python installed with the following libraries:

pandas

numpy

scikit-learn

seaborn

matplotlib

Bash

pip install pandas numpy scikit-learn seaborn matplotlib
Training: Run the Jupyter Notebook or Python script containing the model training code. This will train the RandomForestRegressor and save the preprocessing and model steps into a pipeline.

Prediction: To predict on new data, load your CSV file and use the trained model pipeline.

Python

# Load your trained model pipeline
# (Assuming it's stored in 'rf_model_pipeline')

# Load new data from a CSV
new_data = pd.read_csv('your_new_data.csv')

# Make predictions
predictions = rf_model_pipeline.predict(new_data)
Conclusion
This project successfully developed a high-accuracy machine learning model for predicting life expectancy. The Random Forest Regressor proved to be highly effective, demonstrating that life expectancy is strongly determined by a combination of health indicators and socio-economic factors.
