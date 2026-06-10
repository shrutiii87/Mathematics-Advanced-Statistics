<div align="center">

<img src="https://readme-typing-svg.demolab.com?font=Fira+Code&size=32&duration=3000&pause=1000&color=6C63FF&center=true&vCenter=true&width=700&lines=🎯+Expectation+Decider;Probability+%7C+Statistics+%7C+Python;Predicting+Student+Success" alt="Typing SVG" />

<br/>

![Python](https://img.shields.io/badge/Python-3.x-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-F37626?style=for-the-badge&logo=jupyter&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-150458?style=for-the-badge&logo=pandas&logoColor=white)
![NumPy](https://img.shields.io/badge/NumPy-013243?style=for-the-badge&logo=numpy&logoColor=white)
![SciPy](https://img.shields.io/badge/SciPy-8CAAE6?style=for-the-badge&logo=scipy&logoColor=white)
![Matplotlib](https://img.shields.io/badge/Matplotlib-11557C?style=for-the-badge&logo=matplotlib&logoColor=white)

<br/>

> **A probability-based analysis system that uses 7 core statistical concepts to predict and understand student exam outcomes — applied on a real dataset of 450 students.**

<br/>

</div>

---

## 📌 Table of Contents

- [About the Project](#-about-the-project)
- [Dataset Overview](#-dataset-overview)
- [Libraries Used](#-libraries-used)
- [Topics Covered](#-topics-covered)
  - [Q1 · Basic Probability](#q1--basic-probability)
  - [Q2 · Empirical vs Theoretical](#q2--empirical-vs-theoretical-probability)
  - [Q3 · Random Variable & Binomial Distribution](#q3--random-variable--binomial-distribution)
  - [Q4 · Venn Diagram](#q4--venn-diagram)
  - [Q5 · Contingency Table](#q5--contingency-table--probability-calculations)
  - [Q6 · Independence & Mutual Exclusivity](#q6--independence--mutual-exclusivity)
  - [Q7 · Bayes' Theorem](#q7--bayes-theorem)
- [Key Findings](#-key-findings)
- [Project Structure](#-project-structure)
- [How to Run](#-how-to-run)

---

## 🎯 About the Project

**Expectation Decider** is a probability analysis project built as part of an AI, Machine Learning & Data Science course. It applies **7 fundamental probability concepts** to a student performance dataset to answer one core question:

> *What factors most affect the probability of a student passing their final exam?*

Every concept is backed by real data — no assumptions, no guesswork. The analysis moves from basic probability all the way to Bayes' Theorem, building a complete statistical picture of student performance.

---

## 📊 Dataset Overview

| Property | Detail |
|---|---|
| **File** | `student_dataset.xlsx` |
| **Total Records** | 450 students |
| **Outcome** | 312 Pass · 138 Fail |

### Columns

| Column | Type | Description |
|---|---|---|
| `study_hours` | Numeric | Weekly study hours per student |
| `attendance` | Numeric | Attendance percentage (0–100) |
| `group_discussion` | Categorical | Whether student joined group discussions (Yes / No) |
| `previous_test_score` | Numeric | Score from previous test |
| `final_exam_pass` | Categorical | Final outcome — Pass or Fail |

---

## 📦 Libraries Used

```python
import numpy as np
import pandas as pd
from scipy import stats
from scipy.stats import binom
import math
from matplotlib_venn import venn2
import matplotlib.pyplot as plt
```

| Library | Purpose |
|---|---|
| `pandas` | Data loading, filtering, crosstab |
| `numpy` | Numerical operations |
| `scipy.stats` | Binomial distribution (PMF) |
| `matplotlib` | Plotting charts |
| `matplotlib_venn` | Drawing Venn diagrams |

---

## 📚 Topics Covered

---

### Q1 · Basic Probability

> **Formula:** `P(E) = Favorable Outcomes / Total Outcomes`

Three real probability events computed from the dataset:

| Event | Favorable | Total | P(E) |
|---|---|---|---|
| Student passes the exam | 312 | 450 | **0.6933** |
| Participates in group discussion | 211 | 450 | **0.4689** |
| Attendance > 75% | 226 | 450 | **0.5022** |

```python
p_pass       = len(df[df["final_exam_pass"] == "Pass"]) / total_students   # 0.6933
p_group      = len(df[df["group_discussion"] == "Yes"]) / total_students   # 0.4689
p_attendance = len(df[df["attendance"] > 75]) / total_students             # 0.5022
```

---

### Q2 · Empirical vs Theoretical Probability

| Type | Formula | Result |
|---|---|---|
| **Empirical** | 312 / 450 | **0.6933** |
| **Theoretical** | 1 / 2 | **0.5000** |
| **Difference** | — | **+0.1933** |

- **Empirical** → based on actual observed data from 450 students
- **Theoretical** → assumes equal chance of Pass or Fail `S = {Pass, Fail}`

> Real-world performance is **19.33 percentage points** higher than the theoretical baseline — proving that effort, attendance, and engagement truly matter.

---

### Q3 · Random Variable & Binomial Distribution

**X** = Number of students passing out of **n = 3** randomly selected students

> `p = 312/450 = 0.6933` &nbsp;|&nbsp; `q = 1 - p = 0.3067` &nbsp;|&nbsp; `n = 3`

**Formula:** &nbsp; `P(X = k) = C(n,k) × pᵏ × (1−p)ⁿ⁻ᵏ`

| X | C(3,X) | P(X) | Meaning |
|---|---|---|---|
| 0 | 1 | **0.0288** | All 3 fail |
| 1 | 3 | **0.1956** | Exactly 1 passes |
| 2 | 3 | **0.4423** | Exactly 2 pass ← most likely |
| 3 | 1 | **0.3333** | All 3 pass |

```python
mean     = n * p            # = 3 × 0.6933 = 2.08
variance = n * p * (1 - p)  # = 3 × 0.6933 × 0.3067 = 0.6379
```

> In any random group of 3 students, **on average 2 will pass**. The most probable outcome is exactly 2 passing (44.23% chance).

---

### Q4 · Venn Diagram

**Set A** = Students with `study_hours > 10` &nbsp;|&nbsp; **Set B** = Students with `attendance > 80%`

```
     ╔══════════════════════════════════════╗
     ║                                      ║
     ║   ┌─────────┐       ┌─────────┐      ║
     ║   │         │       │         │      ║
     ║   │   200   │  140  │   40    │      ║
     ║   │ Only A  │  A∩B  │ Only B  │      ║
     ║   └─────────┘       └─────────┘      ║
     ║                                      ║
     ║          Neither: 70                 ║
     ╚══════════════════════════════════════╝
```

| Region | Count | % of 450 |
|---|---|---|
| Only Study > 10 hrs | 200 | 44.44% |
| **Both (A ∩ B)** | **140** | **31.11%** |
| Only Attendance > 80% | 40 | 8.89% |
| Neither | 70 | 15.56% |

**Calculated Probabilities:**

```
P(A)     = 340 / 450 = 0.7556
P(B)     = 180 / 450 = 0.4000
P(A ∩ B) = 140 / 450 = 0.3111
P(A ∪ B) = P(A) + P(B) - P(A∩B) = 0.7556 + 0.4000 - 0.3111 = 0.8444
```

---

### Q5 · Contingency Table & Probability Calculations

```
final_exam_pass    Fail   Pass   Total
group_discussion
No                  84    155     239
Yes                 54    157     211
               ─────────────────────
Total              138    312     450
```

**Joint Probability** — P(Group Discussion = Yes AND Pass)
```
= 157 / 450 = 0.3489
```

**Marginal Probability** — P(Pass)
```
= 312 / 450 = 0.6933
```

**Conditional Probability** — P(Pass | Group Discussion = Yes)
```
= P(Yes AND Pass) / P(Yes)
= (157/450) / (211/450)
= 157 / 211
= 0.7441
```

> Students who join group discussions pass at **74.41%** vs **64.85%** for those who don't — a **~9.55 percentage point** advantage.

---

### Q6 · Independence & Mutual Exclusivity

**Test for Independence:**
```
P(Pass | Group Discussion = Yes) = 0.7441
P(Pass)                          = 0.6933

0.7441 ≠ 0.6933  →  Events are DEPENDENT
```

**Test for Mutual Exclusivity:**
```
157 students both participated AND passed
→  Events are NOT Mutually Exclusive
```

> Participating in group discussions is a **dependent, co-occurring** event with passing — it positively influences exam outcomes.

---

### Q7 · Bayes' Theorem

**Goal:** Find P(Pass | High Attendance > 80%)

**Given:**

| Symbol | Value | Meaning |
|---|---|---|
| P(H \| Pass) | 0.70 | 70% of students who passed had high attendance |
| P(H \| Fail) | 0.40 | 40% of students who failed had high attendance |
| P(H) | 0.60 | 60% of all students had high attendance |
| P(Pass) | 312/450 = **0.6933** | From the dataset |
| P(Fail) | 138/450 = **0.3067** | From the dataset |

**Formula:**
```
P(Pass | H) = [ P(H | Pass) × P(Pass) ] / P(H)
```

**Step-by-step Calculation:**
```
P(Pass | H) = (0.70 × 0.6933) / 0.60
            =  0.4853 / 0.60
            =  0.8089
            =  80.89%
```

```python
P_P         = pass_count / total_students   # 0.6933
P_P_given_H = (P_H_given_P * P_P) / P_H    # 0.8089
```

> A student with attendance > 80% has an **80.89% probability of passing** — an uplift of **+11.56 pp** over the base rate.

---

## 🏆 Key Findings

| Rank | Factor | Pass Rate | Uplift |
|---|---|---|---|
| 🥇 1 | High Attendance (> 80%) | **80.89%** | +11.56 pp |
| 🥈 2 | Group Discussion Participation | **74.41%** | +9.55 pp |
| 🥉 3 | High Study Hours (> 10 hrs/week) | Venn overlap | 31.11% of batch |

> **Overall batch pass rate: 69.33%** — nearly 20 points above the theoretical 50%, showing that this cohort's habits and engagement genuinely drive results.

---

## 📁 Project Structure

```
Expectation_Decider/
│
├── 📓 Expectation_Decider.ipynb   ← Main Jupyter Notebook
├── 📊 student_dataset.xlsx        ← Dataset (450 students)
└── 📄 README.md                   ← You are here
```

---

## ▶️ How to Run

**1. Clone the repository**
```bash
git clone https://github.com/shrutiii87/Expectation_Decider.git
cd Expectation_Decider
```

**2. Install dependencies**
```bash
pip install numpy pandas scipy matplotlib matplotlib-venn openpyxl
```

**3. Open the notebook**
```bash
jupyter notebook Expectation_Decider.ipynb
```

**4. Run all cells**
```
Kernel → Restart & Run All
```

---

<div align="center">

**Made with 💜 by Shruti**

*AI · Machine Learning · Data Science*

![GitHub](https://img.shields.io/badge/GitHub-shrutiii87-181717?style=flat-square&logo=github)

</div>
