# Predicting Hospital Performance from Structured Data

## Overview

This project analyzes Medicare’s **Hospital Value-Based Purchasing (VBP)** program to understand what drives whether hospitals receive **financial bonuses or penalties**.

Using FY2025 performance data, I built predictive models to estimate **FY2026 bonus outcomes** and identify which performance domains matter most—especially for **safety-net hospitals**.

---

## Research Question

**Which VBP domains best predict future bonus outcomes, and do these relationships differ between safety-net and non–safety-net hospitals?**

---

## Data

* FY2025 hospital performance scores:

  * Clinical Outcomes
  * Patient & Community Engagement (PCE)
  * Safety
  * Efficiency
* FY2026 bonus/penalty outcomes
* Structural variables (beds, region, DSH%)

---

## Methods

* Exploratory Data Analysis (EDA)
* Logistic Regression (baseline, interpretable model)
* Random Forest (captures nonlinear relationships)
* SHAP analysis for model interpretability

Key preprocessing steps:

* Log transformation + standardization of skewed variables
* Mean imputation with missingness indicators (aligned with CMS methodology)
* One-hot encoding for categorical variables

---

## Key Results

* **Random Forest outperformed Logistic Regression**

  * AUC: **0.846 vs. 0.822**
  * Accuracy: **0.77 vs. 0.74**

* **Most important predictors:**

  * Patient & Community Engagement (strongest)
  * Efficiency
  * Clinical Outcomes
  * Safety (smaller but meaningful impact)

* Structural factors (beds, region, etc.) played a **much smaller role**

---

## Key Insights

* **Performance domains—not structural factors—drive bonus outcomes**
* **Nonlinear relationships matter**, making tree-based models more effective
* **Safety-net hospitals are disadvantaged**, especially in:

  * PCE
  * Efficiency
* Domain improvements can meaningfully shift bonus probability

---

## Example Insight (SHAP)

For an individual hospital:

* Strong **PCE and Safety** scores increased bonus probability
* Lower **Efficiency and Clinical Outcomes** reduced it
* Final predicted probability: **0.59 (correctly classified as bonus)**

---

## Project Structure

```
Predicting Hospital Performance from Structured Data/
│── data/
│── notebooks/
│── README.md
```

---

## Technologies Used

* Python (Pandas, NumPy)
* Scikit-learn
* Matplotlib / Seaborn
* SHAP
* Jupyter Notebook

---

## Takeaways

This project shows how combining **interpretable models (logistic regression)** with **flexible models (random forest)** and **SHAP explanations** can provide both:

* strong predictive performance
* actionable insights for healthcare decision-making

---

## Acknowledgments

Developed as part of an academic project on healthcare analytics.