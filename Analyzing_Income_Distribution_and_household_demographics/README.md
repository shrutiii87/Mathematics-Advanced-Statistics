# 📊 Analyzing Income Distribution & Household Demographics
A two-part Statistics project combining **Theory (Part A)** with **Hands-on Python Analysis (Part B)** to explore income distribution patterns, household demographics, and key statistical concepts using a real-world dataset of 500 household records.

---

## 🚀 Project Overview

The goal was to apply core statistical concepts — central tendency, dispersion, distribution analysis, and data categorization — to a structured household dataset. Part A covers theoretical foundations with definitions and formulas, while Part B implements them end-to-end in Python using pandas, matplotlib, seaborn, numpy, and scipy.

---

## 🎬 Project Demo GIF

<img width="800" height="450" alt="Descriptive booster GIf" src="https://github.com/user-attachments/assets/a84e3162-8729-4446-a020-cd26fab4adb5" />


> 📸 short tour of notebook output :-

---

## 📁 Project Files

| File / Folder | Description |
|---|---|
| 📓 `Analyzing_Income_Distribution_and_household_demographics.ipynb` | Main Jupyter Notebook — full Python analysis (Part B) |
| 📝 `Statistics_Part_A.docx` | Theory document — definitions, formulas, and examples |
| 📊 `PR_1.xlsx` | Source dataset — `household_dataset_500_records.xlsx` |
| 📘 `README.md` | Project documentation |

---

## 📁 Dataset Structure

**File:** `household_dataset_500_records.xlsx` &nbsp;|&nbsp; **Records:** 500 households

| Column Name | Description |
|---|---|
| `Household_ID` | Unique identifier for each household (e.g., HH0001) |
| `Age_of_Household_Head` | Age of the primary earner / household head |
| `Household_Income` | Annual household income (in ₹) |
| `Education_Level` | Education: Primary / Secondary / Graduate / Post-Graduate |
| `Family_Size` | Number of members in the household |
| `Owns_House` | Whether the household owns a house (Yes / No) |
| `Urban_Rural` | Area type: Urban or Rural |

---

## 🧩 Project Tasks Breakdown

### 🔹 Part A — Theory & Definitions

All statistical concepts are defined with formulas and real-world examples in `Statistics_Part_A.docx`.

#### ✅ Q1 — Types of Data & Statistics
- **Numerical vs Categorical** data with examples
- **Descriptive vs Inferential** statistics

#### ✅ Q2 — Key Statistical Measures

| Measure | Formula |
|---|---|
| Mean | x̄ = (Σx) / n |
| Median | Middle value of sorted data |
| Mode | Most frequently occurring value |
| Range | Max − Min |
| Variance | σ² = Σ(xᵢ − x̄)² / n |
| Standard Deviation | σ = √σ² |

#### ✅ Q3 — Distribution Concepts

| Concept | Description |
|---|---|
| Gaussian (Normal) Distribution | Bell-shaped, symmetric; Mean = Median = Mode |
| Log-Normal Distribution | Right-skewed; defined only for x > 0 |
| 3-Sigma Rule | 68% / 95% / 99.7% of data within ±1σ / ±2σ / ±3σ |
| Percentiles | Value below which P% of observations fall |
| Quartiles & IQR | Q1, Q2, Q3 split data into four equal parts; IQR = Q3 − Q1 |
| Skewness | Measures asymmetry — positive (right tail), negative (left tail) |
| Kurtosis | Measures peak sharpness — Platykurtic / Mesokurtic / Leptokurtic |

---

### 🔹 Part B — Python Analysis (Jupyter Notebook)

#### ✅ Step 1 — Import Libraries & Load Dataset
```python
import pandas as pd
import matplotlib.pyplot as plt
import numpy as np
import seaborn as sns
from scipy.stats import norm

df = pd.read_excel('household_dataset_500_records.xlsx')
```

#### ✅ Step 2 — Types of Data (Q3)
Identify Numerical vs Categorical columns programmatically:
```python
numerical_cols   = df.select_dtypes(include=['number']).columns.tolist()
categorical_cols = df.select_dtypes(include=['object']).columns.tolist()
```

**Numerical:** `Age_of_Household_Head`, `Household_Income`, `Family_Size`  
**Categorical:** `Education_Level`, `Owns_House`, `Urban_Rural`

---

#### ✅ Step 3 — Central Tendency (Q4)

Calculate Mean, Median, and Mode for **Household Income** and **Age**:

| Statistic | Household Income | Age |
|---|---|---|
| Mean | ₹57,582 | 50 years |
| Median | ₹48,138 | 50 years |
| Mode | — | 25 years |

