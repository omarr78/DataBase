# 📌 Mapping ER Model to Relational Model

Here’s how you map each part of an ER diagram into relational tables (relations):

---

### ✅ **1. Each Entity → Becomes a Table (Relation)**

* For **each entity** in the ER model, create a separate relation.
* Include **all simple attributes**.
* Choose a **primary key**.

**Example**
Entity: `STUDENT(SID, Name, Age)`
→ Becomes table: `STUDENT(SID, Name, Age)`
`SID` is the **Primary Key**.

---

### ✅ **2. Multivalued Attribute → Becomes a New Table**

* A **multivalued attribute** means an entity can have **multiple values** for one attribute.
* Create a **new table**:

  * Include the **primary key** of the original entity
  * Include the **multivalued attribute**
  * Together, they form the **primary key** of the new table.

**Example**
Entity: `STUDENT(SID, Name, PhoneNumber{multivalued})`
→
Tables:

* `STUDENT(SID, Name)`
* `STUDENT_PHONE(SID, PhoneNumber)` ← both form the PK

---

### ✅ **3. N\:M (Many-to-Many) Relationship → Becomes a New Table**

* Create a **new relation** for each N\:M relationship.
* Include:

  * **Primary keys** of the related entities (as foreign keys)
  * **Attributes** of the relationship (if any)
  * The combination of foreign keys usually acts as the **primary key**

**Example**
Entities: `STUDENT(SID)`, `COURSE(CID)`
Relationship: `ENROLLS(SID, CID, Grade)` ← N\:M
→
Table: `ENROLLS(SID, CID, Grade)`
`SID` and `CID` are **foreign keys**, together forming the **primary key**.

---

### ✅ **4. 1\:N (One-to-Many) Relationship → Add FK on N-side**

* Add the **primary key** of the "1-side" as a **foreign key** into the "N-side".
* Also include any **attributes** of the relationship in the N-side table.

**Example**
Relationship: Each `DEPARTMENT` has many `EMPLOYEES` (1\:N)
→ Add `DeptID` as FK in `EMPLOYEE` table:

`EMPLOYEE(EID, Name, ..., DeptID)` ← `DeptID` is FK to `DEPARTMENT`

---

### ✅ **5. 1:1 (One-to-One) Relationship → Add FK from Partial to Total Participation Side**

* If both entities have **total participation**, choose either.
* If one has **partial participation**, place the **foreign key** in that one.
* Also add any attributes of the relationship.

**Example**
`EMPLOYEE` — 1:1 — `PARKING_SPOT`
If only some employees have parking spots → add FK in `PARKING_SPOT`

`PARKING_SPOT(SpotID, Location, EmpID)` ← `EmpID` is FK to `EMPLOYEE`

---

### ✅ **6. Derived Attributes → Not Stored in Table**

* Derived attributes (calculated from other data) **do not become columns** in a table.
* These are calculated when needed.

**Example**
`Age` derived from `DateOfBirth` → Only store `DateOfBirth`.

---

### ✅ **7. Attributes on Relationships (1:1 or 1\:N) → Go with FK**

* If a **relationship** (1:1 or 1\:N) has **attributes**, they go into the table where the **foreign key is added**.

**Example**
`DEPARTMENT` — has — `MANAGER` with attribute `StartDate`

→ Add FK `MgrID` and `StartDate` to the `DEPARTMENT` table:
`DEPARTMENT(DeptID, Name, MgrID, StartDate)`

---

## 🎯 Summary Table

| ER Component            | Mapping in Relational Model                        |
| ----------------------- | -------------------------------------------------- |
| Entity                  | Table (Relation)                                   |
| Multivalued Attribute   | New table with FK to main entity                   |
| N\:M Relationship       | New table with FKs from both entities + attributes |
| 1\:N Relationship       | Add FK to N-side table                             |
| 1:1 Relationship        | Add FK to side with partial participation          |
| Derived Attribute       | Do **not** store, calculate when needed            |
| Relationship Attributes | Add them to the table holding the FK               |

---
