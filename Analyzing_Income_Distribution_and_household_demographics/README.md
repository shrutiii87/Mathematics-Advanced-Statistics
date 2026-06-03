
---
## 🎬 Project Demo GIF

<img width="800" height="450" alt="Descriptive booster GIf" src="https://github.com/user-attachments/assets/a84e3162-8729-4446-a020-cd26fab4adb5" />

> 📸 short tour of notebook output :-
---

# 📊 Analyzing Income Distribution and Household Demographics

> **Skill Education** — Shaping Skills for Scaling Higher...!!!

A complete **Theory + Practical** Statistics project built on a real-world Household Dataset of 200 records. The project explores types of data, central tendency, dispersion, distribution properties, skewness, kurtosis — and visualizes income patterns across education levels and urban/rural areas using Python.

---

## 📋 Project Details

| Field | Details |
|-------|---------|
| **Title** | Analyzing Income Distribution and Household Demographics |
| **Duration** | 4 Hours |
| **Type** | Theory + Practical |
| **Language** | Python |
| **Libraries** | Pandas · NumPy · Matplotlib · Seaborn · SciPy |

---

## 🎯 Objective

> You are a data analyst working for a **socio-economic research organization**. Your task is to analyze a dataset containing information about household demographics, incomes, and education levels. Through this project, you will explore types of data, apply statistical concepts, calculate descriptive statistics, and analyze distribution properties including skewness and kurtosis.

---

## 🗂️ Project Files

| File | Description |
|------|-------------|
| 📓 `Descriptive_Booster.ipynb` | Main Jupyter Notebook — all code, outputs & insights |
| 📊 `Household_Dataset_200_Records.xlsx` | Dataset — 200 household records across 7 columns |
| 📄 `PART_-_A__Theory_.pdf` | Theory document — definitions, formulas & diagrams |
| 📘 `README.md` | Project documentation (this file) |

---

## 🧩 Dataset Structure

> Generated using an AI Tool · 200+ Records

| Column Name | Data Type | Description |
|-------------|-----------|-------------|
| `Household_ID` | Categorical | Unique household identifier |
| `Age_of_Household_Head` | Numerical | Age of the head of household |
| `Household_Income` | Numerical | Monthly income in local currency (₹) |
| `Education_Level` | Categorical | Primary / Secondary / Graduate / Post-Grad |
| `Family_Size` | Numerical | Total number of family members |
| `Owns_House` | Categorical | Yes / No |
| `Urban_Rural` | Categorical | Urban or Rural |

---

## ✅ Task Checklist

### 🔶 Part A — Theory & Definitions

- [x] **1. Define with examples from the dataset**
  - Types of Data: Numerical & Categorical
  - Types of Statistics: Descriptive vs. Inferential
  - What is Descriptive Statistics?

- [x] **2. Explain the difference between**
  - Mean, Median, Mode
  - Range, Variance, Standard Deviation

- [x] **3. Explain with neat diagrams & formulas**
  - Gaussian Distribution
  - Log Normal Distribution
  - 3-Sigma Rule / Empirical Rule
  - Percentiles
  - Quartiles & Five-Number Summary
  - Skewness
  - Kurtosis

---

### 🔶 Part B — Practical (Python)

- [x] **3. Types of Data** — Identify categorical vs numerical columns
- [x] **4. Central Tendency** — Mean, Median, Mode for Income & Age
- [x] **5. Measures of Dispersion** — Range, Variance, Std Dev, IQR
- [x] **6. Distribution** — Histogram, Gaussian Curve, Skewness & Kurtosis
- [x] **7. Data Categorization** — Income across Education & Urban/Rural

---

## 🧪 Practical Breakdown

### 🔹 3. Types of Data

```python
numerical_cols  = df.select_dtypes(include=['number']).columns.tolist()
categorical_cols = df.select_dtypes(include=['object']).columns.tolist()
```

| Type | Columns |
|------|---------|
| **Numerical** | `Age_of_Household_Head`, `Household_Income`, `Family_Size` |
| **Categorical** | `Household_ID`, `Education_Level`, `Owns_House`, `Urban_Rural` |

---

### 🔹 4. Central Tendency

```python
income_mean   = df['Household_Income'].mean()
income_median = df['Household_Income'].median()
income_mode   = df['Household_Income'].mode()[0]

age_mean   = df['Age_of_Household_Head'].mean()
age_median = df['Age_of_Household_Head'].median()
age_mode   = df['Age_of_Household_Head'].mode()[0]
```

| Measure | 💰 Household Income | 👤 Age |
|---------|-------------------|-------|
| Mean | ₹75,182 | 47.5 |
| Median | ₹72,085 | 48.0 |
| Mode | ₹10,106 | — |

📌 **Insight:**
- **Income:** Mean > Median → slight right skew; high earners pull the average up. Mode is very low — just the most repeated value, not representative.
- **Age:** Mean ≈ Median → symmetric distribution, no skew.

---

### 🔹 5. Measures of Dispersion

```python
income_range    = df['Household_Income'].max() - df['Household_Income'].min()
income_variance = df['Household_Income'].var()
income_std_dev  = df['Household_Income'].std()

Q1  = df['Household_Income'].quantile(0.25)   # ₹37,102
Q3  = df['Household_Income'].quantile(0.75)   # ₹1,10,100
IQR = Q3 - Q1                                 # ₹72,998
```

| Measure | Value |
|---------|-------|
| Q1 (25th Percentile) | ₹37,102 |
| Q3 (75th Percentile) | ₹1,10,100 |
| IQR | ₹72,998 |
| Standard Deviation | ₹42,285 (56% of mean) |

