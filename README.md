# 📊 Course Project – Linear Regression Analysis of Internet Firewall Data

## 📌 Overview

This project applies **Linear Regression models** to a real-world dataset from the *Internet Firewall Logs* (Kaggle / UCI Machine Learning Repository).

The objective is to:

* Model and predict transmitted traffic volume (**bytes**)
* Evaluate statistical significance of predictors
* Compare single, multiple, interaction, and polynomial regression models
* Analyze model complexity using the bias–variance tradeoff

This project was completed as part of **Applied Machine Learning & Data Analytics** coursework.

---

## 📂 Dataset

Source:

* Kaggle: *Internet Firewall Data Set*
* UCI Machine Learning Repository

Number of observations: **65,532**

Main variables used:

* `bytes` (Response variable)
* `packets`
* `elapsed_time_sec`
* `pkts_sent`
* `pkts_received`
* `action` (Allow / Deny)

---

## 🧠 Models Implemented

### 1️⃣ Simple Linear Regression (Single Predictor)

Model:
$$
Y = \beta_0 + \beta_1 X + \varepsilon
$$

* Estimated coefficients
* RSS (Residual Sum of Squares)
* t-statistic and p-value
* RSE (Residual Standard Error)
* R² and correlation (r)

**Finding:**
Packets alone explains ~95% of the variance in transmitted bytes.

---

### 2️⃣ Multiple Linear Regression

Model:
$$
Y = \beta_0 + \beta_1 X_1 + \beta_2 X_2 + \varepsilon
$$

Evaluated:

* Global F-test
* Individual t-tests
* Adjusted R²
* Prediction interval
* Residual diagnostics

Feature Selection:

* Forward Selection
* Backward Elimination

**Finding:**
Additional predictors are statistically significant but provide modest improvement over packets alone.

---

### 3️⃣ Interaction Analysis

Model:
$$
Y = \beta_0 + \beta_1 X + \beta_2 D + \beta_3(X \times D)
$$

* Tested interaction between `packets` and `action`
* Interaction term not statistically significant

**Conclusion:**
Firewall action does not significantly change the slope between packets and bytes.

---

### 4️⃣ Polynomial Regression

Model:
$$
Y = \beta_0 + \beta_1 X + \beta_2 X^2
$$

Evaluation:

* Train/Test RMSE
* Bias–Variance Tradeoff analysis (degrees 1–6)

**Finding:**
Polynomial regression increases variance and worsens test performance.
The relationship between packets and bytes is predominantly linear.

---

## 📊 Key Results Summary

| Metric          | Value      |
| --------------- | ---------- |
| Single LR R²    | 0.9494     |
| Multiple LR R²  | 0.9612     |
| Linear RMSE     | 418,728.70 |
| Polynomial RMSE | 511,282.77 |
| Correlation (r) | 0.9744     |

---

## 🧪 Experimental Setup

* OLS regression via `statsmodels`
* Polynomial features via `sklearn`
* Train/Test split for model evaluation
* RMSE used for performance comparison
* Visual diagnostics included

---

## 👥 Team Contributions

**Gabil Gurbanov**

* Regression modeling
* Statistical inference
* Evaluation metrics interpretation
* Report preparation

**Vusal Shirinbayli**

* Data preprocessing
* Visualization
* Polynomial experiments
* Interaction analysis


---

## 📚 References

* UCI Machine Learning Repository – Internet Firewall Data Set
* Kaggle – Internet Firewall Logs
* James, Witten, Hastie, Tibshirani – *An Introduction to Statistical Learning*

---

## ✅ Conclusion

* Packet count is the dominant predictor of transmitted bytes.
* Multiple regression slightly improves explanatory power.
* Interaction effects are not statistically significant.
* Polynomial regression does not improve generalization.
* The underlying relationship is strongly linear.
