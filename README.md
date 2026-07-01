# Titanic Survival  Statistical Analysis

Statistical deep-dive into the Titanic passenger dataset, examining what factors were actually associated with survival and which of those associations hold up to scrutiny as genuine causal relationships versus confounded correlations.

Completed as part of the AnalystLab Africa data analytics internship program.

---

## 📋 Project Overview

This project moves beyond descriptive summaries into formal hypothesis testing, using the Titanic dataset to answer a central question: **which passenger characteristics were statistically associated with survival, and why?**

The analysis combines:
- Descriptive statistics & probability distributions
- Formal hypothesis testing (t-tests, chi-square tests)
- Correlation analysis (point-biserial & Pearson)
- A critical correlation-vs-causation discussion grounded in the historical record

---

## 🗂️ Dataset

| Field | Description |
|---|---|
| **Source** | Titanic passenger manifest dataset |
| **Key variables** | `Survived`, `Sex`, `Pclass`, `Fare`, `Embarked`, `Age` |
| **Cleaned dataset** | `Titanic_cleaned` (missing values handled, `Sex_enc` encoded) |

---

## 🔬 Statistical Tests Performed

| # | Test | Variables | Type |
|---|---|---|---|
| 1 | Independent samples t-test (Welch's) | Fare vs Survived | Two-sample mean comparison |
| 2 | Chi-square test of independence | Sex vs Survived | Categorical association |
| 3 | Chi-square test of independence | Pclass vs Survived | Categorical association |
| 4 | Point-biserial correlation | Sex_enc vs Survived | Correlation |
| 5 | Point-biserial correlation | Fare vs Survived | Correlation |
| 6 | Pearson/ordinal correlation | Pclass vs Survived | Correlation |

All tests use **α = 0.05** as the significance threshold.

---

## 📊 Key Findings

- **Fare differs significantly between survivors and non-survivors** (Welch's t-test, p < 0.001) — survivors paid notably higher fares on average.
- **Sex and Survival are strongly associated** (χ², p < 0.001) — being female was strongly linked to higher survival odds.
- **Passenger Class and Survival are strongly associated** (χ², p < 0.001) — 1st class passengers survived at much higher rates.
- **Correlation strength ranking:** Sex (r ≈ 0.54) > Fare (r ≈ 0.26) > Embarked (r ≈ 0.11).

### Correlation vs Causation
A dedicated section critically evaluates **which** of these correlations reflect genuine causal mechanisms:

| Variable | Correlated with Survival? | Causal? | Why |
|---|---|---|---|
| **Sex** | Yes (r=0.54) | ✅ Yes | Documented "women and children first" evacuation protocol |
| **Fare** | Yes (r=0.26) | ❌ No | Proxy for Class/cabin location — wealth → class → lifeboat proximity → survival |
| **Embarked** | Yes (r≈0.11) | ❌ No | Confounded — Cherbourg simply had more 1st class passengers |

**Bottom line:** Sex → Survival is the one relationship with genuine causal support. Fare and Embarked are correlated with survival only because they're entangled with Passenger Class — the true structural driver.

---

## 🛠️ Tech Stack

- **Python** — Pandas, NumPy
- **SciPy** (`scipy.stats`) — t-tests, chi-square tests, point-biserial correlation
- **Matplotlib / Seaborn** — boxplots, grouped bar charts, survival-rate visualizations

---

## 📁 Deliverables

```
├── Titanic_Statistical_Analysis.ipynb   # Full notebook (tests + visualizations)
├── Titanic_cleaned.csv                  # Cleaned dataset
├── Titanic_Analysis_Report.docx         # Word report summary
└── README.md                            # This file
```

---

## ▶️ How to Run

1. Install dependencies:
   ```bash
   pip install pandas numpy scipy matplotlib seaborn
   ```
2. Open `Titanic_Statistical_Analysis.ipynb` in Jupyter.
3. Run all cells in order — hypothesis test results and visualizations render inline.

---

## 👤 Author

**Nathaniel Akomolafe**
Data Analytics Intern — Decode Lab / AnalystLab Africa

---

*This is a learning/portfolio project completed as part of a structured internship program. Statistical conclusions are scoped to this dataset and are intended for educational and demonstrative purposes.*
