---
title: "🌾 Global Crop Yield Modeling using FAOSTAT (1961–2023)"
author: "S. Harish Krishnan"
output: github_document
---

# 🌍 Overview

This project explores **global crop yield prediction** using FAOSTAT data (1961–2023) for five agriculturally diverse countries: **Australia, Brazil, India, Nigeria, and South Africa**. We cleaned and processed over 78,000 records to engineer a modeling-ready dataset and built multiple machine learning models to understand yield trends and drivers of agricultural productivity.

---

# 🎯 Problem Statement

Can we predict **crop yield (tonnes per hectare)** using:

- 📍 Country  
- 🌾 Crop type  
- 📅 Year  

And identify the **most predictive features** influencing agricultural productivity across regions?

---

# 📦 Dataset

- **Source**: [FAOSTAT](https://www.fao.org/faostat/) – United Nations Food and Agriculture Organization  
- **Raw Data**: 78,164 rows × 198 columns  
- **Final Cleaned Dataset**: 24,655 yield records across 5 countries

### Key Features:
- `Country`, `Crop`, `Year`  
- **Target**: `Yield_tonnes_per_ha`

---

# 🧹 Data Pipeline

```r
1. Filter     → Yield-only entries
2. Select     → Top 5 target countries
3. Reshape    → Wide to long format (melt)
4. Clean      → Remove missing/null entries
5. Transform  → Convert kg/ha to tonnes/ha
6. Export     → Cleaned_FAOSTAT_Yield.csv
```

---

# 🤖 Modeling Approach

We evaluated multiple ML models for yield prediction:

- **Linear Regression** (baseline)
- **Random Forest Regressor (tuned)** ✅ Best performance
- **Gradient Boosting Regressor (tuned)**

**Training Strategy**:
- Standardized features  
- GridSearchCV for hyperparameter tuning  
- 5-fold cross-validation

---

# 📊 Evaluation Metrics

| Model                     | RMSE (Val) | R² (Val) |
|--------------------------|------------|------------|
| Linear Regression         | 5.72       | 0.80       |
| Random Forest (Tuned)     | 1.47       | 0.99       |
| Gradient Boosting (Tuned) | 2.84       | 0.95       |

> 🔥 Random Forest showed **best generalization** with lowest RMSE and near-perfect R².

---

# 📈 Results & Visualizations

### Key Findings:
- **Rainfall** and **arable land** were top predictors of crop yield.
- SHAP values and permutation importance confirmed consistent feature relevance across countries.

### Sample Plot:
![Feature Importance](figures/feature_importance.png)

📁 All visualizations are available in the `figures/` directory.

---

# 🔀 Reproducibility

## ✅ Requirements:
- Python 3.9+
- Libraries: `pandas`, `scikit-learn`, `matplotlib`, `seaborn`, `xgboost`, `shap`, `jupyter`

## 🚀 Run Locally:
```bash
# Clone repo
git clone https://github.com/yourusername/crop-yield-forecast.git
cd crop-yield-forecast

# Launch notebook
jupyter notebook Final_Modeling_Pipeline.ipynb
```

---

# 📬 Contact

For questions, reach out to **S. Harish Krishnan**  
📧 haricap273@gmail.com  
🔗 [LinkedIn](https://linkedin.com/in/your-profile) | [Portfolio](https://yourportfolio.com)

---
