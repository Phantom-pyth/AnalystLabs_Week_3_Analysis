# Housing Prices — Statistical Analysis

Statistical exploration of residential housing data, applying descriptive statistics, probability distributions, and formal hypothesis testing to identify which property characteristics are genuinely associated with sale price.

Completed as part of the Decode Lab / AnalystLab Africa data analytics internship program.

---

## 📋 Project Overview

This project applies a rigorous statistical lens to a housing dataset, moving past simple "bigger house, higher price" intuition to test specific hypotheses about *which* features matter, *how strongly*, and whether observed relationships are likely to be meaningful versus coincidental.

The analysis combines:
- Descriptive statistics (central tendency, spread, skewness)
- Probability distribution fitting on price and key continuous variables
- Formal hypothesis testing (t-tests, ANOVA, chi-square where applicable)
- Correlation analysis between numerical features and price

---

## 🗂️ Dataset

| Field | Description |
|---|---|
| **Source** | Housing dataset (residential property records) |
| **Key variables** | `Price`, `Area/SqFt`, `Bedrooms`, `Bathrooms`, `Location`, `Age of Property` |
| **Cleaned dataset** | `Housing_cleaned` (missing values handled, categorical encodings applied) |

---

## 🔬 Statistical Tests Performed

| # | Test | Variables | Type |
|---|---|---|---|
| 1 | Descriptive statistics & distribution check | Price | Normality / skewness assessment |
| 2 | Independent samples t-test | Price by binary feature (e.g. has garage/basement) | Two-sample mean comparison |
| 3 | One-way ANOVA | Price across categorical groups (e.g. Location/Neighborhood) | Multi-group mean comparison |
| 4 | Pearson correlation | Area/SqFt vs Price | Correlation |
| 5 | Pearson correlation | Bedrooms / Bathrooms vs Price | Correlation |
| 6 | Chi-square test of independence | Categorical feature vs Price bracket | Categorical association |

All tests use **α = 0.05** as the significance threshold.

---

## 📊 Key Findings

- **Price is right-skewed**, consistent with most real-world housing markets — a small number of high-value properties pull the mean above the median.
- **Area/SqFt shows the strongest correlation with Price** among numerical features tested.
- **Location/Neighborhood produces statistically significant differences in mean price** (ANOVA, p < 0.05), confirming geography is a meaningful price driver.
- Feature-by-feature significance results are summarized in a consolidated results table within the notebook for quick reference.

### Practical Interpretation
As with any observational housing data, statistically significant association does **not** automatically imply that a feature *causes* price changes in isolation — features like size, location, and amenities are often correlated with each other (e.g. larger homes tend to also be newer or in particular neighborhoods). Where relevant, the notebook flags features that may be acting as proxies for an underlying driver rather than independent causes.

---

## 🛠️ Tech Stack

- **Python** — Pandas, NumPy
- **SciPy** (`scipy.stats`) — t-tests, ANOVA, chi-square, distribution fitting
- **statsmodels** — supplementary regression/ANOVA diagnostics
- **Matplotlib / Seaborn** — distribution plots, boxplots, correlation heatmaps

---

## 📁 Deliverables

```
├── Housing_Statistical_Analysis.ipynb   # Full notebook (tests + visualizations)
├── Housing_cleaned.csv                  # Cleaned dataset
├── Housing_Analysis_Report.docx         # Word report summary
└── README.md                            # This file
```

---

## ▶️ How to Run

1. Install dependencies:
   ```bash
   pip install pandas numpy scipy statsmodels matplotlib seaborn
   ```
2. Open `Housing_Statistical_Analysis.ipynb` in Jupyter.
3. Run all cells in order — hypothesis test results and visualizations render inline.

---

## 👤 Author

**Nathaniel Akomolafe**
Data Analytics Intern — Decode Lab / AnalystLab Africa

---

*This is a learning/portfolio project completed as part of a structured internship program. Statistical conclusions are scoped to this dataset and are intended for educational and demonstrative purposes.*
