## 📘 What Is the Relational Data Model?

The **Relational Data Model** is the most common way to represent data in a database. It is based on the concept of a **relation**, which is just a **table**.

You can think of a **relation = table** in a database.

---

## 📊 What Is a Relation?

A **relation** is a table with:

* **Rows (records)** → Each row is called a **tuple**
* **Columns (fields)** → Each column is called an **attribute**
* A **table name** → The name of the relation

### 💡 Example:

Let’s take a **STUDENT** table (relation):

| StudentID | Name  | Age | Major            |
| --------- | ----- | --- | ---------------- |
| 101       | Alice | 20  | Computer Science |
| 102       | Bob   | 22  | Business         |
| 103       | Carol | 21  | Engineering      |

* This table is a **relation**
* Each row (Alice, Bob, Carol) is a **tuple**
* Each column (StudentID, Name, Age, Major) is an **attribute**

---

## 🔢 Why is it Called a "Mathematical" Concept?

* The relational model comes from **set theory** in math.
* A table is like a **set of rows**.
* Each row in the set is unique (no duplicates).
* Order of rows or columns doesn’t matter in pure math, but in practice, databases show them in order for readability.

---

## ✅ Relational Database Constraints

**Constraints** are rules that make sure the data in the table is **correct** and **reliable**. Here are the most common types:

---

### 1. **Domain Constraint**

* Each column has a specific type of data (called a **domain**).
* Example: The `Age` column must contain only integers.

---

### 2. **Key Constraints**

* Each table should have a **key** that uniquely identifies each row.

#### ✅ Types of Keys:

* **Primary Key**: A column (or columns) that uniquely identifies every row.

  * Example: `StudentID` in the STUDENT table.
* **Candidate Key**: Other columns that could also serve as a unique ID.
* **Foreign Key**: A key that links to a primary key in another table (used to connect tables).

---

### 3. **Entity Integrity**

* **Primary key values cannot be NULL**.
* Every record must have a valid ID.

---

### 4. **Referential Integrity**

* If a table uses a **foreign key**, the value must match an existing value in the referenced table.

#### 💡 Example:

If there’s an `ENROLLMENT` table that uses `StudentID` from the `STUDENT` table, that `StudentID` must exist in the STUDENT table.

---

## 🧠 Summary

| Concept         | Simple Meaning                                |
| --------------- | --------------------------------------------- |
| **Relation**    | A table                                       |
| **Tuple**       | A row in the table                            |
| **Attribute**   | A column in the table                         |
| **Domain**      | Allowed type of data in a column              |
| **Primary Key** | Unique ID for each row                        |
| **Foreign Key** | A reference to a primary key in another table |
| **Constraints** | Rules to keep the data accurate               |

---

