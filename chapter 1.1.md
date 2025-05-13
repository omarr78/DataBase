
### What Is a Database?

A **database** is a collection of **related data**—facts that are recorded and have meaning.
For example:

> A list of people’s names, phone numbers, and addresses.

---

### Key Properties of a Database:

1. **Represents the Real World (Miniworld):**
   A database models a specific part of the real world.
   Any change in the real world is reflected in the database.

   > *Example: If someone changes their phone number, the database should be updated too.*

2. **Logically Organized and Meaningful:**
   Data in a database is arranged in a meaningful way. Random or unorganized data doesn’t qualify as a database.

3. **Designed for a Purpose:**
   Every database is built with a specific goal and has an intended group of users.

   > *Example: A school database is designed for teachers, students, and administrators to manage academic records.*

---

### Types of Database Applications:

* **Traditional Databases:**
  Store **textual** or **numerical** data.

  > *Example: Customer details or employee records.*

* **Multimedia Databases:**
  Store **images**, **audio**, and **videos**.

  > *Example: A music streaming app's database.*

* **Geographic Information Systems (GIS):**
  Store and analyze **maps**, **weather data**, and **satellite images**.

* **Data Warehouses and online analytical processing OLAP Systems:**
  Analyze large volumes of data to support **business decisions**.

  > *Example: A sales report across different regions for a company.*

---

### What Is a DBMS?

- A **Database Management System (DBMS)** is a collection of program that enables  users to create and maintain a database.
- The DBMS is a general-purpose software system that facilitates the processes of `defining`, `constructing`, `manipulating`, and `sharing`
databases among various users and applications.
---

### Main Functions of a DBMS:

1. **Defining the Database**

   * Specifies the **data types**, **structures**, and **constraints** for storing data.
   * This information is saved in a special place called the **data dictionary** or **metadata**.

   > *Example: Defining that a student’s name must be text and their age must be a number.*

2. **Constructing the Database**

   * Involves **storing data** on a physical device like a hard drive, which is managed by the DBMS.

3. **Manipulating the Database**

   * **Querying**: Asking questions to retrieve specific data.

     > *Example: “Find all customers from New York.”*
   * **Updating**: Making changes to reflect real-world updates.

     > *Example: Changing a customer’s phone number.*
   * **Reporting**: Creating summaries or structured outputs from the data.

4. **Sharing the Database**

   * Multiple users and applications can access the database at the **same time**.

---

### How Applications Use a DBMS:

Applications interact with a DBMS by sending:

* **Queries** to **retrieve** data.
* **Transactions** to **read** and **write** data.

> *Example: An e-commerce app updating inventory when a customer places an order.*

---

### Additional Features of a DBMS:

* **Protection**:

  * **System protection**: Guards against hardware or software failures.
  * **Security protection**: Prevents unauthorized access or malicious access.

* **Maintenance and Evolution**:

  * A DBMS supports the database as it changes over time.
  * It ensures the database continues working properly as business needs evolve.

> *Example: As a company grows, new features like customer reviews or delivery tracking might be added to the database.*

---

### Example: UNIVERSITY Database

A university database stores information about:

* **Students**
* **Courses**
* **Course Sections**
* **Grades**
* **Prerequisites**

---

### Data Files and Their Structure

Each **record type** stores specific information. Each piece of data has a defined type, like **text (string)** or **number (integer)**.

#### 1. **STUDENT**

* Student ID (String)
* Name (String)
* Major (String)
* Class (String – e.g. Sophomore)

#### 2. **COURSE**

* Course ID (String)
* Course Name (String)
* Department (String)

#### 3. **SECTION**

* Section ID (String)
* Course ID (String)
* Semester (String)
* Instructor (String)

#### 4. **GRADE\_REPORT**

* Student ID (String)
* Section ID (String)
* Grade (String – e.g., A, B, C)

#### 5. **PREREQUISITE**

* Course ID (String)
* Prerequisite Course ID (String)

---

### Constructing the Database

To build the UNIVERSITY database:

* Store actual data for each student, course, section, grade, and prerequisite as **records** in the appropriate file.
* **Define relationships** between records.

  > *Example: A GRADE\_REPORT connects a STUDENT and a GRADE.*

---

### Data Manipulation

The database can be used to:

#### ✅ **Query (Retrieve Information)**

* **Get a student’s transcript**

  > *Show all courses and grades for a student.*

* **List names and grades** of students who took the **'Database' course in Fall 2008**.

* **Find prerequisites** for the **'Database' course**.

#### 🔄 **Update (Change or Add Data)**

* **Change a student's class**

  > *Update ‘Smith’ to Sophomore.*

* **Add a new section**

  > *Create a new section for the ‘Database’ course this semester.*

* **Enter a new grade**

  > *Assign grade ‘A’ to ‘Smith’ in the Database course section from last semester.*

---

![Screenshot 2025-05-14 014342](https://github.com/user-attachments/assets/506a690d-63d7-4d70-9b03-25ebc8c94ca7)

![example-of-dbms-catalog-n](https://github.com/user-attachments/assets/cccc1042-029b-449e-9a10-42ca071024eb)

