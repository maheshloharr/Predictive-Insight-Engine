# 🏠 Predictive Insight Engine: House Price Prediction

## 📌 Project Overview

This project, **Predictive Insight Engine**, is a supervised machine learning project for a real estate analytics use case.

The objective is to estimate **house prices in INR** using property characteristics such as house area, bedrooms, bathrooms, location score, property age, and other available attributes.

The project covers:
- Data loading and exploration
- Exploratory Data Analysis (EDA)
- Simple Linear Regression
- Regression assumptions and residual analysis
- Model evaluation
- Multiple Linear Regression
- Polynomial Regression
- Gradient Descent
- Batch Gradient Descent
- Stochastic Gradient Descent
- Mini-Batch Gradient Descent
- Bias-Variance analysis
- Overfitting and Underfitting
- Model comparison
- Business interpretation

---

## 🎯 Problem Statement

A real estate analytics firm wants to develop a predictive system that can estimate house prices based on property characteristics.

The target variable is **`house_price_inr`**.

The project applies different regression techniques and compares their performance to identify an appropriate predictive model.

---

## 📊 Dataset Information

**Dataset:** `RealEstate_HousePrice_Dataset_4200.xlsx`

**Records:** 4,200  
**Columns:** 12

| Column | Description |
|---|---|
| `house_id` | Unique identifier for each house |
| `area_sqft` | House area in square feet |
| `bedrooms` | Number of bedrooms |
| `bathrooms` | Number of bathrooms |
| `location_score` | Numerical score representing location quality |
| `age_years` | Age of the property in years |
| `distance_city_km` | Distance from the city in kilometers |
| `lot_size_sqft` | Lot size in square feet |
| `has_garage` | Garage availability indicator |
| `has_pool` | Pool availability indicator |
| `renovation_years_ago` | Number of years since renovation |
| `house_price_inr` | House price in Indian Rupees |

### Target Variable

```text
house_price_inr
```

### Main Predictor Variables

```text
area_sqft
bedrooms
bathrooms
location_score
age_years
distance_city_km
lot_size_sqft
has_garage
has_pool
renovation_years_ago
```

---

# 📚 Project Questions and Implementation

## Part A: Regression Concepts

### Q1. What is Supervised Learning?

Supervised learning is a machine learning approach where a model learns from labeled data.

In this project:
- Input features = property characteristics
- Target = house price

The model learns the relationship between property features and house prices and uses that relationship to make predictions.

---

### Q2. Regression vs Classification

**Regression** predicts continuous numerical values.

Example:
```text
Predicted House Price = ₹4,02,75,084
```

**Classification** predicts categories or classes.

Example:
```text
House = Affordable / Expensive
```

Since house price is a continuous numerical value, this project is a **Regression problem**.

---

### Q3. Simple Linear Regression

Simple Linear Regression uses one independent variable to predict a dependent variable.

General equation:

```text
y = β0 + β1x
```

Where:
- `y` = predicted target
- `x` = independent variable
- `β0` = intercept
- `β1` = slope

In this project, `area_sqft` is used as the predictor and `house_price_inr` is the target.

---

### Q4. Assumptions of Linear Regression

Important assumptions include:

1. Linear relationship between features and target
2. Independent observations
3. Homoscedasticity of residuals
4. Residuals approximately follow a normal distribution
5. Low multicollinearity among predictors for multiple regression

These assumptions are checked using appropriate plots and diagnostics.

---

### Q5. Bias-Variance Tradeoff

**Bias** represents error caused by an overly simple model.

**Variance** represents sensitivity to the training data.

A good model tries to maintain a balance between bias and variance.

```text
High Bias       → Underfitting
High Variance   → Overfitting
Balanced Model  → Better Generalization
```

---

### Q6. Overfitting and Underfitting

**Overfitting:** The model learns the training data too closely and performs poorly on unseen data.

**Underfitting:** The model is too simple and fails to capture important patterns.

A suitable model should perform well on both training and test data.

---

# 🔍 Part B: Data Understanding and Visualization

## Q7. Independent and Dependent Variables

### Independent Variables

The independent variables are the property characteristics used to predict price.

