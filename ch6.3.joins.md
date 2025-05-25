


![joins](https://github.com/user-attachments/assets/f8951b55-642a-449f-b8fb-6d33b6d7ec38)



We’ll denote:

* `R1 ← Department`
* `R2 ← Project`

Now let’s apply all join types:

---

## 1. **Inner Join (θ-Join)**

### ⨝ Join where `Dnumber = Dno`

📘 **Relational Algebra**:

```
R3 ← Department ⨝ Dnumber = Dno Project
```

### ✅ Result:

| Dnumber | Dname | Pno | Pname | Dno |
| ------- | ----- | --- | ----- | --- |
| 1       | D1    | 100 | ABC   | 1   |
| 2       | D2    | 200 | CDE   | 2   |
| 2       | D2    | 300 | EFG   | 2   |
| 3       | D3    | 400 | YUK   | 3   |


---

## 2. **Natural Join**

Only possible if both relations had a common column (say `Dnumber` in both).

📘 **Relational Algebra**:

```
R3 ← Department ⨝ Project
```

➡️ In this case, you'd need to rename `Dno → Dnumber` in Project first.

---

## 3. **Left Outer Join (⟕)**

Keeps all departments, even if no matching project.

📘 **Relational Algebra**:

```
R3 ← Department ⟕ Project
```

### ✅ Result:

| Dnumber | Dname | Pno  | Pname | Dno  |
| ------- | ----- | ---- | ----- | ---- |
| 1       | D1    | 100  | ABC   | 1    |
| 2       | D2    | 200  | CDE   | 2    |
| 2       | D2    | 300  | EFG   | 2    |
| 3       | D3    | 400  | YUK   | 3    |
| 4       | D4    | NULL | NULL  | NULL |
| 5       | D5    | NULL | NULL  | NULL |

---

## 4. **Right Outer Join (⟖)**

Keeps all projects, even if no matching department.

📘 **Relational Algebra**:

```
R3 ← Department ⟖ Project
```

### ✅ Result:

| Dnumber | Dname | Pno | Pname | Dno |
| ------- | ----- | --- | ----- | --- |
| 1       | D1    | 100 | ABC   | 1   |
| 2       | D2    | 200 | CDE   | 2   |
| 2       | D2    | 300 | EFG   | 2   |
| 3       | D3    | 400 | YUK   | 3   |
| NULL    | NULL  | 500 | ZZZ   | 6   |

---

## 5. **Full Outer Join (⟗)**

Keeps **all** departments and **all** projects, with NULLs where no match.

📘 **Relational Algebra**:

```
R3 ← Department ⟗ Project
```

### ✅ Result:

| Dnumber | Dname | Pno  | Pname | Dno  |
| ------- | ----- | ---- | ----- | ---- |
| 1       | D1    | 100  | ABC   | 1    |
| 2       | D2    | 200  | CDE   | 2    |
| 2       | D2    | 300  | EFG   | 2    |
| 3       | D3    | 400  | YUK   | 3    |
| 4       | D4    | NULL | NULL  | NULL |
| 5       | D5    | NULL | NULL  | NULL |
| NULL    | NULL  | 500  | ZZZ   | 6    |

---

### ✅ Summary Table of Join Types

| Join Type        | Keeps Unmatched Departments | Keeps Unmatched Projects |
| ---------------- | --------------------------- | ------------------------ |
| Inner Join       | ❌                           | ❌                        |
| Left Outer Join  | ✅                           | ❌                        |
| Right Outer Join | ❌                           | ✅                        |
| Full Outer Join  | ✅                           | ✅                        |

![image](https://github.com/user-attachments/assets/946b0278-16bf-4e8b-a493-9879e40b2324)

---

### 🔵 **Natural Join**

A **natural join (⨝)** is a type of join operation that automatically matches columns between two relations that
have the **same name** and **compatible types** — **without** explicitly specifying the join condition.


* **Implicit condition:** Attributes with **the same name** are matched.
* **Join condition:** An implicit **equality** condition is used between all pairs of common-named attributes.
* **No duplicates:** Only **one copy** of each matched attribute is kept in the result.
* **Notation:**

  ```
  R ⨝ S
  ```

---

### 📘 **Example 1: DEPARTMENT ⨝ DEPT\_LOCATIONS**

Given:

* Common attribute: `DNUMBER`
* No need to specify condition explicitly.

So we can write:

```
R ← DEPARTMENT ⨝ DEPT_LOCATIONS
```

### 🧠 What happens:

* The result will **merge** DEPARTMENT and DEPT\_LOCATIONS on `DNUMBER`.
* Only **one DNUMBER** column will appear in the result.

---

### 📘 **Example 2: Q ⨝ S**

Let:

* `Q(A, B, C, D)`
* `S(C, D, E)`

Then:

```
Q ⨝ S
```

### 🧠 What happens:

* Common attributes: `C` and `D`
* The join condition is:

  ```
  Q.C = S.C AND Q.D = S.D
  ```
* The result will be:

  ```
  Q(A, B, C, D, E)
  ```

Because `C` and `D` were matched, only **one copy** of each is retained.

---
