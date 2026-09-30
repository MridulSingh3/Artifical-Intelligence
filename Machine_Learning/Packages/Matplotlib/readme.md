# 📊 Matplotlib Interview Questions

A collection of **Matplotlib interview questions** covering both **theoretical concepts and coding problems**, from beginner to interview level.

---

## 📌 Table of Contents

1. [Basic Theory Questions](#1-basic-theory-questions)
2. [Intermediate Theory Questions](#2-intermediate-theory-questions)
3. [Chart-Based Questions](#3-chart-based-questions)
4. [Basic Coding Questions](#4-basic-coding-questions)
5. [Intermediate Coding Questions](#5-intermediate-coding-questions)
6. [Advanced Coding Questions](#6-advanced-coding-questions)
7. [Rapid-Fire Questions](#7-rapid-fire-questions)
8. [Output-Based Questions](#8-output-based-questions)
9. [Important Functions](#9-important-functions)
10. [Practice Problems](#10-practice-problems)

---

# 1. Basic Theory Questions

### Q1. What is Matplotlib?

### Q2. Why is Matplotlib used in Python?

### Q3. What is `pyplot`?

### Q4. How do you import Matplotlib?

### Q5. What does `plt.show()` do?

### Q6. What is a Figure in Matplotlib?

### Q7. What is an Axes object?

### Q8. What is the difference between Figure and Axes?

### Q9. What is the difference between Matplotlib and Seaborn?

### Q10. What types of charts can be created using Matplotlib?

---

# 2. Intermediate Theory Questions

### Q11. What is the difference between `plt.plot()` and `plt.scatter()`?

### Q12. What is the difference between a bar chart and a histogram?

### Q13. When should you use a line chart?

### Q14. When should you use a bar chart?

### Q15. When should you use a scatter plot?

### Q16. When should you use a histogram?

### Q17. When should you use a pie chart?

### Q18. What are bins in a histogram?

### Q19. What does `figsize` do?

### Q20. What does `marker` do?

### Q21. What does `linestyle` do?

### Q22. What does `plt.legend()` do?

### Q23. What does `plt.grid()` do?

### Q24. What does `plt.tight_layout()` do?

### Q25. What does `plt.savefig()` do?

### Q26. What is `autopct` in a pie chart?

### Q27. What is the purpose of `plt.xticks()`?

### Q28. What is the purpose of `plt.yticks()`?

### Q29. What is the difference between `plt.figure()` and `plt.subplot()`?

### Q30. What is an annotation in Matplotlib?

---

# 3. Chart-Based Questions

### Q31. Which chart is best for showing trends over time?

### Q32. Which chart is best for comparing categories?

### Q33. Which chart is best for showing the relationship between two numerical variables?

### Q34. Which chart is used to show the distribution of numerical data?

### Q35. Which chart is commonly used to show percentage composition?

### Q36. What is the difference between a histogram and a bar chart?

### Q37. What is a grouped bar chart?

### Q38. What is a trend line?

### Q39. How can you plot multiple lines on the same graph?

### Q40. How can you display values above bars?

---

# 4. Basic Coding Questions

## Q41. Create a simple line chart.

```python
import matplotlib.pyplot as plt

x = [1, 2, 3, 4, 5]
y = [10, 20, 15, 30, 25]

plt.plot(x, y)
plt.show()
