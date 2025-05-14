## 🗣️ DBMS Languages

To work with a database, we need different types of **languages**—each one has a special job. Think of them as **tools** for different tasks like **creating**, **viewing**, or **changing** data.

---

### 1. **Data Definition Language (DDL)**

> Used to **define the structure** of the database.

* It creates **tables**, **schemas**, and defines **constraints** (like primary keys, data types, etc.).
* It works at both the **conceptual level** and **external level**.

🧠 Example:

```sql
CREATE TABLE Student (
  StudentID INT PRIMARY KEY,
  Name VARCHAR(100),
  Major VARCHAR(50)
);
```

---

### 2. **Storage Definition Language (SDL)**

> Used to define **how data is stored physically** in the database.

* It works at the **internal level**.
* Defines storage details like file organization, indexing, compression.

📌 Note: Modern DBMSs often **hide SDL from users**, but the DBMS uses it internally.

🧠 Example: (conceptual)

* Define how `Student` records are stored on disk and whether an **index** should be created for faster searching.

---

### 3. **View Definition Language (VDL)**

> Used to create **user views** of the database.

* Views allow users to see only the **relevant parts** of the data.
* VDL defines **external schemas** and maps them to the **conceptual schema**.

🧠 Example:

```sql
CREATE VIEW StudentNames AS
SELECT StudentID, Name FROM Student;
```

✅ VDL as the **custom filter** — showing only what the user needs.

---

### 4. **Data Manipulation Language (DML)**

> Used to **work with the actual data** (insert, delete, update, retrieve).

* There are two types:

  * **High-level DML**: Easy-to-use (like SQL).
  * **Low-level DML**: More detailed, used in programming.

🧠 Example:

```sql
-- Insert a new student
INSERT INTO Student (StudentID, Name, Major) VALUES (1, 'Ali', 'Computer Science');

-- Update a student’s major
UPDATE Student SET Major = 'Data Science' WHERE StudentID = 1;

-- Delete a student
DELETE FROM Student WHERE StudentID = 1;

-- Get all student names
SELECT Name FROM Student;
```
