# NumPy Interview Questions & Practice

A structured collection of **NumPy interview questions, coding problems, concepts, and practice exercises** for Python developers, Data Analysts, Data Scientists, and beginners preparing for technical interviews.

---

## 📌 About NumPy

**NumPy (Numerical Python)** is a Python library used for numerical computing.

It provides:

* Multidimensional arrays
* Fast mathematical operations
* Array indexing and slicing
* Broadcasting
* Linear algebra operations
* Statistical functions
* Random number generation
* Vectorized computation

---

# 📚 NumPy Interview Preparation

## 1. NumPy Basics

### Q1. What is NumPy?

NumPy is a Python library mainly used for numerical and scientific computing. Its core feature is the `ndarray`, which allows efficient operations on multidimensional data.

### Q2. How do you import NumPy?

```python
import numpy as np
```

### Q3. How do you create a NumPy array?

```python
import numpy as np

arr = np.array([1, 2, 3, 4, 5])

print(arr)
```

### Q4. What is the difference between a Python list and a NumPy array?

| Python List                      | NumPy Array                     |
| -------------------------------- | ------------------------------- |
| Can contain different data types | Usually contains one data type  |
| Slower for numerical operations  | Faster for numerical operations |
| Less memory efficient            | More memory efficient           |
| Limited mathematical operations  | Supports vectorized operations  |

---

# 2. Array Properties

Given:

```python
arr = np.array([
    [10, 20, 30],
    [40, 50, 60],
    [70, 80, 90]
])
```

### Q5. Find the number of dimensions

```python
print(arr.ndim)
```

Output:

```text
2
```

### Q6. Find the shape

```python
print(arr.shape)
```

Output:

```text
(3, 3)
```

### Q7. Find the total number of elements

```python
print(arr.size)
```

Output:

```text
9
```

### Q8. Find the data type

```python
print(arr.dtype)
```

---

# 3. Array Creation

### Q9. Create an array containing numbers from 1 to 10

```python
arr = np.arange(1, 11)
print(arr)
```

### Q10. Create an array of zeros

```python
arr = np.zeros(5)
print(arr)
```

### Q11. Create an array of ones

```python
arr = np.ones(5)
print(arr)
```

### Q12. Create an identity matrix

```python
arr = np.eye(3)
print(arr)
```

---

# 4. Indexing

Given:

```python
arr = np.array([
    [10, 20, 30],
    [40, 50, 60],
    [70, 80, 90]
])
```

### Q13. Extract `50`

```python
print(arr[1, 1])
```

### Q14. Extract the first row

```python
print(arr[0, :])
```

### Q15. Extract the last row

```python
print(arr[-1, :])
```

### Q16. Extract the first column

```python
print(arr[:, 0])
```

### Q17. Extract the last column

```python
print(arr[:, -1])
```

### Important Rule

For a 2D array:

```python
arr[row, column]
```

Examples:

```python
arr[1, 1]    # specific element
arr[0, :]    # first row
arr[:, 0]    # first column
arr[-1, :]   # last row
arr[:, -1]   # last column
```

---

# 5. Slicing

### Q18. Extract the first three elements

```python
arr = np.array([10, 20, 30, 40, 50])

print(arr[:3])
```

### Q19. Extract the last three elements

```python
print(arr[-3:])
```

### Q20. Extract every second element

```python
print(arr[::2])
```

### Q21. Reverse an array

```python
print(arr[::-1])
```

---

# 6. Mathematical Operations

### Q22. Find the maximum value

```python
arr = np.array([10, 30, 20, 50, 40])

print(np.max(arr))
```

### Q23. Find the minimum value

```python
print(np.min(arr))
```

### Q24. Find the sum

```python
print(np.sum(arr))
```

### Q25. Find the average

```python
print(np.mean(arr))
```

### Q26. Find the standard deviation

```python
print(np.std(arr))
```

---

# 7. Conditional Filtering

### Q27. Extract all numbers greater than 30

```python
arr = np.array([10, 20, 30, 40, 50])

result = arr[arr > 30]

print(result)
```

### Q28. Extract even numbers

```python
arr = np.arange(1, 11)

result = arr[arr % 2 == 0]

print(result)
```

### Q29. Replace negative numbers with 0

```python
arr = np.array([10, -5, 20, -8, 30])

arr[arr < 0] = 0

print(arr)
```

---

# 8. 2D Array Operations

Given:

```python
arr = np.array([
    [10, 20, 30],
    [40, 50, 60],
    [70, 80, 90]
])
```

### Q30. Calculate row-wise sum

```python
print(np.sum(arr, axis=1))
```

Output:

```text
[ 60 150 240]
```

### Q31. Calculate column-wise sum

```python
print(np.sum(arr, axis=0))
```

Output:

```text
[120 150 180]
```

### Remember

```text
axis=0 → operate vertically → result for each column

axis=1 → operate horizontally → result for each row
```

---

# 9. Reshaping

### Q32. Convert a 1D array into a 3 × 4 matrix

```python
arr = np.arange(1, 13)

result = arr.reshape(3, 4)

print(result)
```

### Q33. Convert a 2D array into 1D

```python
arr = np.array([
    [1, 2],
    [3, 4]
])

print(arr.flatten())
```

---

# 10. Sorting and Unique Values

### Q34. Sort an array

```python
arr = np.array([50, 10, 40, 20, 30])

print(np.sort(arr))
```

### Q35. Find unique values

```python
arr = np.array([1, 2, 2, 3, 3, 3, 4])

print(np.unique(arr))
```

---

# 11. Finding Index

