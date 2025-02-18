# Employee Management Application

## 📌 Overview
This is a **Java-based Employee Management System** that allows users to perform CRUD operations (Create, Read, Update, Delete) on an `employee` table. The application uses **JDBC** to interact with a **MySQL database**.

## 📦 Features
- ✅ **Add Employee**
- ✅ **Update Employee** (if ID exists) or Insert (if ID does not exist)
- ✅ **Delete Employee** by ID
- ✅ **Retrieve Employee** by ID
- ✅ **Department table with Foreign Key in Employee table**
- ✅ **Uses Switch and Scanner for User Input**

## 🏗️ Technologies Used
- **Java (Core Java, JDBC)**
- **MySQL Database**
- **JDK 21 (Compatible with MySQL Connector/J 8.2.0)**

## 📂 Database Schema
### 🔹 `department` Table
```sql
CREATE TABLE department (
    id INT PRIMARY KEY,
    name VARCHAR(100) NOT NULL
);
```

### 🔹 `employee` Table
```sql
CREATE TABLE employee (
    id INT AUTO_INCREMENT PRIMARY KEY,
    name VARCHAR(100) NOT NULL,
    age INT NOT NULL,
    department_id INT,
    FOREIGN KEY (department_id) REFERENCES department(id) ON DELETE SET NULL
);
```

## ⚙️ Setup & Installation
### 1️⃣ **Database Setup**
```sql
CREATE DATABASE companydb;
USE companydb;
```
Run the table creation scripts mentioned above.

### 2️⃣ **Add MySQL Connector (JDBC Driver)**

#### 🔹 If using a JAR file
1. Download MySQL Connector/J from: [MySQL Official Site](https://dev.mysql.com/downloads/connector/j/)
2. Add the `.jar` file to your project's **classpath**.

### 3️⃣ **Configure Database Connection**
Modify `DatabaseManager` class:
```java
private static final String URL = "jdbc:mysql://localhost:3306/companydb";
private static final String USER = "root";
private static final String PASSWORD = "password";
```

### 4️⃣ **Run the Application**
Compile and run `Main.java`.
```sh
javac Main.java
java Main
```

## 🚀 How to Use
Upon running, the application provides options to **Add, Update, Delete, and Retrieve employees** using a **menu-driven approach with Scanner and Switch cases**.

## 🛠️ Future Enhancements
- ✅ Implement **Spring Boot** for better structure
- ✅ Add **RESTful APIs** for frontend integration
- ✅ Improve **exception handling and logging**

🎯 **Happy Coding! 🚀**

