# Startup Growth Prediction Model
### ML Classification · Nairobi Tech Ecosystem · iHub Research · 2022–2023

![Accuracy](https://img.shields.io/badge/Model%20Accuracy-85%25-0D7377?style=flat-square)
![Stack](https://img.shields.io/badge/Stack-Python%20%7C%20scikit--learn%20%7C%20XGBoost%20%7C%20R-1B3A6B?style=flat-square)
![Organisation](https://img.shields.io/badge/Organisation-iHub%20Research-223D5F?style=flat-square)

---

## Overview

A machine learning classification model identifying high-growth startups in Nairobi's innovation ecosystem, built for a regional innovation mapping project funded by a major international development partner. Outputs were used to guide targeted investment and support across East Africa's tech ecosystem.

---

## Problem Statement

> *Given a startup's characteristics at a point in time — funding, team, market, traction — can we predict which firms are likely to achieve high growth over the next 12–18 months?*

---

## Methodology

### Data Pipeline
```
Raw startup data (survey + secondary sources)
        │
        ├── Automated validation (Python)     → 40% reduction in cleaning time
        ├── Deduplication & standardisation
        ├── Feature engineering
        └── Cleaned dataset (n = ~450 startups)
```

### Feature Engineering

| Feature Category | Variables |
|-----------------|-----------|
| Funding | Total raised, # rounds, last round size |
| Team | Founder count, technical co-founder (Y/N), team size |
| Market | Vertical (fintech, agri, health, edtech, logistics), B2B/B2C |
| Traction | Revenue, user growth rate, partnerships |
| Geography | Nairobi hub, upcountry, diaspora-linked |

### Modelling
```
Baseline: Logistic Regression
Ensemble: Random Forest + XGBoost (final model)

Tuning:   GridSearchCV with 5-fold cross-validation
Eval:     Accuracy, Precision, Recall, F1, AUC-ROC
Result:   85% accuracy on held-out test set
```

### Class Imbalance Handling
- High-growth startups = minority class (~25% of sample)
- Applied SMOTE oversampling on training set only
- Evaluated on original distribution

---

## Results

| Metric | Score |
|--------|-------|
| Accuracy | **85%** |
| Precision (high-growth) | 0.81 |
| Recall (high-growth) | 0.78 |
| AUC-ROC | 0.89 |

**Top 5 features by importance:**
1. Revenue growth rate (last 12 months)
2. Technical co-founder present
3. Total funding raised
4. B2B model
5. Active partnerships count

---

## Files

```
startup-growth-prediction/
├── data/
│   └── startups_cleaned.csv         # Anonymised dataset
├── notebooks/
│   ├── 01_eda.ipynb                 # Exploratory data analysis
│   ├── 02_feature_engineering.ipynb
│   ├── 03_modelling.ipynb           # Model training & evaluation
│   └── 04_interpretation.ipynb     # Feature importance & SHAP
├── src/
│   ├── validate.py                  # Automated data validation pipeline
│   ├── features.py                  # Feature engineering functions
│   └── model.py                     # Training & prediction utilities
├── outputs/
│   ├── model_results.xlsx
│   └── feature_importance.png
└── README.md
```

---

## Stack

`Python` · `scikit-learn` · `XGBoost` · `pandas` · `numpy` · `SHAP` · `R` · `SPSS` · `Power BI` · `Tableau`

---

## Impact

- Findings shaped ICT innovation support frameworks across multiple East African tech hubs
- Automated validation pipeline adopted as standard across 3 national-level iHub projects
- Recognised as lead data consultant on the regional innovation mapping project
