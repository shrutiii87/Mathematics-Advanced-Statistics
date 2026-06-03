# 📊 Analyzing Income Distribution and Household Demographics

> **Skill Education** — Shaping Skills for Scaling Higher...!!!

A complete **Theory + Practical** Statistics project analyzing a real-world Household Dataset of 200 records. The project covers types of data, central tendency, measures of dispersion, distribution properties, skewness & kurtosis — implemented in both **Python (Jupyter Notebook)** and **Excel (with Pivot Tables, Statistics Sheet & Dashboard)**.

---

## 📋 Project Details

| Field | Details |
|-------|---------|
| **Title** | Analyzing Income Distribution and Household Demographics |
| **Duration** | 4 Hours |
| **Type** | Theory + Practical |
| **Tools Used** | Python · Excel |
| **Libraries** | Pandas · NumPy · Matplotlib · Seaborn · SciPy |

---

## 🎯 Objective

> You are a data analyst working for a **socio-economic research organization**. Your task is to analyze a dataset containing information about household demographics, incomes, and education levels. Through this project, you will explore types of data, apply statistical concepts, calculate descriptive statistics, and analyze distribution properties including skewness and kurtosis.

---

## 🗂️ Project Files

| File | Description |
|------|-------------|
| 📓 `Descriptive_Booster.ipynb` | Jupyter Notebook — all Python code, charts & insights |
| 📊 `Household_Dataset_200_Records.xlsx` | Excel file — Dataset + Statistics + Pivot Tables + Dashboard |
| 📄 `PART_-_A__Theory_.pdf` | Theory document — definitions, formulas & diagrams |
| 📘 `README.md` | Project documentation (this file) |

---

## 🧩 Dataset Structure

> AI-Generated Dataset · **200 Records** · Sheet: `Household_Data`

| Column Name | Data Type | Description |
|-------------|-----------|-------------|
| `Household_ID` | Categorical | Unique household identifier (HH001–HH200) |
| `Age_of_Household_Head` | Numerical | Age of the head of household (23–75) |
| `Household_Income` | Numerical | Monthly income in local currency ₹ (10,106–1,49,885) |
| `Education_Level` | Categorical | Primary / Secondary / Graduate / Post-Grad |
| `Family_Size` | Numerical | Total number of family members (1–10) |
| `Owns_House` | Categorical | Yes / No |
| `Urban_Rural` | Categorical | Urban (103 records) / Rural (97 records) |

---
## 🎬 Project Demo GIF

<img width="800" height="450" alt="Descriptive booster GIf" src="https://github.com/user-attachments/assets/a84e3162-8729-4446-a020-cd26fab4adb5" />

> 📸 short tour of Excel output :-
---
## 🎬 Project Demo GIF

<img width="800" height="420" alt="Descriptive_Booster_ipynb GIF" src="https://github.com/user-attachments/assets/7f73ac5c-91e7-477a-b3d6-cdca13c9482c" />

> 📸 short tour of Excel output :-
---
## 📗 Excel Workbook — Sheet Breakdown

The Excel file `Household_Dataset_200_Records.xlsx` contains **5 sheets**:

### 📋 Sheet 1 — `Household_Data`
Raw dataset with all 200 household records across 7 columns.

### 📐 Sheet 2 — `Statistics`
Key statistical measures calculated directly in Excel:

| Measure | Value |
|---------|-------|
| Average Income | ₹75,182.02 |
| Median Income | ₹72,085 |
| Max Income | ₹1,49,885 |
| Min Income | ₹10,106 |
| Standard Deviation | ₹42,285.05 |
| IQR | ₹72,998.5 |
| Average Family Size | 5.59 |
| Average Age | 47.5 |

### 📊 Sheet 3 — `Pivot Tables`
Three Pivot Tables built to analyze the dataset:

**Pivot 1 — Average Income by Education Level:**

| Education Level | Avg Household Income |
|----------------|---------------------|
| Graduate | ₹82,390 |
| Secondary | ₹79,205 |
| Post-Grad | ₹74,833 |
| Primary | ₹61,884 |

**Pivot 2 — Count by Urban/Rural & House Ownership:**

| Area | Count |
|------|-------|
| Urban | 103 |
| Rural | 97 |

| Owns House | Count |
|------------|-------|
| No | 109 |
| Yes | 91 |

**Pivot 3 — Average Income by Age:** (Age-wise breakdown from 23 to 75)

### 📈 Sheet 4 — `Dashboard`
Visual dashboard built in Excel summarizing key metrics and charts.

### 💡 Sheet 5 — `Data Story & Insights`
Narrative data story explaining findings and conclusions from the analysis.

---

## ✅ Task Checklist

### 🔶 Part A — Theory & Definitions (`PART_-_A__Theory_.pdf`)

