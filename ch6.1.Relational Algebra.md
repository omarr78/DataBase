
## 🔹 What is Relational Algebra?

Relational Algebra is a **set of operations** used to **query data** in a relational database.

* Every operation **takes relations (tables)** as input and **produces a new relation** as output.

---

## ✅ Types of Relational Algebra Operations

### 1. **Unary Operations (work on one table only):**

| Operation | Symbol | Description                                                 |
| --------- | ------ | ----------------------------------------------------------- |
| SELECT    | σ      | Chooses rows (tuples) based on condition — "horizontal cut" |
| PROJECT   | π      | Chooses columns (attributes) — "vertical cut"               |
| RENAME    | ρ      | Renames table or attributes                                 |

### 2. **Set Operations:**

* UNION, INTERSECTION, DIFFERENCE (MINUS), CARTESIAN PRODUCT (×)

### 3. **Binary Operations:**

* JOIN (many types), DIVISION

---

## 🔸 SELECT Operation (σ)

### 🔍 Purpose:

It **filters rows** based on a condition.

### 📌 Example:

> **Get employees from department 4**

```plaintext
σ Dno = 4 (EMPLOYEE)
```

> **Get employees who earn over 30,000**

```plaintext
σ Salary > 30000 (EMPLOYEE)
```

> **Get employees from dept 4 AND salary > 30,000 OR from dept 9 AND salary < 20,000**

```plaintext
σ (Dno = 4 AND Salary > 30000) OR (Dno = 9 AND Salary < 20000) (EMPLOYEE)
```

---

## 🔸 PROJECT Operation (π)

### 🔍 Purpose:

It **filters columns** — selects only specific attributes.

### 📌 Example:

> **Get each employee's first name, last name, and salary**

```plaintext
π Fname, Lname, Salary (EMPLOYEE)
```

> **Get SSN, Salary, Address**

```plaintext
π SSN, Salary, Address (EMPLOYEE)
```

🚫 **PROJECT removes duplicates automatically.**

---

## 🔄 COMBINING SELECT + PROJECT

We use **SELECT first, then PROJECT**.

### Example:

> **List SSN, Fname, and Salary of employees in department 5**

```plaintext
π SSN, Fname, Salary (σ Dno = 5 (EMPLOYEE))
```

---

### ❓ Why SELECT first?

* SELECT **reduces the number of rows** → less data to work with.
* Then PROJECT **picks needed columns** from those filtered rows.
* 📉 This **improves performance** and ensures that the projection applies only to the relevant data.

* ⚠️ **Avoiding Loss of Important Rows**

If you apply **PROJECT first**, you might lose **columns needed in the selection condition**.

### 📌 Example:

Let's say:

```plaintext
π Fname, Salary (EMPLOYEE)
```

Then try to do:

```plaintext
σ Dno = 5 (...)
```

❌ You **can't** apply `Dno = 5` anymore, because **Dno is gone** after projection!

So:

> **PROJECT removes columns — if SELECT needs those columns, the condition fails.**

---

