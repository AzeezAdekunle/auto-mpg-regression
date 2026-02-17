# Auto MPG Regression Analysis

## Project Overview
This project builds and evaluates regression models to predict vehicle fuel efficiency (miles per gallon) using engine and design characteristics from the Auto MPG dataset. The goal is to demonstrate a complete, real-world regression workflow, including data cleaning, feature engineering, model evaluation, and interpretation.

---

## Dataset
- **Source:** Auto MPG dataset
- **Observations:** 392 vehicles
- **Target Variable:** Miles per gallon (mpg)
- **Features:** Engine displacement, horsepower, weight, acceleration, model year, and origin

---

## Methodology

### 1. Data Cleaning
- Converted non-numeric values in the `horsepower` column
- Removed rows with missing values
- Ensured correct data types for all features

### 2. Feature Engineering
- Created a **power-to-weight ratio** (horsepower / weight)
- Created **engine size per cylinder** (displacement / cylinders)
- Retained original variables after empirical evaluation showed improved performance

### 3. Feature Scaling
- Applied standardization to input features only
- Scaling was performed using training data statistics to avoid data leakage

### 4. Modeling
- **Baseline model:** Multiple Linear Regression
- **Regularized model:** Ridge Regression
- Models were compared using MAE and R² on a held-out test set

### 5. Model Diagnostics
- Residual analysis to verify linearity and homoscedasticity
- Variance Inflation Factor (VIF) used to assess multicollinearity

### 6. Cross-Validation
- 5-fold cross-validation used to assess model stability across different data splits

---

## Results

| Model | Test R² | Test MAE |
|------|--------|----------|
| Linear Regression | ~0.82 | ~10% |
| Ridge Regression | **~0.82** | **~9.7%** |

Ridge regression achieved slightly better generalization and was selected as the final model.

---

## Key Insights
- Feature engineering improved predictive accuracy when original predictors were retained
- Regularization improved model robustness in the presence of correlated features
- Linear models can perform competitively on structured tabular data with proper diagnostics

---

## Tools & Libraries
- Python
- pandas, numpy
- scikit-learn
- matplotlib, seaborn

---

## Conclusion
This project demonstrates best practices for regression modeling on real-world tabular data, balancing predictive performance, interpretability, and robustness.

