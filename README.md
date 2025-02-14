# PythonDataAnalytics
Jupyter Notebook from a Machine Learning course on Udemy covering fundamental data analytic techniques, web scrapping, and machine learning techniques.

Real-Life Data Cleaning and Regression Analysis

Overview

This project demonstrates how to clean, preprocess, and analyze real-world car sales data using Python. The goal is to explore the dataset, remove inconsistencies, and prepare it for regression analysis.

Dataset

The dataset used in this project is 1.04.+Real-life+example.csv, which contains details about various car brands, their prices, engine capacities, body types, mileage, and other attributes.

Requirements

Ensure you have the following Python libraries installed before running the script:

numpy

pandas

statsmodels

matplotlib

sklearn

seaborn

You can install them using:

pip install numpy pandas statsmodels matplotlib scikit-learn seaborn

Steps

1. Load the Data

The dataset is read using pandas:

raw_data = pd.read_csv("1.04.+Real-life+example.csv")

2. Data Exploration

Basic exploration is performed using:

raw_data.describe(include='all')

This helps in understanding the structure, missing values, and outliers.

3. Data Cleaning

Removing unnecessary columns:

data = raw_data.drop(['Model'], axis=1)

Handling missing values:

data_no_mv = data.dropna(axis=0)

Removing outliers using the quantile method:

q = data_no_mv['Price'].quantile(0.99)
data_1 = data_no_mv[data_no_mv['Price'] < q]

4. Data Visualization

Seaborn is used for visualizing distributions:

sns.displot(data_no_mv['Price'], kde=True, linewidth=0)

Future Enhancements

Perform feature engineering and encoding for categorical variables.

Implement linear regression using sklearn.linear_model.LinearRegression.

Optimize the regression model for better predictions.

Conclusion

This project provides an introduction to data preprocessing and regression analysis using real-world data. The techniques demonstrated are fundamental for preparing datasets for machine learning applications.