> 💡 **Insight:** Mean > Median → **Positively Skewed (Right-Skewed)** distribution. A small group of high earners pulls the average up.

---

#### ✅ Step 4 — Measures of Dispersion (Q5)

```python
income_range   = df['Household_Income'].max() - df['Household_Income'].min()
income_variance = df['Household_Income'].var()
income_std_dev  = df['Household_Income'].std()

Q1  = df['Household_Income'].quantile(0.25)
Q3  = df['Household_Income'].quantile(0.75)
IQR = Q3 - Q1
```

> 💡 **Insight:** The dataset has a very large income range. The IQR confirms wide income spread across the middle 50% of households.

---

#### ✅ Step 5 — Distribution Analysis (Q6)

Three visualizations were produced:

**1. Histogram with KDE**
```python
sns.histplot(df['Household_Income'], kde=True, color='green', edgecolor='black')
```
> Most household incomes concentrate between ₹20,000–₹80,000 with a longer right tail.

**2. Fitted Gaussian Normal Curve**
```python
mu    = df['Household_Income'].mean()
sigma = df['Household_Income'].std()
p     = norm.pdf(x, mu, sigma)
plt.plot(x, p, linewidth=2.5, label='Fitted Normal Curve')
```

**3. Skewness & Kurtosis**
```python
income_skew = df['Household_Income'].skew()   # → 0.91
income_kurt = df['Household_Income'].kurt()   # → 0.11
```

| Metric | Value | Interpretation |
|---|---|---|
| Skewness | 0.91 | Positive → Right-skewed distribution |
| Kurtosis | 0.11 | Near 0 → Close to normal peak shape |

---

#### ✅ Step 6 — Data Categorization (Q7)

Income compared across **Education Level** and **Urban vs Rural** areas using FacetGrid histograms and boxplots:

```python
g = sns.FacetGrid(df, col="Urban_Rural", hue="Urban_Rural",
                  palette=["green", "Darkgreen"])
g.map_dataframe(sns.histplot, x="Household_Income", kde=True)
```

> 💡 **Urban vs Rural Insights:**
> - Urban areas have significantly more households overall
> - Both Urban and Rural peak in the ₹30,000–₹50,000 bracket
> - Both areas show a strong right-hand skew

---

## 📈 Key Findings

| Finding | Detail |
|---|---|
| 📊 Income Distribution | Right-skewed (Skewness = 0.91) — a minority of high earners drive the mean above the median |
| 💰 Typical Income | Median income is ₹48,138; mean is ₹57,582 |
| 🌾 Urban vs Rural | Both areas follow similar income distribution patterns with Urban having more households |
| 🎓 Education Effect | Higher education levels correlate with higher household income bands |
| 📦 Outlier Boundary | IQR method used: data beyond Q1 − 1.5×IQR or Q3 + 1.5×IQR flagged as outliers |

---

## 🛠️ Tools & Technologies Used

| Tool | Purpose |
|---|---|
| Python 3 | Core programming language |
| Pandas | Data loading, wrangling, and statistical computation |
| NumPy | Numerical operations and array handling |
| Matplotlib | Base plotting and figure customization |
| Seaborn | Statistical visualizations (histplot, FacetGrid, boxplot) |
| SciPy (stats) | Fitting Gaussian normal distribution curve |
| Jupyter Notebook | Interactive analysis and reporting environment |
| Microsoft Excel | Raw dataset storage (`household_dataset_500_records.xlsx`) |

---

## 📤 Submission Contents

| File | Description |
|---|---|
| 📓 `Analyzing_Income_Distribution_and_household_demographics.ipynb` | Complete Jupyter Notebook with code, charts, and insights |
| 📝 `Statistics_Part_A.docx` | Theory answers — definitions, formulas, tables |
| 📊 `PR_1.xlsx` | Source dataset used in the analysis |
| 📘 `README.md` | Project documentation |

---

## 📦 How to Run

1. Clone or download the repository
2. Place `household_dataset_500_records.xlsx` in the same folder as the notebook
3. Install dependencies:
   ```bash
   pip install pandas numpy matplotlib seaborn scipy openpyxl
   ```
4. Open the notebook:
   ```bash
   jupyter notebook Analyzing_Income_Distribution_and_household_demographics.ipynb
   ```
5. Run all cells from top to bottom (`Kernel → Restart & Run All`)

---

## 👩‍💻 Shruti Bhawsar
📍 Ahmedabad

⭐ If you found this project useful — give this repository a ⭐ and feel free to fork or contribute!

🎯 Clean Statistics. Sharp Visuals. Actionable Insights.
