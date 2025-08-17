---
title: "🌾 Global Crop Yield Modeling using FAOSTAT (1961–2023)"
author: "S. Harish Krishnan"
output: github_document
---

# Overview

This project explores **global crop yield prediction** using the FAOSTAT dataset (1961–2023) for five agriculturally diverse countries: **Australia, Brazil, India, Nigeria, and South Africa**. By preprocessing over 78,000 records and engineering a modeling-ready dataset, we built multiple machine learning models to understand patterns and predict agricultural productivity.

---

# 🧠 Problem Statement

Can we accurately predict crop yields (in tonnes per hectare) using:

- 📍 Country  
- 🌾 Crop type  
- 📅 Year  

And discover which features (e.g., crop, region, or year) are **most predictive** of yield?

---

# 📦 Dataset

- **Source**: [FAOSTAT](https://www.fao.org/faostat/) — United Nations Food and Agriculture Organization
- **Raw**: 78,164 rows × 198 columns  
- **Cleaned**: 24,655 yield records across 5 countries

### Features Used:
- `Country`, `Crop`, `Year` → Target: `Yield_tonnes_per_ha`

---

# 🧹 Data Pipeline

```r
1. Filter → Yield-only entries
2. Select → Top 5 countries
3. Reshape → Wide to long format (melt)
4. Clean → Remove missing data
5. Convert → kg/ha → tonnes/ha
6. Export → Cleaned_FAOSTAT_Yield.csv
