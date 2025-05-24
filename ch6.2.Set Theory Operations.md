
## 📚 **Set Theory Operations in Relational Algebra**

These operations come from **mathematics** and are applied to **relations (tables)** in databases.
But there’s one important **requirement**:

> ✅ The two relations must be **union-compatible**:
>
> * Same number of columns (attributes)
> * Corresponding columns must have the **same data type**

---

### 1️⃣ UNION Operation `(R ∪ S)`

> Combines **all unique tuples** from both relations.

🧠 Think of it like:
**“Give me everything from R and S, but no duplicates.”**

#### 📌 Example:

Let’s say:

```plaintext
R:          S:
ID Name     ID Name
1  John     3  Sarah
2  Alice    2  Alice
```

Then:

```plaintext
R ∪ S = 
ID Name
1  John
2  Alice
3  Sarah
```

🎯 **Duplicates are removed** automatically.

---

### 2️⃣ INTERSECTION Operation `(R ∩ S)`

> Returns only the tuples that exist in **both** relations.

🧠 Think of it like:
**“What’s common between R and S?”**

#### 📌 Example:

```plaintext
R:          S:
ID Name     ID Name
1  John     3  Sarah
2  Alice    2  Alice
```

Then:

```plaintext
R ∩ S =
ID Name
2  Alice
```

Only `Alice` appears in both.

---

### 3️⃣ DIFFERENCE Operation `(R - S)`

> Returns the tuples that exist in **R but not in S**.

🧠 Think of it like:
**“Give me everything in R that is not in S.”**

#### 📌 Example:

```plaintext
R:          S:
ID Name     ID Name
1  John     3  Sarah
2  Alice    2  Alice
```

Then:

```plaintext
R - S =
ID Name
1  John
```

---

### 4️⃣ CARTESIAN PRODUCT (Cross Product) `R × S`

> Combines every tuple in **R** with every tuple in **S**.

🧠 Think of it like:
**“Match everything in R with everything in S.”**

This operation is powerful, but can produce **a lot of data**.
The result table has **rows = |R| × |S|** and **columns = all columns from both R and S.**

#### 📌 Example:

```plaintext
R:          S:
ID Name     Dept
1  John     HR
2  Alice    IT
```

Then:

```plaintext
R × S =
ID Name  Dept
1  John   HR
1  John   IT
2  Alice  HR
2  Alice  IT
```

---

### 📌 Real Use Case:

**Find employees who have dependents with names like their father.**

* Suppose you have two relations:

```plaintext
EMPLOYEE(Ssn, Fname, Lname, ...)
DEPENDENT(Essn, Dependent_name, ...)
```

We do:

```plaintext
EMPLOYEE × DEPENDENT
```

Then:

```sql
SELECT * 
WHERE Ssn = Essn 
AND Dependent_name = Fname
```

🧠 This finds pairs where the **dependent has the same name as the employee** (maybe child named after parent).

---
