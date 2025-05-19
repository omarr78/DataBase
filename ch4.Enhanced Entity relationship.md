

## ✅ **1. Superclasses and Subclasses**

### 🔹 What is a Superclass?

* A **Superclass** is a general entity (like a parent).
* It includes common attributes for a group of entities.

### 🔹 What is a Subclass?

* A **Subclass** is a more specific group within the superclass.
* It inherits the attributes and relationships of the superclass and adds its own.

---

### 📌 **Example:**

Let's say we have a general entity:
🧑‍💼 `EMPLOYEE`

This can have subclasses like:

* 👩‍💻 `ENGINEER` → has attribute: `Eng_type`
* 👨‍💼 `MANAGER` → manages projects
* ⌨️ `SECRETARY` → has attribute: `Typing_speed`
* 🕐 `HOURLY_EMPLOYEE` → has attribute: `Pay_scale`
* 💵 `SALARIED_EMPLOYEE` → has attribute: `Salary`

Each subclass represents a specific role or feature of an employee.

---

## ✅ **2. Specialization**

### 🔹 What is Specialization?

> The process of creating **subclasses** from a **superclass**.

**Why do we use it?**

* Because not all entities in the superclass share the same attributes or relationships.

### 📌 Example(attributes):

From `EMPLOYEE`, we define:

* `HOURLY_EMPLOYEE` (has `Pay_scale`)
* `SALARIED_EMPLOYEE` (has `Salary`)

Not all employees have both `Salary` and `Pay_scale`. That’s why we **specialize** them into different subclasses.

Certainly! Here's the missing example explained clearly:


📌 **Example(relationships):**

From `EMPLOYEE`, only some employees are **managers** — not all.

To represent this, we create a subclass:

* `MANAGER` — this subclass **only includes** those employees who **manage** projects or other employees.

📍 So, the **relationship** `MANAGES` is associated **only with** the `MANAGER` subclass, **not** the entire `EMPLOYEE` superclass.

![superclass and subclass](https://github.com/user-attachments/assets/b9ca518d-78b7-4479-a9cd-44aa1ad068a5)

---

## ✅ **3. Generalization**

### 🔹 What is Generalization?

> The reverse of specialization — Several classes with common features are generalized into a **superclass**.

**Why do we use it?**

* To avoid repetition and redundancy by finding what they share.



### 📌 Example:

![generalization](https://github.com/user-attachments/assets/2bd3c961-5fe5-4349-8be7-ce89ae3d2c17)

We can generalize:

* `CAR`
* `TRUCK`

into a common superclass: `VEHICLE`

Because they all have:

* vehicle_id
* price
* license_plate_on 


---

## ✅ **4. Constraints on Specialization/Generalization**

There are **two main constraints**:

---

### 🔸 A. Disjointness Constraint

#### ➤ Disjoint (Symbol: **`d`**)

* An entity can **only belong to one subclass**.

📌 Example:

![disjoint specialization](https://github.com/user-attachments/assets/201276c0-3a31-429a-939a-888e141b40b6)


* If an `EMPLOYEE` is a `SECRETARY`, they **cannot** be a `TECHNICIAN` or `ENGINEER`.

#### ➤ Overlapping (Symbol: **`o`**)

* An entity **can belong to more than one subclass**.

📌 Example:

![overlapping specialization](https://github.com/user-attachments/assets/a72cf2b7-2f8b-4ecd-a3e2-22d3c77808c1)

* An `PART` can be both a `MANUFACTURED_PART` and an `PURCHASED_PART`.

---

### 🔸 B. Completeness Constraint

![completeness constraint](https://github.com/user-attachments/assets/f8e7bd66-6ffb-4a72-b7d5-a80057ef84f1)


#### ➤ Total Specialization (Double Line)

* every entity in the superclass **must be a member of some subclass** in the specialization/generalization.
* `EMPLOYEE` must be `SALARIED_EMPLOYEE` or `HOURLY_EMPLOYEE`

#### ➤ Partial Specialization (Single Line)

* Some entities in the superclass may **not belong to any subclass**.
* Some `EMPLOYEE`s may not be `MANAGER`, `ENGINEER`, or `SECRETARY`.

---

## ✅ **5. Specialization & Generalization Structures**

### 🔸 Hierarchy

* A subclass has **only one superclass** (like a family tree with one parent).
* This is called **single inheritance**.

📌 Example:

```
     EMPLOYEE
        |
     ENGINEER
```

### 🔸 Lattice

* A subclass can have **more than one superclass** (like a network).
* This is called **multiple inheritance**.

📌 Example:

```
       EMPLOYEE           STUDENT 
           \                /
            \              /
            STUDENT_ASSISTANT
```

![Hierarchy   Lattices](https://github.com/user-attachments/assets/17369a4c-6f36-4606-a802-9deca090c974)

---
## ✅ **6. Categories (UNION TYPES) (Symbol: **`U`**)**

* In some cases, we need to model a single superclass/subclass relationship with more than one superclass
* Superclasses can represent different entity types
* Such a subclass is called a category or UNION TYPE

![image](https://github.com/user-attachments/assets/48db49b0-9642-472c-9dbd-0fae62f5d720)