- [x] **Q1. Define with examples**
  - Types of Data: Numerical & Categorical
  - Types of Statistics: Descriptive vs. Inferential
  - What is Descriptive Statistics?

- [x] **Q2. Explain the difference between**
  - Mean, Median, Mode
  - Range, Variance, Standard Deviation

- [x] **Q3. Explain with neat diagrams & formulas**
  - Gaussian Distribution
  - Log Normal Distribution
  - 3-Sigma Rule / Empirical Rule
  - Percentiles
  - Quartiles & Five-Number Summary
  - Skewness
  - Kurtosis

---

### 🔶 Part B — Practical

#### 🐍 Python (`Descriptive_Booster.ipynb`)

- [x] **Task 3 — Types of Data** — Identify categorical vs numerical columns
- [x] **Task 4 — Central Tendency** — Mean, Median, Mode for Income & Age
- [x] **Task 5 — Measures of Dispersion** — Range, Variance, Std Dev, IQR
- [x] **Task 6 — Distribution** — Histogram, Gaussian Curve, Skewness & Kurtosis
- [x] **Task 7 — Data Categorization** — Income across Education & Urban/Rural

#### 📗 Excel (`Household_Dataset_200_Records.xlsx`)

- [x] Statistics Sheet — Avg, Median, Max, Min, Std Dev, IQR, Avg Family Size, Avg Age
- [x] Pivot Table 1 — Average Income by Education Level
- [x] Pivot Table 2 — Count by Urban/Rural and House Ownership
- [x] Pivot Table 3 — Average Income by Age
- [x] Dashboard — Visual summary of key metrics
- [x] Data Story & Insights — Written narrative of findings

---

## 🧪 Python — Practical Breakdown

### 🔹 Task 3 — Types of Data

```python
numerical_cols   = df.select_dtypes(include=['number']).columns.tolist()
categorical_cols = df.select_dtypes(include=['object']).columns.tolist()
```

| Type | Columns |
|------|---------|
| **Numerical** | `Age_of_Household_Head`, `Household_Income`, `Family_Size` |
| **Categorical** | `Household_ID`, `Education_Level`, `Owns_House`, `Urban_Rural` |

---

### 🔹 Task 4 — Central Tendency

```python
income_mean   = df['Household_Income'].mean()    # ₹75,182
income_median = df['Household_Income'].median()  # ₹72,085
income_mode   = df['Household_Income'].mode()[0] # ₹10,106

age_mean   = df['Age_of_Household_Head'].mean()    # 47.5
age_median = df['Age_of_Household_Head'].median()  # 48.0
```

| Measure | 💰 Household Income | 👤 Age |
|---------|-------------------|-------|
| Mean | ₹75,182 | 47.5 |
| Median | ₹72,085 | 48.0 |
| Mode | ₹10,106 | — |

📌 **Insight:**
- **Income:** Mean > Median → slight right skew; a few high earners pull the average up
- **Age:** Mean ≈ Median → perfectly symmetric distribution, no skew

---

### 🔹 Task 5 — Measures of Dispersion

```python
income_range    = df['Household_Income'].max() - df['Household_Income'].min()
income_variance = df['Household_Income'].var()
income_std_dev  = df['Household_Income'].std()

Q1  = df['Household_Income'].quantile(0.25)  # ₹37,102
Q3  = df['Household_Income'].quantile(0.75)  # ₹1,10,100
IQR = Q3 - Q1                                # ₹72,998
```

| Measure | Value |
|---------|-------|
| Min Income | ₹10,106 |
| Max Income | ₹1,49,885 |
| Q1 (25th Percentile) | ₹37,102 |
| Q3 (75th Percentile) | ₹1,10,100 |
| IQR | ₹72,998.5 |
| Standard Deviation | ₹42,285 (56% of mean) |

📌 **Insight:** IQR of ₹72,998 is very large → **high income inequality**. Std Dev at 56% of the mean confirms extremely high variability across households.

---

### 🔹 Task 6 — Distribution Analysis

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
income_skew = df['Household_Income'].skew()  # 0.14
income_kurt = df['Household_Income'].kurt()  # -1.27
```

| Measure | Value | Interpretation |
|---------|-------|----------------|
| Skewness | **0.14** | Nearly symmetric — very slight right tail |
| Kurtosis | **−1.27** | Platykurtic — flatter than a normal bell curve |

📌 **Insight:** Skewness of 0.14 (between −0.5 and +0.5) → approximately normal shape. Kurtosis of −1.27 → income spread evenly, no sharp peak concentration.

---

### 🔹 Task 7 — Data Categorization

```python
# Urban vs Rural — FacetGrid Histogram
g = sns.FacetGrid(df, col='Urban_Rural', hue='Urban_Rural', height=5)
g.map_dataframe(sns.histplot, x='Household_Income', kde=True)

