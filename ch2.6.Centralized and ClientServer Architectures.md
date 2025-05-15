## 🖥️ 1. Centralized DBMS Architecture

### 🔹 What is it?

A **centralized database system** means everything is done on **one main computer (the server)**—this includes:

* Running application programs
* Managing the database
* User interface handling

The **users** only have simple devices (called **terminals**) that can **display information** but **don’t process anything**.

![image](https://github.com/user-attachments/assets/1dec5c3c-2e6e-4db8-9887-f8652070b2fa)


### 📌 Example:

You’re using a calculator, but all the calculations happen on someone else’s computer—you just see the results.

---

## 🌐 2. Basic Client/Server Architecture

### 🔹 What is it?

In a **client/server model**, the work is divided between:

* **Clients** (e.g., your PC) → used to send requests
* **Servers** → powerful machines that handle the requests

There are also **specialized servers** like:

* File Server: Stores files
* Printer Server: Handles printing
* Database Server: Manages databases

![image](https://github.com/user-attachments/assets/4bf2bd25-feae-44a0-a54b-42b43bfb3a1d)


---

## 🧱 Types of DBMS Architectures

---

### 💻 3. Two-Tier Client/Server Architecture

### 🔹 What is it?

This setup splits the system into **2 layers (tiers):**

1. **Client Tier**:

   * Runs the **user interface** (GUI)
   * Runs the **application program**
2. **Server Tier**:

   * Runs the **DBMS**
   * Handles **SQL queries and transactions**

### 💡 Example:

You open a desktop app that sends a request to a remote database (like MySQL), gets the result, and shows it on screen.

---

### 🧩 How It Works:

* The client connects to the database server.
* Sends a request using **SQL**.
* The **server processes** the request and sends back the result.
* Client displays the result.

### 🧰 Tools Used:

* **ODBC (Open Database Connectivity)**: A standard for connecting apps to databases.
* **JDBC (Java Database Connectivity)**: Java’s version of ODBC.

---

### 📊 Summary – Two-Tier

| Tier   | Responsibility                     |
| ------ | ---------------------------------- |
| Client | User interface + Application logic |
| Server | SQL processing + Data management   |

---

### 🌐 4. Three-Tier Architecture (Common in Web Apps)

### 🔹 What is it?

A more modern approach with **3 layers:**

1. **Client Tier**:

   * Web browser or mobile app
   * Shows the user interface

2. **Application Tier (Middle Tier)**:

   * Also called **Application Server** or **Web Server**
   * Handles business logic (e.g., rules like “users must log in before viewing orders”)
   * Receives requests from the client, then communicates with the database

3. **Database Tier**:

   * Stores and processes the actual data
   * Sends results back through the middle tier to the client

![image](https://github.com/user-attachments/assets/0379f2b8-a585-4b7f-9212-44a954e0f616)

---

### 📱 Example:

You open Amazon on your phone:

* **Client Tier**: You see the product page
* **Middle Tier**: Web server handles your search and checks if you're logged in
* **Database Tier**: Your search is sent to the database, which finds matching products

---

### 🧠 Why Use Three Tiers?

* **Better security**: Middle tier checks credentials before database access
* **Scalability**: Each layer can be upgraded separately
* **More flexibility**: Logic and presentation are separated

---

## 📌 Final Comparison Table

| Architecture | Layers | Description                       | Example                    |
| ------------ | ------ | --------------------------------- | -------------------------- |
| Centralized  | 1      | Everything on one computer        | Old mainframe banks        |
| Two-Tier     | 2      | App logic on client, DB on server | Desktop app with SQL       |
| Three-Tier   | 3      | App logic on middle server        | Web apps (Amazon, Netflix) |

