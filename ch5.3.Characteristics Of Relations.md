
## 📌 Characteristics of Relations (Tables)

A **relation** (or table) in a database has specific rules and behaviors. Let’s explore them one by one.

---

### 1. **Ordering of Tuples (Rows)**

* In **relational theory**, **tuples (rows) are *not* considered ordered**.
* Even though they appear in a certain order when shown in a table, that order **doesn't matter**.

#### Example:

These two tables are considered the **same relation**:

| ID | Name  |
| -- | ----- |
| 1  | Alice |
| 2  | Bob   |

and

| ID | Name  |
| -- | ----- |
| 2  | Bob   |
| 1  | Alice |

✅ Same relation → because the **set** of rows is the same.

---

### 2. **Ordering of Attributes (Columns)**

* **Attributes (columns) *are considered ordered*** when defining a relation schema.

#### Example:

For schema: `STUDENT(ID, Name, Major)`
→ We consider the order of columns as fixed: ID → Name → Major

Also, a tuple `<101, "Alice", "CS">` follows the same attribute order.

> ⚠️ Technically, some definitions allow unordered attributes, but we treat them as ordered in practice to avoid confusion.

---

### 3. **Values in a Tuple Are Atomic (Indivisible)**

* Every value in a tuple must be **atomic**, which means it **cannot be split** further.

✅ Valid: `"Alice"` as a Name
❌ Invalid: `{"Alice", "Bob"}` in one column (because it's a set, not atomic)

> This rule is part of the **First Normal Form (1NF)** in databases.

---

### 4. **Domain of Attributes**

* Each value must belong to the **domain** (allowed type/format) of that attribute.

#### Example:

If the domain of the `Age` attribute is "integers between 0 and 150",
then a value like `"twenty"` or `-5` is **not valid**.

---

### 5. **Null Values**

* Sometimes, a value is:

  * **Unknown** (we don’t know it yet)
  * **Not applicable** (it doesn't make sense for that row)

To represent this, we use a special value called **NULL**.

#### Example:

| ID | Name  | Phone    |
| -- | ----- | -------- |
| 1  | Alice | 555-1234 |
| 2  | Bob   | NULL     |

Bob has no phone number recorded → `NULL` used.

---

### 6. **Accessing Tuple Values**

We can refer to a specific value in a tuple using:

* `t[Ai]` or `t.Ai`
  Where:

  * `t` is a tuple
  * `Ai` is an attribute name
  * The result is the **value** for that attribute in that tuple

#### Example:

If `t = <101, "Alice", "CS">`, then:

* `t["Name"]` or `t.Name` = `"Alice"`
* `t["Major"]` or `t.Major` = `"CS"`

---