📌 **Insight:** IQR of ₹72,998 is very large → **high income inequality**. Std Dev at 56% of the mean confirms extremely high variability across households.

---

### 🔹 6. Distribution Analysis

#### Histogram of Household Income
```python
sns.histplot(df['Household_Income'], kde=True, color='red', edgecolor='black')
```
📌 Most households earn **₹20K–₹40K**. Distribution is slightly right-skewed.

#### Gaussian Normal Distribution Curve
```python
mu, sigma = df['Household_Income'].mean(), df['Household_Income'].std()
x = np.linspace(xmin, xmax, 100)
p = norm.pdf(x, mu, sigma)
plt.plot(x, p, linewidth=2.5, label='Fitted Normal Curve')
```

#### Skewness & Kurtosis
```python
income_skew = df['Household_Income'].skew()   # 0.14
income_kurt = df['Household_Income'].kurt()   # -1.27
```

| Measure | Value | Interpretation |
|---------|-------|----------------|
| Skewness | **0.14** | Nearly symmetric — very slight right tail |
| Kurtosis | **−1.27** | Platykurtic — flatter than normal bell curve |

📌 **Insight:** Skewness of 0.14 falls between −0.5 and +0.5 → approximately normal. Kurtosis of −1.27 → income is spread evenly with no sharp concentration peak.

---

### 🔹 7. Data Categorization

#### Urban vs Rural — Income Histogram
```python
g = sns.FacetGrid(df, col='Urban_Rural', hue='Urban_Rural', height=5, aspect=1.2)
g.map_dataframe(sns.histplot, x='Household_Income', kde=True)
```

#### Age by Education Level — Histogram + KDE
```python
sns.histplot(x=df['Age_of_Household_Head'], hue=df['Education_Level'],
             multiple='dodge', bins=10, kde=True,
             palette=['purple','red','yellow','green'])
```

#### Family Size by Education Level — Boxplot
```python
sns.boxplot(data=df, x='Family_Size', hue='Education_Level', gap=0.2)
```

📌 **Insight:** All education groups overlap heavily in age → age alone is not a reliable predictor of education level.

---

## 📊 Visualizations

| # | Visual | Purpose |
|---|--------|---------|
| 1 | Histogram + KDE — Household Income | Show distribution shape & spread |
| 2 | Gaussian Normal Curve overlay | Compare actual vs theoretical distribution |
| 3 | FacetGrid Histogram — Urban vs Rural | Compare income by area type |
| 4 | Histogram + KDE — Age by Education Level | Show age overlap across education groups |
| 5 | Boxplot — Family Size by Education Level | Compare family size spread per education group |
| 6 | KDE Plot — Age vs Income Distribution | Density-based comparison across education levels |

---

## 📌 Key Insights

✔️ **Income is right-skewed** — Mean (₹75,182) > Median (₹72,085); high earners pull the average up

✔️ **High income inequality** — IQR of ₹72,998 and Std Dev of 56% of mean confirm very wide spread

✔️ **Age is symmetric** — Mean ≈ Median ≈ 48; no skew present in the age data

✔️ **Platykurtic income distribution** — Kurtosis of −1.27 means income is flat, not peaked around any central value

✔️ **Education groups overlap in age** — No clear age-based separation between Primary, Secondary, Graduate, and Post-Grad households

✔️ **Urban vs Rural** income histograms reveal similar spread patterns across both settlement types

---

## 🛠️ Tools & Technologies

| Tool | Usage |
|------|-------|
| **Python** | Core programming language |
| **Pandas** | Data loading, `mean()`, `median()`, `mode()`, `quantile()`, `skew()`, `kurt()` |
| **NumPy** | `linspace` for normal curve generation |
| **Matplotlib** | Figure layout, axis labels, grid styling |
| **Seaborn** | `histplot`, `boxplot`, `kdeplot`, `FacetGrid` |
| **SciPy (stats)** | `norm.pdf` for Gaussian curve fitting |
| **Jupyter Notebook** | Interactive development environment |

---

## 🚀 How to Run

1. Clone or download this repository
2. Install required libraries:
   ```bash
   pip install pandas numpy matplotlib seaborn scipy openpyxl
   ```
3. Place `Household_Dataset_200_Records.xlsx` in the same folder as the notebook
4. Open `Descriptive_Booster.ipynb` in Jupyter Notebook or JupyterLab
5. Run all cells from top to bottom
6. Each section is labelled with its question number and ends with a 📌 INSIGHT

> Refer to `PART_-_A__Theory_.pdf` for the conceptual background behind each analysis step.

---

## 🌟 Future Enhancements

- [ ] Add **Correlation Analysis** — Income vs Age, Income vs Family Size
- [ ] Perform **Hypothesis Testing** — t-test for Urban vs Rural income difference
- [ ] Build an **interactive Streamlit dashboard** for live filtering
- [ ] Extend dataset to 1000+ records for more robust statistical conclusions
- [ ] Add **outlier detection** using Z-score and IQR methods with flagging visuals

---

## ✅ Submission Checklist

- [x] Practical implementation in Jupyter Notebook
- [x] All charts clearly labelled with short interpretations
- [x] Theory PDF with definitions, diagrams & formulas
- [x] Dataset file included
- [x] Clear and descriptive README.md

---

## 👩‍💻 Shruti Bhawsar
📍 Ahmedabad, Gujarat

---

> ⭐ If you found this project helpful, give it a star and feel free to fork!
>
> 📊 Clean Data · Sharp Stats · Confident Insights
