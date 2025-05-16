## 🔶 1. **Entities**

Entities are real-world objects or things about which we store data.

### ✅ Examples:

* **EMPLOYEE** (a person working in a company)
* **OFFICE** (a physical place)
* **PROJECT** (a specific task with goals)

Each entity is represented as a **rectangle** in an ER diagram.

![image](https://github.com/user-attachments/assets/b8ab2888-f80a-4863-b39a-36d74dbe33e4)


---

## 🔶 2. **Attributes**

Attributes are **details or properties** of an entity.

### Example:

**EMPLOYEE** entity can have:

* Name
* SSN (Social Security Number)
* Address
* BirthDate

Each attribute is represented as an **oval** in an ER diagram and connected to its entity.


![image](https://github.com/user-attachments/assets/ce8b9d9c-8e08-4dcf-be8c-844661c94fce)



---

## 🔷 Types of Attributes (with diagrams)

### 1. **Simple Attribute**

* Cannot be divided.
* Holds one value only.
* Example: `Sex`, `Age`

📍 **ER Symbol**:

![image](https://github.com/user-attachments/assets/0b62ab39-a9b0-4620-98ee-3053d99f93ff)


---

### 2. **Composite Attribute**

* Can be divided into smaller sub-parts.
* Example: `Name` → FirstName, MiddleName, LastName

📍 **ER Symbol**:

![image](https://github.com/user-attachments/assets/8748002a-013c-4c78-ba1d-3fe95b57d8e9)


---

### 3. **Multi-Valued Attribute**

* Can hold multiple values.
* Example: `PhoneNumbers`

📍 **ER Symbol**: Double oval

![image](https://github.com/user-attachments/assets/d1dab082-0ab6-4741-b8da-851b8ab023a2)

---

### 4. **Derived Attribute**

* **Derived**: Calculated from stored data (e.g., `Area` from `Radius`)

📍 **ER Symbol**: Dashed oval for derived

![image](https://github.com/user-attachments/assets/1ba72875-5862-4b1a-9198-31a0e71c0599)

---

### 5. **Complex Attribute**

* An attribute that is **composite + multi-valued**.
* Example: `Address` can have multiple values and each with components.

![image](https://github.com/user-attachments/assets/1f451140-8172-4d23-ab58-e3a5d3d7b975)


---

## 🔶 6. **Key Attribute**

* Uniquely identifies each entity.
* Example: `SSN` for EMPLOYEE.

👉 **Can have more than one key (called candidate keys)**. One is chosen as **primary key**.

📍 **ER Symbol**: Underlined attribute

![image](https://github.com/user-attachments/assets/bf697e5c-b7e4-4f65-9725-abdbd920261f)


---

## 🔶 4. **Weak Entity**

* Cannot be uniquely identified without another (strong) entity.
* Depends on a strong entity for identification.

### Example:

* **Dependent** (child or spouse of employee)
* Needs EMPLOYEE’s ID + dependent name

📍 **ER Symbol**:

![image](https://github.com/user-attachments/assets/041f2074-5450-469d-9d91-4e01f31082b1)


---

## 🔶 5. **Relationships**

A relationship connects two or more entities.

### Types:

### ✅ **Binary Relationship**: Between 2 entities

* Example: `EMPLOYEE works_on PROJECT`

### ✅ **Ternary Relationship**: Among 3 entities

* Example: `DOCTOR prescribes MEDICINE to PATIENT`

📍 **ER Symbol**: 

![image](https://github.com/user-attachments/assets/f0fa8e0b-ef8e-46fe-880c-0bf1767f0b82)


---

## 🔷 Recursive Relationship

* An entity relates to itself.
* Example: An **EMPLOYEE supervises another EMPLOYEE**

![image](https://github.com/user-attachments/assets/21e7dd63-a9a4-4a4f-a36a-5807a48fbb3b)


---

## 🔶 6. **Participation Constraints**

### ✅ **Total Participation**:

* Every instance of the entity **must** be involved in the relationship.
* Drawn with **double line**.

### ✅ **Partial Participation**:

* Some instances are involved.
* Drawn with **single line**.

### Example:

* All employees must work in at least one department (total).
* Some projects may have no employees (partial).

---

## 🔶 7. **Min-Max Cardinality**

This shows **how many instances** of one entity can be associated with how many of another.

### Example:

* An EMPLOYEE can work on **1 to many** PROJECTS.
* A PROJECT can have **1 to many** EMPLOYEES.

![image](https://github.com/user-attachments/assets/94ae2a7d-0691-481a-b54b-33ec7f2a3336)


---
