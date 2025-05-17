
## 📦 **Populated Database State**

### ✅ What is it?

* A **relation (table)** contains **tuples (rows)** — that’s its current state.
* A **database** consists of **many relations**, so:

  > **Database state = all current data in all tables**

![data base state](https://github.com/user-attachments/assets/182c74f9-e960-4ac3-aef6-93eb3d85d961)


### 🔁 When the database changes (e.g., data is added or removed), a **new state** arises.

---

## 🔧 **Basic Operations that Change the Database**

| Operation  | What it does                       |
| ---------- | ---------------------------------- |
| **INSERT** | Adds a new row to a table          |
| **DELETE** | Removes a row from a table         |
| **MODIFY** | Changes a value in an existing row |

These are called **update operations**.

---

## 🔐 **Update Operations & Integrity Constraints**

When we perform updates, we must make sure they **do not break rules (constraints)** in the database.

### Integrity constraints include:

* **Domain constraint**: Value must match the correct data type (e.g., number, text).
* **Key constraint**: No duplicates for primary keys.
* **Entity integrity**: Primary key cannot be NULL.
* **Referential integrity**: Foreign key must match a value in the referenced table or be NULL.

---

## ✍️ **INSERT Operation**

### What it does:

Adds a new row (tuple) into a table.

### What can go wrong?

| Constraint                | Violation Example                                                         |
| ------------------------- | ------------------------------------------------------------------------- |
| **Domain constraint**     | Inserting text into a numeric field (e.g., Age = "Ten") ❌                 |
| **Key constraint**        | Inserting a row with a **duplicate primary key** ❌                        |
| **Entity integrity**      | Inserting a row with **NULL in the primary key** ❌                        |
| **Referential integrity** | Inserting a foreign key that **does not exist** in the referenced table ❌ |

---

## 🗑️ **DELETE Operation**

### What it does:

Removes an existing row from a table.

### What can go wrong?

* **Referential integrity violation**:
  If you delete a row that is **referenced as a foreign key** in another table.

### 💡 Example:

Suppose we have:

**DEPARTMENT**

| DeptID (PK) | DeptName |
| ----------- | -------- |
| D01         | HR       |

**EMPLOYEE**

| EmpID | Name  | DeptID (FK) |
| ----- | ----- | ----------- |
| 101   | Alice | D01         |

If you **DELETE** the row in `DEPARTMENT` where `DeptID = D01`, it breaks the link to `EMPLOYEE`, violating **referential integrity**.

---

### 🛠 Solutions to Referential Integrity Violation on DELETE:

| Option       | What it does                                            |
| ------------ | ------------------------------------------------------- |
| **RESTRICT** | Rejects the deletion ❌                                  |
| **CASCADE**  | Deletes related rows in the referencing table too ⚠️    |
| **SET NULL** | Sets the foreign key in the referencing table to NULL ✅ |

---

## ✏️ **MODIFY (UPDATE) Operation**

### What it does:

Changes a value in a specific column of a row.

### What can go wrong?

| Update Type                      | May Violate                  |
| -------------------------------- | ---------------------------- |
| Changing to an invalid value     | **Domain constraint** ❌      |
| Setting a NOT NULL field to NULL | **NOT NULL constraint** ❌    |
| Changing primary key (PK)        | Same risk as DELETE + INSERT |
| Changing foreign key (FK)        | **Referential integrity** ❌  |

### 💡 Example:

If you update an employee’s `DeptID` to a value not present in the `DEPARTMENT` table → Referential integrity breaks.

---
