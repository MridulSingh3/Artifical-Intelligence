# 🐼 Pandas Interview Questions & Practice

A structured collection of **Pandas interview questions and practice problems** for Python/Data Analyst, Data Science, and Software Engineering interviews.

The questions are arranged from **beginner to intermediate level**, with practical examples and commonly used Pandas operations.

---

## 📌 Table of Contents

* [About](#-about)
* [Setup](#-setup)
* [Dataset](#-dataset)
* [Level 1 — Pandas Basics](#-level-1--pandas-basics)
* [Level 2 — Filtering & Conditions](#-level-2--filtering--conditions)
* [Level 3 — Sorting & Creating Columns](#-level-3--sorting--creating-columns)
* [Level 4 — GroupBy & Aggregation](#-level-4--groupby--aggregation)
* [Level 5 — Missing Values](#-level-5--missing-values)
* [Level 6 — Intermediate Interview Questions](#-level-6--intermediate-interview-questions)
* [Important Pandas Methods](#-important-pandas-methods)
* [Interview Preparation Checklist](#-interview-preparation-checklist)

---

# 📖 About

This repository contains frequently asked **Pandas interview questions** with Python solutions.

It focuses on:

* DataFrame creation
* Data selection
* Filtering
* Sorting
* Creating and modifying columns
* `groupby()`
* Aggregation
* Missing-value handling
* Duplicate handling
* Finding top-N records
* Interview-style data problems

---

# ⚙️ Setup

Install Pandas:

```bash
pip install pandas
```

Import Pandas:

```python
import pandas as pd
```

---

# 📊 Dataset

Most questions use the following employee dataset:

```python
import pandas as pd

data = {
    "Name": ["Rahul", "Aman", "Priya", "Neha",
             "Rohit", "Anjali", "Vikas", "Sneha"],

    "Age": [21, 23, 20, 22, 24, 21, 25, 22],

    "Department": [
        "IT", "HR", "IT", "Finance",
        "IT", "HR", "Finance", "IT"
    ],

    "Salary": [
        45000, 35000, 50000, 42000,
        60000, 38000, 55000, 48000
    ],

    "Experience": [1, 2, 1, 3, 4, 1, 5, 2],

    "City": [
        "Delhi", "Agra", "Mathura", "Delhi",
        "Agra", "Mathura", "Delhi", "Agra"
    ]
}

df = pd.DataFrame(data)
```

---

# 🟢 Level 1 — Pandas Basics

### 1. Display the first 5 rows

```python
df.head()
```

### 2. Display the last 3 rows

```python
df.tail(3)
```

### 3. Find the number of rows and columns

```python
df.shape
```

### 4. Display all column names

```python
df.columns
```

### 5. Display data types

```python
df.dtypes
```

### 6. Display statistical information

```python
df.describe()
```

### 7. Display only Name and Salary

```python
df[["Name", "Salary"]]
```

### 8. Display Name, Department and City

```python
df[["Name", "Department", "City"]]
```

### 9. Find average salary

```python
df["Salary"].mean()
```

### 10. Find maximum and minimum salary

```python
df["Salary"].max()
df["Salary"].min()
```

---

# 🟡 Level 2 — Filtering & Conditions

### 11. Employees with salary greater than 50000

```python
df[df["Salary"] > 50000]
```

### 12. Employees whose age is greater than 21

```python
df[df["Age"] > 21]
```

### 13. Employees from IT department

```python
df[df["Department"] == "IT"]
```

### 14. Employees from Agra

```python
df[df["City"] == "Agra"]
```

### 15. Salary between 40000 and 55000

```python
df[
    (df["Salary"] >= 40000) &
    (df["Salary"] <= 55000)
]
```

Or:

```python
df[df["Salary"].between(40000, 55000)]
```

### 16. Employees with more than 2 years of experience

```python
df[df["Experience"] > 2]
```

### 17. Employees from Agra AND IT

```python
df[
    (df["City"] == "Agra") &
    (df["Department"] == "IT")
]
```

### 18. Employees from Delhi OR Mathura

```python
df[
    (df["City"] == "Delhi") |
    (df["City"] == "Mathura")
]
```

> **Important:** In Pandas use `&` for AND and `|` for OR.

---

# 🔵 Level 3 — Sorting & Creating Columns

### 19. Sort employees by salary ascending

```python
df.sort_values("Salary")
```

### 20. Sort employees by salary descending

```python
df.sort_values("Salary", ascending=False)
```

### 21. Sort by Department and then Salary

```python
df.sort_values(
    ["Department", "Salary"]
)
```

### 22. Add Bonus column

Bonus = 10% of Salary.

```python
df["Bonus"] = df["Salary"] * 0.10
```

### 23. Add TotalSalary column

```python
df["TotalSalary"] = (
    df["Salary"] + df["Bonus"]
)
```

### 24. Increase everyone's salary by 5%

```python
df["Salary"] = df["Salary"] * 1.05
```

### 25. Rename Name to Employee_Name

```python
df.rename(
    columns={"Name": "Employee_Name"},
    inplace=True
)
```

---

# 🟣 Level 4 — GroupBy & Aggregation

The basic syntax is:

```python
df.groupby("column")["value"].function()
```

### 26. Average salary of each department

```python
df.groupby("Department")["Salary"].mean()
```

### 27. Maximum salary in each department

```python
df.groupby("Department")["Salary"].max()
```

### 28. Minimum salary in each department

```python
df.groupby("Department")["Salary"].min()
```

### 29. Number of employees in each department

```python
df.groupby("Department")["Name"].count()
```

Or:

```python
df["Department"].value_counts()
```

### 30. Average salary of each city

```python
df.groupby("City")["Salary"].mean()
```

### 31. Total salary paid by each department

```python
df.groupby("Department")["Salary"].sum()
```

### 32. Employee count for each city

```python
df.groupby("City")["Name"].count()
```

Or:

```python
df["City"].value_counts()
```

---

# 🟠 Level 5 — Missing Values

Example dataset:

```python
data = {
    "Name": ["Aman", "Rahul", "Priya", "Neha", "Rohit"],
    "Age": [21, None, 23, 22, None],
    "Salary": [40000, 50000, None, 45000, 60000],
    "City": ["Agra", "Delhi", None, "Mathura", "Agra"]
}

df = pd.DataFrame(data)
```

### 33. Count missing values

```python
df.isna().sum()
```

### 34. Remove rows containing missing values

```python
df.dropna()
```

### 35. Replace missing Age with average Age

```python
df["Age"] = df["Age"].fillna(
    df["Age"].mean()
)
```

### 36. Replace missing Salary with average Salary

```python
df["Salary"] = df["Salary"].fillna(
    df["Salary"].mean()
)
```

### 37. Replace missing City with Unknown

```python
df["City"] = df["City"].fillna("Unknown")
```

---

# 🔴 Level 6 — Intermediate Interview Questions

### 38. Find the second-highest salary

```python
df["Salary"].drop_duplicates().nlargest(2).iloc[-1]
```

### 39. Find the employee with the highest salary

```python
df.loc[df["Salary"].idxmax()]
```

### 40. Find the highest-paid employee in each department

```python
df.loc[
    df.groupby("Department")["Salary"].idxmax()
]
```

### 41. Departments having average salary greater than 45000

```python
avg_salary = (
    df.groupby("Department")["Salary"]
    .mean()
)

print(avg_salary[avg_salary > 45000])
```

### 42. Employees whose salary is greater than average salary

```python
df[
    df["Salary"] > df["Salary"].mean()
]
```

### 43. Department with the highest total salary

```python
total_salary = (
    df.groupby("Department")["Salary"]
    .sum()
)

print(total_salary.idxmax())
```

### 44. Find duplicate employee records

```python
df[df.duplicated()]
```

To find all duplicated records:

```python
df[df.duplicated(keep=False)]
```

### 45. Remove duplicate rows

```python
df.drop_duplicates()
```

### 46. Employee count for each Department + City combination

```python
df.groupby(
    ["Department", "City"]
).size()
```

### 47. Find top 3 highest-paid employees

```python
df.nlargest(3, "Salary")
```

Alternative:

```python
df.sort_values(
    "Salary",
    ascending=False
).head(3)
```

### 48. Employees whose experience is greater than average experience

```python
df[
    df["Experience"] >
    df["Experience"].mean()
]
```

---

# 🧠 Important Pandas Methods

| Method              | Purpose                |
| ------------------- | ---------------------- |
| `head()`            | First rows             |
| `tail()`            | Last rows              |
| `shape`             | Rows and columns       |
| `columns`           | Column names           |
| `dtypes`            | Data types             |
| `describe()`        | Statistical summary    |
| `mean()`            | Average                |
| `max()`             | Maximum                |
| `min()`             | Minimum                |
| `sum()`             | Total                  |
| `count()`           | Count                  |
| `value_counts()`    | Frequency count        |
| `sort_values()`     | Sort data              |
| `groupby()`         | Create groups          |
| `agg()`             | Multiple aggregations  |
| `isna()`            | Find missing values    |
| `fillna()`          | Fill missing values    |
| `dropna()`          | Remove missing values  |
| `duplicated()`      | Find duplicates        |
| `drop_duplicates()` | Remove duplicates      |
| `nlargest()`        | Find largest N values  |
| `nsmallest()`       | Find smallest N values |
| `idxmax()`          | Index of maximum       |
| `idxmin()`          | Index of minimum       |
| `between()`         | Range filtering        |

---

# ⭐ Most Important Interview Patterns

### Filtering

```python
df[df["Salary"] > 50000]
```

### Multiple conditions

```python
df[
    (df["Age"] > 21) &
    (df["Salary"] > 50000)
]
```

### GroupBy + Average

```python
df.groupby("Department")["Salary"].mean()
```

### GroupBy + Multiple Statistics

```python
df.groupby("Department")["Salary"].agg(
    ["mean", "max", "min", "sum", "count"]
)
```

### Highest row

```python
df.loc[df["Salary"].idxmax()]
```

### Highest row per group

```python
df.loc[
    df.groupby("Department")["Salary"].idxmax()
]
```

### Top N

```python
df.nlargest(3, "Salary")
```

### Compare with average

```python
df[
    df["Salary"] > df["Salary"].mean()
]
```

### Missing values

```python
df.isna().sum()
```

### Fill missing values

```python
df["Salary"] = df["Salary"].fillna(
    df["Salary"].mean()
)
```

### Duplicate records

```python
df[df.duplicated()]
```

### Multiple-column grouping

```python
df.groupby(
    ["Department", "City"]
).size()
```

---

# 🎯 Interview Preparation Checklist

Before an interview, make sure you can solve these without looking at notes:

* [ ] Create a DataFrame
* [ ] Select rows and columns
* [ ] Filter using conditions
* [ ] Use `&` and `|`
* [ ] Sort data
* [ ] Create calculated columns
* [ ] Rename columns
* [ ] Use `groupby()`
* [ ] Use `mean()`, `max()`, `min()`, `sum()`, `count()`
* [ ] Use `agg()`
* [ ] Handle missing values
* [ ] Find and remove duplicates
* [ ] Find top-N records
* [ ] Find second-highest values
* [ ] Use `idxmax()` / `idxmin()`
* [ ] Perform multiple-column grouping
* [ ] Compare rows against an aggregate value

---

# 🚀 Recommended Practice Order

```text
Level 1
   ↓
Basics
   ↓
Level 2
   ↓
Filtering & Conditions
   ↓
Level 3
   ↓
Sorting & Calculated Columns
   ↓
Level 4
   ↓
GroupBy & Aggregation
   ↓
Level 5
   ↓
Missing Values
   ↓
Level 6
   ↓
Intermediate Interview Problems
```

---

## 📚 Goal

The goal of this repository is to build strong practical knowledge of Pandas through **interview-oriented problems rather than memorizing syntax**.

> **Practice every question yourself before checking the solution.**
