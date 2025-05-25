### 🔵 **Divide Operator (÷) in Relational Algebra**

is a special relational algebra operator used when we want to find **"for all"** relationships.
It’s mainly used to **answer queries that include “all” or “every”** in their condition.

---

### ✅ **General Use of Divide Operator:**

If:

* **R(A, B)** = A relation with **many-to-many** data (e.g., Employees and Projects).
* **S(B)** = A relation with the subset of **values we want "all of"**.

Then:

```
R ÷ S
```

Gives us:

> All **A-values** from R that are associated with **every B-value** in S.

---

## 📘 Example 1:

### 🧩 **Find employees who worked on *all* projects**

Let:

* **R(Essn, Pno)** ← relation `Works_On`
  (shows which employees worked on which projects)
* **S(Pno)** ← relation `Project`
  (shows all project numbers)

Then:

```
T ← Works_On ÷ Project
```

This returns **Essn** (employee IDs) of those who worked on **all projects**.

---

## 📘 Example 2:

### 🧩 **Retrieve employees who work on *all the projects* that 'John Smith' works on**

Let:

* `R(Essn, Pno)` ← `Works_On`
* `S(Pno)` ← project numbers worked on by 'John Smith'

Then:

```
T ← Works_On ÷ (π Pno (σ Fname='John' AND Lname='Smith' (Employee ⨝ Works_On)))
```

Explanation:

1. First get all projects that 'John Smith' works on.
2. Use divide to find employees who are working on **all of those**.

---

## ✅ **What are Aggregate Functions?**

Aggregate functions perform **calculations on a set of values** and return a **single value** as the result.

---

### 🎯 Common Aggregate Functions:

| Function  | Description             |
| --------- | ----------------------- |
| `COUNT()` | Counts number of rows   |
| `SUM()`   | Adds up values          |
| `AVG()`   | Calculates average      |
| `MIN()`   | Finds the minimum value |
| `MAX()`   | Finds the maximum value |

---

## ✅ **What is `GROUP BY`?**

The `GROUP BY` clause in SQL is used **with aggregate functions** to **group the result set by one or more columns**.

* It partitions data into groups.
* Then applies the aggregate function **within each group**.

---

## 📘 **Example Table: EMPLOYEE**

| Dno | Name    | Salary |
| --- | ------- | ------ |
| 1   | Alice   | 5000   |
| 1   | Bob     | 5500   |
| 2   | Charlie | 7000   |
| 2   | Diana   | 6800   |
| 3   | Edward  | 6200   |

---

## 🧮 **1. Total Salary for Each Department**

### 🔹 Output:

| Dno | TotalSalary |
| --- | ----------- |
| 1   | 10500       |
| 2   | 13800       |
| 3   | 6200        |

---

## 🧮 **2. Count of Employees per Department**


### 🔹 Output:

| Dno | NumEmployees |
| --- | ------------ |
| 1   | 2            |
| 2   | 2            |
| 3   | 1            |

---

## 🧮 **3. Average Salary in Each Department**

### 🔹 Output:

| Dno | AvgSalary |
| --- | --------- |
| 1   | 5250      |
| 2   | 6900      |
| 3   | 6200      |

---

## 🔸 In Relational Algebra:

```
γ Dno, SUM(Salary) (EMPLOYEE)
```

* `γ` (gamma) is the grouping operator.
* `Dno` is the **grouping attribute**.
* `SUM(Salary)` is the **aggregate function** applied within each group.

Other examples:

```
γ Dno, COUNT(*) (EMPLOYEE)
γ Dno, AVG(Salary) (EMPLOYEE)
```

---

