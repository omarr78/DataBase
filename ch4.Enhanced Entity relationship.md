

## **1. What Are Superclasses and Subclasses?**

---

### 🔸 **Why Use Subclasses?**

Sometimes, entities (like `EMPLOYEE`) share some common features, but also have additional, specific characteristics.
So we break them into **subclasses** to handle these differences **without duplicating** information.

---

## 🧠 **Example: EMPLOYEE Superclass**

Imagine we have a general entity:
**EMPLOYEE**

All employees have common attributes:

* `Name`
* `SSN`
* `Address`
* `Salary`

But some employees have **special roles**. For example:

| Subclass            | Special Attribute or Role |
| ------------------- | ------------------------- |
| `ENGINEER`          | Has `Engineering Field`   |
| `SECRETARY`         | Has `Typing Speed`        |
| `TECHNICIAN`        | Has `Skill Set`           |
| `MANAGER`           | Manages `Department`      |
| `SALARIED_EMPLOYEE` | Paid Monthly              |
| `HOURLY_EMPLOYEE`   | Paid Per Hour             |

---

## 📌 Key Concepts

1. **Subclass** = A specialized version of a superclass

   > `ENGINEER` is a subclass of `EMPLOYEE`.

2. **Superclass** = The general entity type

   > `EMPLOYEE` is the superclass of `ENGINEER`, `SECRETARY`, etc.

3. **One employee can belong to multiple subclasses**

   > For example:

   * John is an `ENGINEER` and a `SALARIED_EMPLOYEE`
   * Alice is a `MANAGER`, `ENGINEER`, and `SALARIED_EMPLOYEE`

4. **Not every employee has to be in a subclass**

   > For instance, a general employee record may exist without belonging to any specific role.

---

## ✅ **Why Use This Structure in ER Modeling?**

It helps you:

* Avoid repeating common attributes.
* Keep data organized and meaningful.
* Model real-world scenarios accurately.

---
![superclass and subclass](https://github.com/user-attachments/assets/b9ca518d-78b7-4479-a9cd-44aa1ad068a5)

---