### Q36. Find the index of the maximum element

```python
arr = np.array([10, 50, 20, 80, 30])

print(np.argmax(arr))
```

### Q37. Find the index of the minimum element

```python
print(np.argmin(arr))
```

---

# 12. Matrix Operations

Given:

```python
A = np.array([
    [1, 2],
    [3, 4]
])

B = np.array([
    [5, 6],
    [7, 8]
])
```

### Q38. Matrix addition

```python
print(A + B)
```

### Q39. Matrix subtraction

```python
print(A - B)
```

### Q40. Element-wise multiplication

```python
print(A * B)
```

### Q41. Matrix multiplication

```python
print(A @ B)
```

### Important

Do not confuse:

```python
A * B
```

with:

```python
A @ B
```

`*` performs **element-wise multiplication**.

`@` performs **matrix multiplication**.

---

# 13. Broadcasting

### Q42. What is broadcasting?

Broadcasting allows NumPy to perform operations between arrays with compatible shapes without explicitly creating copies of the smaller array.

Example:

```python
arr = np.array([1, 2, 3])

print(arr + 10)
```

Output:

```text
[11 12 13]
```

---

# 14. Vectorization

### Q43. What is vectorization?

Vectorization means performing operations on entire arrays instead of using explicit Python loops.

Without vectorization:

```python
result = []

for x in arr:
    result.append(x * 2)
```

Using NumPy:

```python
result = arr * 2
```

NumPy's vectorized approach is generally faster and more concise for numerical operations.

---

# 💻 Coding Interview Questions

Try solving these **without looking at solutions**.

## Beginner

### Problem 1

Create an array from 1 to 50 and extract all even numbers.

### Problem 2

Find the maximum and minimum values of an array.

### Problem 3

Count how many values are greater than 50.

### Problem 4

Replace all negative numbers with 0.

### Problem 5

Reverse an array without using a loop.

---

## Intermediate

### Problem 6

Given:

```python
arr = np.array([
    [10, 20, 30],
    [40, 50, 60],
    [70, 80, 90]
])
```

Find:

* Main diagonal
* First row
* Last row
* First column
* Last column

### Problem 7

Find the sum of every row and every column.

### Problem 8

Find the row containing the maximum sum.

### Problem 9

Find all values between 20 and 60.

### Problem 10

Remove duplicate values from an array.

---

# 🔥 Interview-Level Problems

### Problem 11 — Student Marks

```python
marks = np.array([
    [80, 75, 90],
    [60, 55, 70],
    [95, 88, 92],
    [40, 50, 45]
])
```

Find:

1. Total marks of every student
2. Average marks of every student
3. Highest total
4. Student with highest average
5. Students with average > 75

---

### Problem 12 — Matrix Diagonal

Given:

```python
arr = np.array([
    [1, 2, 3],
    [4, 5, 6],
    [7, 8, 9]
])
```

Find:

```text
Main diagonal
Secondary diagonal
```

Expected:

```text
Main:      [1 5 9]
Secondary: [3 5 7]
```

---

### Problem 13 — Common Elements

Given:

```python
a = np.array([1, 2, 3, 4, 5])
b = np.array([3, 4, 5, 6, 7])
```

Find the common elements.

Expected:

```text
[3 4 5]
```

---

### Problem 14 — Second Largest

Find the second-largest unique value in:

```python
arr = np.array([10, 50, 20, 50, 30, 40])
```

Expected:

```text
40
```

---

### Problem 15 — Normalize an Array

Given:

```python
arr = np.array([10, 20, 30, 40, 50])
```

Normalize the values using:

```text
(x - min) / (max - min)
```

Expected range:

```text
0 to 1
```

---

# 🎯 Important NumPy Topics for Interviews

Before an interview, make sure you understand:

* [ ] `np.array()`
* [ ] `np.arange()`
* [ ] `np.linspace()`
* [ ] `np.zeros()`
* [ ] `np.ones()`
* [ ] `np.eye()`
* [ ] `ndim`
* [ ] `shape`
* [ ] `size`
* [ ] `dtype`
* [ ] Indexing
* [ ] Slicing
* [ ] Boolean indexing
* [ ] `reshape()`
* [ ] `flatten()`
* [ ] `transpose()`
* [ ] `sum()`
* [ ] `mean()`
* [ ] `max()`
* [ ] `min()`
* [ ] `std()`
* [ ] `argmax()`
* [ ] `argmin()`
* [ ] `sort()`
* [ ] `unique()`
* [ ] `concatenate()`
* [ ] `axis`
* [ ] Broadcasting
* [ ] Vectorization
* [ ] Matrix multiplication
* [ ] Difference between `*` and `@`

---

# 🚀 Practice Strategy

Don't memorize the syntax first.

For every problem, follow this process:

```text
1. Understand the array
        ↓
2. Identify its shape
        ↓
3. Decide row / column / element
        ↓
4. Choose indexing / slicing / operation
        ↓
5. Write NumPy code
        ↓
6. Check the output
```

## Recommended Order

```text
Arrays
  ↓
Indexing
  ↓
Slicing
  ↓
Boolean Filtering
  ↓
Aggregation
  ↓
2D Arrays
  ↓
axis
  ↓
Reshape
  ↓
Broadcasting
  ↓
Vectorization
  ↓
Matrix Operations
```

---

## 🏆 Goal

By completing these questions, you should be able to solve common NumPy interview problems without relying heavily on Python loops.

**Practice rule:** For each coding problem, first try to solve it yourself. Then compare your solution with the NumPy/vectorized approach.