```text
area_sqft
bedrooms
bathrooms
location_score
age_years
distance_city_km
lot_size_sqft
has_garage
has_pool
renovation_years_ago
```

### Dependent Variable

```text
house_price_inr
```

---

## Q8. Feature-Target Visualization

The project visualizes relationships between important features and house price.

### 📈 Area vs House Price

This graph shows the relationship between house area and house price. A positive relationship indicates that larger properties generally tend to have higher prices.

### 📈 Bedrooms vs House Price

This graph shows how the number of bedrooms relates to house prices. It helps identify whether properties with more bedrooms generally have higher prices.

### 📈 Bathrooms vs House Price

This graph visualizes the relationship between bathroom count and house price and helps understand whether additional bathrooms are associated with higher property prices.

### 📈 Location Score vs House Price

This graph shows how location quality relates to house prices. A higher location score may be associated with higher property values.

### 📈 Property Age vs House Price

This graph examines the relationship between property age and house price and helps identify whether older properties show different pricing patterns.

### 🔥 Correlation Heatmap

The correlation heatmap displays relationships between numerical variables.

Approximate correlations with `house_price_inr`:

| Feature | Correlation |
|---|---:|
| `area_sqft` | 0.76 |
| `bedrooms` | 0.64 |
| `location_score` | 0.59 |
| `bathrooms` | 0.53 |
| `age_years` | -0.09 |

`area_sqft` has the strongest positive linear correlation with house price among these listed variables.

---

## Q9. Train-Test Split

The dataset is divided into:

- **80% Training Data**
- **20% Testing Data**

Training data is used to learn model parameters, while testing data evaluates performance on unseen observations.

`random_state=42` is used for reproducibility.

---

# 📐 Part C: Simple Linear Regression

## Q10. Simple Linear Regression Using House Area

A Simple Linear Regression model is trained using:

```text
Independent Variable → area_sqft
Dependent Variable   → house_price_inr
```

The model learns how house area is related to house price.

---

## Q11. Regression Line

The regression line represents the relationship learned by the linear regression model.

```text
House Price = Intercept + Slope × Area
```

**Slope:** Expected change in house price for one additional unit of house area.

**Intercept:** Predicted house price when area is zero. This is primarily a mathematical parameter and may not have practical real-world meaning.

---

## Q12. Regression Assumption Validation

### Residual Plot

The residual plot shows prediction errors against predicted values. A reasonably random spread around zero supports the assumptions of linearity and constant variance.

### Residual Distribution

The residual distribution helps examine the shape of prediction errors. A roughly symmetric distribution is consistent with approximately normal residuals.

### Q-Q Plot

The Q-Q plot compares residual quantiles with theoretical normal quantiles. Points close to the reference line indicate approximately normal residuals.

---

# 📏 Part D: Model Evaluation

## Q13. Regression Evaluation Metrics

### Mean Squared Error (MSE)

MSE calculates the average squared prediction error.

```text
MSE = Average((Actual - Predicted)²)
```

Lower MSE indicates better performance.

### Mean Absolute Error (MAE)

MAE calculates the average absolute prediction error.

```text
MAE = Average(|Actual - Predicted|)
```

Lower MAE indicates better performance.

### Root Mean Squared Error (RMSE)

```text
RMSE = √MSE
```

RMSE is expressed in the same unit as the target variable.

---

## Q14. R² and Adjusted R²

### R² Score

R² measures the proportion of variance in house prices explained by the model. A higher R² generally indicates better explanatory performance.

### Adjusted R²

Adjusted R² accounts for the number of predictors in the model and is useful when comparing models with different numbers of features.

---

# 🏘️ Part E: Multiple Linear Regression

## Q15. Multiple Linear Regression

Multiple Linear Regression uses multiple independent variables to predict house price.

Example predictors:

```text
area_sqft
bedrooms
bathrooms
location_score
age_years
distance_city_km
lot_size_sqft
has_garage
has_pool
renovation_years_ago
```

Target:

```text
house_price_inr
```

---

## Q16. Simple vs Multiple Linear Regression

### Simple Linear Regression

Uses one predictor:

```text
area_sqft → house_price_inr
```

