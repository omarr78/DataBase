## 🔐 Relational Integrity Constraints

**Constraints** are rules that ensure the data in the database is **accurate**, **correct**, and **valid**.

These constraints must always hold true in the database.

---

### ✅ Types of Constraints

There are **3 main types** of integrity constraints in the relational model (explicit):

| Constraint Type                         | Purpose                                                 |
| --------------------------------------- | ------------------------------------------------------- |
| 1. **Key Constraint**                   | Uniquely identifies each row (tuple) in a table         |
| 2. **Entity Integrity Constraint**      | Ensures **primary keys are not null**                   |
| 3. **Referential Integrity Constraint** | Ensures **relationships between tables** are consistent |

📝 Plus an **implicit** constraint:

* **Domain Constraint** – Values must be from the valid type or format for each attribute.

---

## 1️⃣ Key Constraints

A **key** is used to uniquely identify each row in a table.

### 🔸 Superkey

A **superkey** is **any set of attributes** that **uniquely identifies** each tuple in a table.

> ✅ No two rows can have the same values for a superkey.

### 🔸 Key (Candidate Key)

A **key** is a **minimal superkey** — meaning it has **just enough attributes** to uniquely identify a row, and no extra.

> If you remove any attribute from a key, it will no longer be unique.

---

### 🚗 Example: CAR Table

| State | Reg#  | SerialNo | Make   | Model   | Year |
| ----- | ----- | -------- | ------ | ------- | ---- |
| CA    | 12345 | SN001    | Toyota | Corolla | 2020 |
| TX    | 56789 | SN002    | Honda  | Civic   | 2021 |

* **Superkeys**:

  * `{State, Reg#}`
  * `{SerialNo}`
  * `{SerialNo, Make}` → ✅ Still unique, but **not minimal**, so **not a key**

* **Keys**:

  * `{State, Reg#}` → Composite key (two attributes)
  * `{SerialNo}` → Simple key (one attribute)

> Every **key** is a **superkey**, but not every superkey is a key.

---

### 🔑 Primary Key

If a table has **multiple candidate keys**, we choose **one** to be the **primary key**.

* Primary key values are **underlined**.

#### Example:

CAR(**SerialNo**, State, Reg#, Make, Model, Year)

We choose `SerialNo` as the **primary key**, because:

* It's short (only one column)
* It's unique
* It's simple and numeric

> General Rule: Choose the **smallest** and most **stable** candidate key.
>
> Not always applicable — choice is sometimes subjective `على حسب الظروف`

---

Here’s a clear and simple explanation of **Entity Integrity**, **Referential Integrity**, and **Semantic Integrity Constraints**, along with helpful examples and structure:

---

## 🧱 **Entity Integrity Constraint**

**What is it?**
This rule ensures that **every row (tuple) in a table can be uniquely identified**.

### 📌 Rule:

> **Primary Key values can never be NULL**.

* Every table must have a **primary key**.
* That key **must always have a value** (cannot be blank or unknown).
* If the key has **more than one column**, **none** of those columns can be NULL.

### ✅ Example:

**STUDENT** table:

| StudentID (PK) | Name    | Age                                       |
| -------------- | ------- | ----------------------------------------- |
| 1001           | Alice   | 21                                        |
| 1002           | Bob     | 22                                        |
| **NULL**       | Charlie | 23  ❌ Invalid (violates entity integrity) |

> `StudentID` is the **primary key**, so it cannot be NULL.

---

## 🔗 **Referential Integrity Constraint**

**What is it?**
This rule ensures that **foreign key values match primary key values in another table**.

### 📌 Rule:

> A **foreign key** must either:
>
> 1. Match a **primary key** in the referenced table
> 2. Or be **NULL** (if allowed)
>    
• In case (2), the FK in R1 should not be a part of its 
its own primary key.

### ✅ Example:

We have two tables:

**DEPARTMENT** (Referenced table)

| DeptID (PK) | DeptName |
| ----------- | -------- |
| D01         | HR       |
| D02         | IT       |

**EMPLOYEE** (Referencing table)

| EmpID | Name    | DeptID (FK)                                |
| ----- | ------- | ------------------------------------------ |
| 1     | Alice   | D01         ✅                              |
| 2     | Bob     | D02         ✅                              |
| 3     | Charlie | D03         ❌ Invalid – D03 does not exist |
| 4     | Diana   | NULL        ✅ (If NULLs allowed)           |

> `DeptID` in the EMPLOYEE table is a **foreign key** referencing `DeptID` in the DEPARTMENT table.

---

## 🧠 **Semantic Integrity Constraints**

**What is it?**
These are **rules based on real-world logic or business rules**, not directly enforced by the database model itself.

### 📌 Example:

> “An employee can work **a maximum of 56 hours per week** across all projects.”

* This rule **cannot be enforced** by default relational constraints.
* We need additional logic like:

  * **Triggers**
  * **Assertions**
  * Or enforced in the **application layer**

---
