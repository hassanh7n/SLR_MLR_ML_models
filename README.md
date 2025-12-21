Housing-Price-Prediction/
│
├── notebooks/
│   ├── 01_EDA.ipynb         # Exploratory Data Analysis
│   ├── 02_SLR.ipynb         # Simple Linear Regression
│   ├── 03_MLR.ipynb         # Multiple Linear Regression
│   ├── 04_Polynomial.ipynb  # Polynomial Regression
│   ├── 05_Ridge.ipynb       # Ridge Regression
│   └── 06_Lasso.ipynb       # Lasso Regression
│
├── data/
│   └── california_housing.csv
│
└── README.md






🏠 California Housing Dataset – Exploratory Data Analysis (EDA)

This project contains an EDA of the California Housing dataset, with a focus on understanding relationships between housing features, engineered ratios, and the target variable, median_house_value.

1️⃣ Dataset Overview

Total rows: 20,640

Target variable: median_house_value

Key features: housing_median_age, total_bedrooms, median_income, rooms_per_household, bedrooms_per_room

Missing values: None (after preprocessing)

2️⃣ Descriptive Statistics
Feature	Count	Mean	Std	Min	25%	50%	75%	Max
housing_median_age	20640	28.64	12.59	1	18	29	37	52
total_bedrooms	20640	535.28	420.05	1	292	431	643	6445
median_income	20640	3.87	1.90	0.50	2.56	3.53	4.74	15.00
median_house_value	20640	206,856	115,396	14,999	119,600	179,700	264,725	500,001
rooms_per_household	20640	5.43	2.47	0.85	4.44	5.23	6.05	141.91
bedrooms_per_room	20640	0.21	0.06	0.02	0.17	0.20	0.24	1.82
3️⃣ Distribution Analysis

Median House Value: Right-skewed with a price ceiling at 500,001

Mean (206,855) > Median (179,700) → confirms skewness

Implication: High-value outliers affect linear regression assumptions

Median Income: Right-skewed

Ratio Features (rooms_per_household, bedrooms_per_room): Normalized distributions, useful for regression modeling

4️⃣ Feature Engineering

Two engineered ratio features improve interpretability:

Rooms per Household = total_rooms / households

Average: 5.43

Measures living space per household

Bedrooms per Room = total_bedrooms / total_rooms

Average: 0.21

Higher values indicate more crowded housing

5️⃣ Correlation Analysis
Features	Correlation
Median Income & Median House Value	Strong positive correlation
Median Income & Bedrooms per Room	Negative correlation ≈ -0.58

Insights:

median_income is the most influential predictor of house value

Negative correlation with bedrooms-per-room highlights crowding in lower-income households

6️⃣ Modeling Implications

Right-skewed target and outliers suggest linear regression may underperform

Regularized models work better:

Ridge Regression: Handles multicollinearity and outliers

Lasso Regression: Performs feature selection

7️⃣ Key Takeaways

Median income drives housing prices

Right-skewed distributions and outliers justify regularization

Ratio-based features provide better feature representation

Ridge and Lasso models are better suited than standard linear regression