### Multiple Linear Regression

Uses multiple predictors:

```text
Multiple Property Features → house_price_inr
```

Multiple regression can capture additional information that cannot be represented by house area alone.

---

## Q17. Performance Comparison

Models are compared using:

- MSE
- MAE
- RMSE
- R²
- Adjusted R²

A model with lower error values and higher R² generally provides better predictive performance.

---

# 🔄 Part F: Polynomial Regression

## Q18. Polynomial Regression

Polynomial Regression extends linear regression by adding polynomial terms.

For degree 2:

```text
y = β0 + β1x + β2x²
```

In this project, polynomial regression is applied to the relationship between house area and house price.

---

## Q19. Linear vs Polynomial Regression Visualization

The visualization compares:

- Actual house prices
- Linear regression predictions
- Polynomial regression predictions

The comparison helps determine whether a curved relationship captures the data better than a straight line.

---

## Q20. Overfitting and Underfitting

Training and testing performance are compared to identify model complexity problems.

### Underfitting

If both training and testing performance are poor, the model may be too simple.

### Overfitting

If training performance is very strong but testing performance is substantially weaker, the model may be overfitting.

Polynomial models require careful selection of degree because excessive complexity can increase variance.

---

# ⚙️ Part G: Gradient Descent

## Q21. What is Gradient Descent?

Gradient Descent is an optimization algorithm used to minimize a model's loss function.

General update:

```text
Parameter_new = Parameter_old - Learning_Rate × Gradient
```

The learning rate controls the size of each update.

---

## Q22. Batch Gradient Descent

Batch Gradient Descent calculates the gradient using the entire training dataset before updating model parameters.

**Advantages**
- Stable updates
- Smooth convergence

**Limitation**
- Can be computationally expensive for large datasets

---

## Q23. Stochastic Gradient Descent

Stochastic Gradient Descent updates model parameters using one training example at a time.

**Advantages**
- Frequent updates
- Can be faster for large datasets

**Limitation**
- Updates can be noisy

---

## Q24. Mini-Batch Gradient Descent

Mini-Batch Gradient Descent uses a small batch of training examples for each update.

It provides a balance between Batch Gradient Descent and SGD.

**Advantages**
- More efficient than full-batch updates
- Less noisy than pure SGD
- Suitable for vectorized computation

---

## Q25. Gradient Descent Comparison

The project compares:
- Batch Gradient Descent
- Stochastic Gradient Descent
- Mini-Batch Gradient Descent

using:
1. Loss convergence
2. Training time

### 📉 Convergence Graph

The convergence graph shows how model loss changes across iterations or epochs. A decreasing loss indicates that the optimization process is moving toward a lower-error solution.

### ⏱️ Training Time Graph

The training-time graph compares how long each gradient descent approach takes to train and highlights computational trade-offs.

---

# ⚖️ Part H: Bias-Variance Analysis

## Q26. Bias and Variance Comparison

The project compares:

- Simple Linear Regression
- Multiple Linear Regression
- Polynomial Regression

Simple models may have higher bias because they make stronger assumptions. More complex models can reduce bias but may increase variance.

---

## Q27. Effect of Model Complexity

Increasing model complexity can improve the ability to capture patterns in training data.

However, excessive complexity may cause:

```text
Training Error ↓
Test Error ↑
```

This indicates possible overfitting.

---

## Q28. Best Bias-Variance Balance

The best model should provide:

- Good training performance
- Good testing performance
- Reasonable model complexity
- Small train-test performance gap
- Low prediction error

The goal is a model that generalizes well to unseen data.

---

# 🏆 Part I: Final Model and Business Interpretation

## Q29. Final Model Selection

The final model is selected by comparing all evaluated approaches using:

- RMSE
- MAE
- MSE
- R²
- Adjusted R²
- Train-test performance
- Model complexity
- Generalization

The preferred model is the one that provides a strong balance between predictive accuracy and generalization.

---

## Q30. Final Business Interpretation

The predictive system can help a real estate analytics firm estimate property prices using available property characteristics.

Potential applications include:

