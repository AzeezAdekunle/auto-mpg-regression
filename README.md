# Auto MPG Regression Analysis

## Overview
This project applies regression modeling techniques to predict vehicle fuel efficiency (miles per gallon, MPG) using engine and design characteristics from the Auto MPG dataset. The objective is to demonstrate a complete, real-world regression workflow, from data cleaning and feature engineering to model diagnostics, regularization, and cross-validation.

The project emphasizes **model interpretability, robustness, and generalization**, rather than relying solely on complex models.

---

## Dataset
- **Source:** Auto MPG dataset
- **Number of observations:** 392 vehicles
- **Target variable:** Miles per gallon (mpg)
- **Features include:**  
  Cylinders, displacement, horsepower, weight, acceleration, model year, and origin

---

## Methodology

### 1. Data Cleaning
- Converted non-numeric entries in the `horsepower` column to numeric values
- Removed rows with missing values due to their small proportion
- Ensured correct data types for all features

---

### 2. Feature Engineering
To capture interaction-like relationships between engine characteristics, the following features were engineered:
- **Power-to-weight ratio:** horsepower / weight  
- **Engine size per cylinder:** displacement / cylinders  

Empirical evaluation showed that retaining both original and engineered features improved predictive performance.

---

### 3. Feature Scaling
- Input features (`X`) were standardized using training-set statistics
- The target variable (`mpg`) was **not scaled**
- Scaling was applied to support coefficient interpretation and regularized models
- Care was taken to avoid data leakage

---

### 4. Modeling
Two regression models were evaluated:
- **Multiple Linear Regression (baseline)**
- **Ridge Regression (regularized model)**

Performance was assessed using:
- **R² (coefficient of determination)**
- **Mean Absolute Error (MAE)** expressed as a percentage

---

### 5. Model Diagnostics
- Residual analysis confirmed linearity and homoscedasticity
- Residuals were centered around zero with no clear patterns
- Variance Inflation Factor (VIF) was used to assess multicollinearity

Multicollinearity among engine-related features motivated the use of Ridge regression.

---

### 6. Cross-Validation
- 5-fold cross-validation was performed to evaluate model stability
- Cross-validation provided a realistic estimate of out-of-sample performance
- Results confirmed that the model generalizes reasonably well beyond a single train-test split

---

## Results

| Model | Test R² | Test MAE |
|------|--------|----------|
| Linear Regression | ~0.82 | ~10.0% |
| Ridge Regression | **~0.82** | **~9.7%** |

Ridge regression achieved slightly lower MAE and improved coefficient stability.

---

## Final Model Selection
Ridge regression was selected as the final model due to:
- Comparable explanatory power to linear regression
- Improved robustness in the presence of correlated predictors
- Slightly better generalization performance

This choice reflects best practices in real-world regression modeling.

---

## Tools & Libraries
- Python
- pandas, numpy
- scikit-learn
- matplotlib, seaborn

---

## Conclusion
This project demonstrates a structured and reproducible approach to regression analysis on real-world tabular data. By combining feature engineering, diagnostics, regularization, and cross-validation, the final model achieves strong predictive performance while remaining interpretable and stable.

