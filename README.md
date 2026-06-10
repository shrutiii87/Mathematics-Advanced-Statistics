# 📊 Expectation Decider: Probability Analysis of Student Performance

### Skill Education — Shaping Skills for Scaling Higher...!!!

A complete **Theory + Practical Probability Project** analyzing a real-world student dataset of **450 records**. The project covers fundamental probability concepts including events, empirical vs theoretical probability, random variables, binomial distribution, Venn diagrams, contingency tables, conditional probability, independence, mutual exclusivity, and Bayes' Theorem.

The entire analysis is implemented using **Python (Jupyter Notebook)** and documented through a comprehensive **Insights Report** containing calculations, probability interpretations, and business-style conclusions.

---

# 📋 Project Details

| Field      | Details                                                          |
| ---------- | ---------------------------------------------------------------- |
| Title      | Expectation Decider: Probability Analysis of Student Performance |
| Duration   | 4 Hours                                                          |
| Type       | Theory + Practical                                               |
| Tools Used | Python · Excel                                                   |
| Libraries  | Pandas · NumPy · Matplotlib · SciPy                              |

---

# 🎯 Objective

You are a data analyst working for an educational research organization.

Your task is to analyze student performance data and apply probability concepts to understand factors affecting exam success. Through this project, you will calculate event probabilities, analyze relationships between study habits and outcomes, explore conditional probability, and use Bayes' Theorem to identify the strongest predictors of passing exams.

---

# 🗂️ Project Files

| File                                 | Description                                                           |
| ------------------------------------ | --------------------------------------------------------------------- |
| 📓 Expectation_Decider.ipynb         | Jupyter Notebook containing all probability calculations and analysis |
| 📊 student_dataset.xlsx              | Dataset containing 450 student records                                |
| 📄 Expectation_Decider_Insights.docx | Detailed insights report and interpretations                          |
| 📘 README.md                         | Project documentation                                                 |

---

# 🧩 Dataset Structure

**AI-Generated Dataset · 450 Records**

| Column Name           | Data Type   | Description                   |
| --------------------- | ----------- | ----------------------------- |
| Student_ID            | Categorical | Unique Student Identifier     |
| Attendance_Percentage | Numerical   | Student attendance percentage |
| Study_Hours           | Numerical   | Weekly study hours            |
| Group_Discussion      | Categorical | Yes / No                      |
| Final_Exam_Pass       | Categorical | Pass / Fail                   |
| Previous_Grade        | Numerical   | Previous academic performance |
| Participation_Score   | Numerical   | Classroom participation score |

---

🛠️ Tools used 