- Property price estimation
- Supporting property valuation
- Identifying important pricing factors
- Comparing properties
- Supporting real estate decision-making
- Improving data-driven pricing strategies

---

# 🛠️ Technologies Used

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn
- Jupyter Notebook
- Microsoft Excel

---

# 📦 Python Libraries

```python
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns

from sklearn.model_selection import train_test_split
from sklearn.linear_model import LinearRegression
from sklearn.preprocessing import PolynomialFeatures, StandardScaler
from sklearn.metrics import mean_squared_error, mean_absolute_error, r2_score
```

---

# 🔬 Machine Learning Techniques

1. Simple Linear Regression
2. Multiple Linear Regression
3. Polynomial Regression
4. Batch Gradient Descent
5. Stochastic Gradient Descent
6. Mini-Batch Gradient Descent

---

# 📏 Evaluation Metrics

| Metric | Purpose | Better Value |
|---|---|---|
| MSE | Squared prediction error | Lower |
| MAE | Average absolute error | Lower |
| RMSE | Error in target-variable units | Lower |
| R² | Explained variance | Higher |
| Adjusted R² | R² adjusted for predictors | Higher |

---

# 📈 Key Data Insights

Approximate correlations with `house_price_inr`:

| Feature | Correlation |
|---|---:|
| `area_sqft` | 0.76 |
| `bedrooms` | 0.64 |
| `location_score` | 0.59 |
| `bathrooms` | 0.53 |
| `age_years` | -0.09 |

### 💡 Key Observation

`area_sqft` has the strongest positive linear correlation with house price among the listed variables. Therefore, house area is a useful feature for the initial Simple Linear Regression model.

---

# 🔄 Project Workflow

```text
Raw Real Estate Dataset
          ↓
Data Loading
          ↓
Data Understanding
          ↓
Exploratory Data Analysis
          ↓
Feature & Target Selection
          ↓
Train-Test Split
          ↓
Simple Linear Regression
          ↓
Model Evaluation
          ↓
Multiple Linear Regression
          ↓
Polynomial Regression
          ↓
Gradient Descent
          ↓
Bias-Variance Analysis
          ↓
Model Comparison
          ↓
Final Model Selection
          ↓
Business Insights
```

---

# 📁 Recommended GitHub Repository Structure

```text
Predictive-Insight-Engine/
│
├── Predictive_Insight_Engine.ipynb
├── RealEstate_HousePrice_Dataset_4200.xlsx
├── README.md
│
└── screenshots/
    ├── area_vs_price.png
    ├── correlation_heatmap.png
    ├── regression_line.png
    ├── residual_plot.png
    ├── polynomial_comparison.png
    └── gradient_descent_comparison.png
```

---

# 🚀 How to Run the Project

### 1. Clone the repository

```bash
git clone YOUR_GITHUB_REPOSITORY_URL
```

### 2. Install dependencies

```bash
pip install pandas numpy matplotlib seaborn scikit-learn openpyxl
```

### 3. Open the notebook

```text
Predictive_Insight_Engine.ipynb
```

### 4. Run all cells

Run the notebook from top to bottom. Keep the Excel dataset in the project folder or update the dataset path in the notebook.

---

# 🧠 Learning Outcomes

This project demonstrates:

- Supervised learning
- Regression problem formulation
- Feature-target relationships
- Linear regression
- Multiple regression
- Polynomial regression
- Regression assumptions
- Residual analysis
- Model evaluation
- Gradient descent optimization
- Batch, SGD and Mini-Batch optimization
- Bias-variance tradeoff
- Overfitting and underfitting
- Model comparison
- Business interpretation

---

# 🏁 Conclusion

The **Predictive Insight Engine** demonstrates a complete regression-based machine learning workflow for house price prediction.

Different regression techniques are evaluated to understand how model complexity, optimization techniques, bias, and variance affect predictive performance.

The project highlights the importance of evaluating models not only on training performance but also on unseen test data.

The final model should be selected based on predictive accuracy, generalization performance, and an appropriate balance between model complexity and business interpretability.

---

## 👨‍💻 Author

**Mahesh Lohar**

**Project Category:** Data Science | Machine Learning | Regression | Real Estate Analytics