# Age by Education Level — Histogram + KDE
sns.histplot(x=df['Age_of_Household_Head'], hue=df['Education_Level'],
             multiple='dodge', bins=10, kde=True,
             palette=['purple', 'red', 'yellow', 'green'])

# Family Size by Education Level — Boxplot
sns.boxplot(data=df, x='Family_Size', hue='Education_Level', gap=0.2)
```

📌 **Insight:** All education groups overlap heavily in age distribution → age alone is not a reliable predictor of education level.

---

## 📊 Visualizations

| # | Visual | Tool | Purpose |
|---|--------|------|---------|
| 1 | Histogram + KDE — Household Income | Python | Show income distribution shape |
| 2 | Gaussian Normal Curve overlay | Python | Compare actual vs theoretical distribution |
| 3 | FacetGrid Histogram — Urban vs Rural | Python | Compare income by area type |
| 4 | Histogram + KDE — Age by Education Level | Python | Show age overlap across education groups |
| 5 | Boxplot — Family Size by Education Level | Python | Compare family size spread per education group |
| 6 | KDE Plot — Age vs Income Distribution | Python | Density-based education level comparison |
| 7 | Pivot Charts & Dashboard | Excel | High-level summary of all key metrics |

---

## 📌 Key Insights

✔️ **Income is right-skewed** — Mean (₹75,182) > Median (₹72,085); high earners pull the average up

✔️ **High income inequality** — IQR of ₹72,998 and Std Dev of 56% of mean confirm very wide spread

✔️ **Age is symmetric** — Mean ≈ Median ≈ 48; no skew in the age data

✔️ **Platykurtic income** — Kurtosis of −1.27 means income is flat, not concentrated around any peak

✔️ **Graduate households earn the most** — Avg ₹82,390 vs Primary at ₹61,884 (Excel Pivot)

✔️ **Urban vs Rural split is nearly even** — 103 Urban, 97 Rural households

✔️ **More households don't own a house** — 109 No vs 91 Yes (Excel Pivot)

✔️ **Age groups overlap across education levels** — No clear age-based separation between education categories

---

## 🛠️ Tools & Technologies

| Tool | Usage |
|------|-------|
| **Python** | Core programming language |
| **Pandas** | Data loading, `mean()`, `median()`, `mode()`, `quantile()`, `skew()`, `kurt()` |
| **NumPy** | `linspace` for Gaussian curve generation |
| **Matplotlib** | Figure layout, axis labels, grid styling |
| **Seaborn** | `histplot`, `boxplot`, `kdeplot`, `FacetGrid` |
| **SciPy (stats)** | `norm.pdf` for Gaussian curve fitting |
| **Microsoft Excel** | Statistics Sheet, Pivot Tables, Dashboard, Data Story |
| **Jupyter Notebook** | Interactive Python development environment |

---

## 🚀 How to Run

### Python
1. Clone or download this repository
2. Install required libraries:
   ```bash
   pip install pandas numpy matplotlib seaborn scipy openpyxl
   ```
3. Place `Household_Dataset_200_Records.xlsx` in the same folder as the notebook
4. Open `Descriptive_Booster.ipynb` in Jupyter Notebook or JupyterLab
5. Run all cells from top to bottom — each section ends with a 📌 INSIGHT

### Excel
1. Open `Household_Dataset_200_Records.xlsx` in Microsoft Excel
2. Navigate through the 5 sheets: `Household_Data` → `Statistics` → `Pivot Tables` → `Dashboard` → `Data Story & Insights`
3. All formulas and pivots are pre-built and ready to explore

> Refer to `PART_-_A__Theory_.pdf` for conceptual background on each topic.

---

## 🌟 Future Enhancements

- [ ] Add **Correlation Analysis** — Income vs Age, Income vs Family Size
- [ ] Perform **Hypothesis Testing** — t-test for Urban vs Rural income difference
- [ ] Build an **interactive Streamlit dashboard** for live filtering
- [ ] Add **outlier detection** with Z-score and IQR flagging visuals
- [ ] Extend dataset to 1000+ records for more robust statistical conclusions

---

## ✅ Submission Checklist

- [x] Practical implementation in Jupyter Notebook (Python)
- [x] Practical implementation in Excel (Statistics, Pivot Tables, Dashboard)
- [x] All charts clearly labelled with short interpretations (📌 INSIGHT)
- [x] Theory PDF with definitions, diagrams & formulas for all concepts
- [x] Dataset file included (200 records, AI-generated)
- [x] Clear and descriptive README.md

---

## 👩‍💻 Shruti Bhawsar
📍 Ahmedabad, Gujarat

---

> ⭐ If you found this project helpful, give it a star and feel free to fork!
>
> 📊 Clean Data · Sharp Stats · Confident Insights