![Python](https://img.shields.io/badge/Python-3.x-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-F37626?style=for-the-badge&logo=jupyter&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-150458?style=for-the-badge&logo=pandas&logoColor=white)
![NumPy](https://img.shields.io/badge/NumPy-013243?style=for-the-badge&logo=numpy&logoColor=white)
![SciPy](https://img.shields.io/badge/SciPy-8CAAE6?style=for-the-badge&logo=scipy&logoColor=white)
![Matplotlib](https://img.shields.io/badge/Matplotlib-11557C?style=for-the-badge&logo=matplotlib&logoColor=white)

---

# 📗 Probability Topics Covered

## Q1 — Basic Probability Events

Calculate probabilities of:

* Student Passing Exam
* Student Participating in Group Discussion
* Student Having Attendance > 75%

### Results

| Event            | Probability |
| ---------------- | ----------- |
| Pass Exam        | 0.6933      |
| Group Discussion | 0.4689      |
| Attendance > 75% | 0.5022      |

📌 **Insight:** Nearly 69% of students pass the exam. Attendance remains moderate while classroom participation is relatively low.

---

## Q2 — Empirical vs Theoretical Probability

### Empirical Probability

Calculated using actual dataset observations.

[
P(Pass)=\frac{312}{450}=0.6933
]

### Theoretical Probability

Assuming equal likelihood:

[
P(Pass)=\frac{1}{2}=0.5000
]

| Type        | Probability |
| ----------- | ----------- |
| Empirical   | 0.6933      |
| Theoretical | 0.5000      |

📌 **Insight:** Real-world pass rates exceed theoretical expectations due to factors such as attendance, study effort, and participation.

---

## Q3 — Random Variable & Binomial Distribution

### Random Variable

X = Number of students passing among 3 randomly selected students.

Parameters:

* n = 3
* p = 0.6933
* q = 0.3067

### Probability Distribution

| X | P(X)   |
| - | ------ |
| 0 | 0.0288 |
| 1 | 0.1956 |
| 2 | 0.4423 |
| 3 | 0.3333 |

### Expected Value

[
E(X)=np=2.08
]

### Variance

[
Var(X)=npq=0.6379
]

📌 **Insight:** The most likely outcome is exactly 2 students passing.

---

## Q4 — Venn Diagram Analysis

### Set Definitions

* A = Students with Study Hours > 10
* B = Students with Attendance > 80%

### Region Counts

| Region  | Students |
| ------- | -------- |
| Only A  | 200      |
| A ∩ B   | 140      |
| Only B  | 40       |
| Neither | 70       |

### Probability Calculations

| Probability | Value  |
| ----------- | ------ |
| P(A)        | 0.7556 |
| P(B)        | 0.4000 |
| P(A ∩ B)    | 0.3111 |
| P(A ∪ B)    | 0.8444 |

📌 **Insight:** Students with both strong attendance and study habits form the highest-performing group.

---

## Q5 — Contingency Table & Conditional Probability

### Group Discussion vs Exam Outcome

| Group Discussion | Fail | Pass |
| ---------------- | ---- | ---- |
| No               | 84   | 155  |
| Yes              | 54   | 157  |

### Probabilities

#### Joint Probability

[
P(Discussion \cap Pass)=0.3489
]

#### Marginal Probability

[
P(Pass)=0.6933
]

#### Conditional Probability

[
P(Pass|Discussion)=0.7441
]

📌 **Insight:** Students participating in group discussions show significantly higher pass rates.

---

## Q6 — Independence & Mutual Exclusivity

### Independence Test

[
P(Pass|Discussion)=0.7441
]

[
P(Pass)=0.6933
]

Since both values differ:

✅ Events are **Dependent**

### Mutual Exclusivity Test

157 students both participated and passed.

✅ Events are **Not Mutually Exclusive**

📌 **Insight:** Participation positively influences exam success.

---

## Q7 — Bayes' Theorem Application

### Given

* P(H | Pass) = 0.70
* P(H | Fail) = 0.40
* P(H) = 0.60

Where:

H = High Attendance (>80%)

### Bayes Formula

[
P(Pass|H)=\frac{P(H|Pass)\times P(Pass)}{P(H)}
]

### Result

[
P(Pass|H)=0.8089
]

### Interpretation

| Probability                    | Value  |
| ------------------------------ | ------ |
| Overall Pass Rate              | 69.33% |
| Pass Rate with High Attendance | 80.89% |

📌 **Insight:** High attendance increases the probability of passing by more than 11 percentage points.

---

# 📊 Key Findings

✔️ 69.33% of students passed the final examination

✔️ Group discussion participants achieved a 74.41% pass rate

✔️ Students with attendance above 80% had an 80.89% probability of passing

✔️ The probability of all three randomly selected students failing is only 2.88%

✔️ Study hours and attendance together form the strongest performance combination

✔️ Group discussion and exam success are statistically dependent events

✔️ High attendance is the strongest predictor of passing in this dataset

---

# 🛠️ Tools & Technologies

| Tool             | Usage                                          |
| ---------------- | ---------------------------------------------- |
| Python           | Core programming language                      |
| Pandas           | Data manipulation and probability calculations |
| NumPy            | Numerical computations                         |
| Matplotlib       | Charts and visualizations                      |
| SciPy            | Binomial probability calculations              |
| Jupyter Notebook | Interactive development environment            |
| Microsoft Excel  | Dataset storage and verification               |

---

# 🚀 How to Run

## Python

1. Clone or download the repository.
2. Install required libraries:

```bash
pip install pandas numpy matplotlib scipy openpyxl
```

3. Place the dataset file in the project folder.
4. Open `Expectation_Decider.ipynb`.
5. Run all notebook cells sequentially.

---

# 🌟 Future Enhancements

* Add Probability Tree Diagrams
* Implement Markov Chain Student Progression Analysis
* Build Interactive Streamlit Dashboard
* Perform Hypothesis Testing on Attendance Impact
* Add Monte Carlo Simulation for Exam Predictions
* Expand dataset to 1000+ students

---

# ✅ Submission Checklist

* Probability calculations completed in Python
* Binomial Distribution Analysis
* Venn Diagram Probability Analysis
* Contingency Table Analysis
* Conditional Probability Calculations
* Independence & Mutual Exclusivity Testing
* Bayes' Theorem Application
* Insights Report Included
* Dataset Included
* Complete README Documentation

---

## 👩‍💻 Shruti Bhawsar

📍 Ahmedabad, Gujarat

⭐ If you found this project helpful, give it a star and feel free to fork!

### 📊 Data-Driven Decisions · Probability-Powered Insights · Smarter Predictions
