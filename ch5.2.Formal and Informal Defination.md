

## 🧩 Informal vs Formal Terms in Relational Databases

| Informal Term              | Formal Term           |
| -------------------------- | --------------------- |
| Table                      | Relation              |
| Column Header              | Attribute             |
| All Possible Column Values | Domain                |
| Row                        | Tuple                 |
| Table Definition           | Schema of a Relation  |
| Populated Table            | State of the Relation |

---

## 📘 Informal Definitions

### 🔹 Relation = Table

A **relation** is like a table in a database. It consists of **rows** and **columns**.

### 🔹 Tuple = Row

Each **row** (tuple) represents a single record. For example, one student in a STUDENT table.

### 🔹 Attribute = Column

Each **column** (attribute) describes one property of the record (like name, ID, or age).

### 🔹 Domain

A **domain** is the type of data a column can have. For example, the domain of an Age column might be “integers between 0 and 150”.

---

## 🎓 Example: STUDENT Table

| SSN         | Name        | Major            |
| ----------- | ----------- | ---------------- |
| 123-45-6789 | Alice Smith | Computer Science |
| 987-65-4321 | Bob Jones   | Engineering      |

* This table is a **relation**
* Each row is a **tuple**
* Each column is an **attribute**
* `SSN` can be a **key** (it uniquely identifies each student)

---

## 🔑 Keys in a Relation

A **key** is one or more attributes (columns) that **uniquely identify** each tuple (row) in a relation.

### Example:

* In the `STUDENT` table, `SSN` is a key.
* If we assign a system-generated ID (like 1, 2, 3...), that's called a **`artificial key`** or **`surrogate key`**.

---

## 🧱 Formal Definitions

### 1. **Relation Schema**

* A schema defines the structure of a relation.
* Notation:
  **R(A1, A2, ..., An)**
  where:

  * **R** is the relation name (like `CUSTOMER`)
  * **A1, A2, ..., An** are the attribute names (columns)

#### Example:

```plaintext
CUSTOMER(Cust-id, Cust-name, Address, Phone#)
```

* This defines a table called `CUSTOMER` with 4 attributes.

---

### 2. **Tuple**

* A **tuple** is a row of actual data.
* Written as:
  `<value1, value2, ..., valueN>`

#### Example:

```plaintext
<632895, "John Smith", "101 Main St", "(404)894-2000">
```

This is one record (tuple) in the `CUSTOMER` relation.

---

### 3. **Domain**

* A **domain** is the set of valid values for an attribute.

#### Example:

* The domain of `Phone#` might be U.S. phone numbers, like:
  `(ddd)ddd-dddd` → `(404)894-2000`

* The attribute name designates the role played by a domain in a
relation
* Two attributes can use the same domain but have different meanings:

  * `"Invoice-date"` and `"Payment-date"` can both use the domain of valid dates.

---

### 4. **Relation State**

* subset of the cartesian product of the domains of its attributes
* A **relation state** is the **current content** (tuples) in a relation at a specific moment.
* It’s a subset of all **possible combinations** of the domain values.

#### Example:

Schema:

```plaintext
R(A1, A2)
```

Domains:

* dom(A1) = {0, 1}
* dom(A2) = {a, b, c}

All possible combinations (cartesian product):

```plaintext
{<0,a>, <0,b>, <0,c>, <1,a>, <1,b>, <1,c>}
```

Possible relation state:

```plaintext
r(R) = {<0,a>, <1,b>, <1,c>}
```

---

## ✅ Summary

| Term           | Meaning                       | Example                                 |
| -------------- | ----------------------------- | --------------------------------------- |
| Relation       | Table                         | STUDENT, CUSTOMER                       |
| Tuple          | Row of data                   | `<632895, "John Smith", "101 Main St">` |
| Attribute      | Column                        | Name, Address, Phone#                   |
| Domain         | Valid values for an attribute | Phone# domain: (ddd)ddd-dddd            |
| Schema         | Structure of the relation     | `CUSTOMER(Cust-id, Cust-name, Address)` |
| Relation State | Actual data in the relation   | Set of tuples like {t1, t2, ..., tn}    |
| Key            | Uniquely identifies a row     | SSN or Cust-id                          |
| Surrogate Key  | System-generated key          | 1, 2, 3...                              |

---
