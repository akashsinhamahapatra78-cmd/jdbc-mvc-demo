# JDBC-MVC-Demo

## Overview

This repository contains comprehensive Java applications demonstrating JDBC for database connectivity, CRUD operations, and MVC architecture patterns. The project is structured into three progressive parts, each building upon the knowledge from the previous section.

**Java Applications Using JDBC for Database Connectivity, CRUD Operations, and MVC Architecture**

---

## Project Objectives

### Part A: Connecting to MySQL and Fetching Data from a Table

**Objective:** To develop a Java program that connects to a MySQL database and retrieves data from a single table using JDBC.

- Establish database connection using JDBC drivers
- Execute SQL SELECT queries
- Fetch and display data from a database table
- Handle database exceptions gracefully
- Demonstrate basic JDBC workflow

### Part B: CRUD Operations on Product Table Using JDBC

**Objective:** To create a menu-driven Java program that performs CRUD operations (Create, Read, Update, Delete) on a Product table in a MySQL database with proper transaction handling.

- Create records in the Product table
- Read/Retrieve product information
- Update existing product details
- Delete product records
- Implement transaction management for data integrity
- Menu-driven user interface for easy navigation
- Input validation and error handling

### Part C: Student Management Application Using JDBC and MVC

**Objective:** To build a Java application that manages student data using JDBC and follows the Model-View-Controller (MVC) design pattern.

- Implement MVC architecture with clear separation of concerns
- Model layer: Database operations and business logic
- View layer: User interface and presentation
- Controller layer: Request handling and business logic orchestration
- Perform student CRUD operations through MVC pattern
- Demonstrate best practices in application design
- Scalable and maintainable code structure

---

## Project Structure

```
jdbc-mvc-demo/
├── README.md
├── .gitignore
├── LICENSE
├── Part-A-MySQL-Connection/
│   ├── src/
│   │   └── com/
│   │       └── example/
│   │           ├── MySQLConnection.java
│   │           ├── DataFetcher.java
│   │           └── Main.java
│   ├── lib/
│   │   └── mysql-connector-java-*.jar
│   └── README.md
├── Part-B-CRUD-Operations/
│   ├── src/
│   │   └── com/
│   │       └── example/
│   │           ├── database/
│   │           │   ├── DatabaseConnection.java
│   │           │   └── ProductDAO.java
│   │           ├── models/
│   │           │   └── Product.java
│   │           ├── menu/
│   │           │   └── ProductMenu.java
│   │           └── Main.java
│   ├── lib/
│   │   └── mysql-connector-java-*.jar
│   └── README.md
└── Part-C-MVC-Student-Management/
    ├── src/
    │   └── com/
    │       └── example/
    │           ├── model/
    │           │   ├── Student.java
    │           │   └── StudentDAO.java
    │           ├── view/
    │           │   ├── StudentView.java
    │           │   └── StudentUI.java
    │           ├── controller/
    │           │   └── StudentController.java
    │           ├── database/
    │           │   └── DatabaseConnection.java
    │           └── Main.java
    ├── lib/
    │   └── mysql-connector-java-*.jar
    └── README.md
```

---

## Technologies Used

- **Java**: JDK 8 or higher
- **MySQL**: 5.7 or higher
- **JDBC**: MySQL Connector/J
- **IDE**: IntelliJ IDEA, Eclipse, or VS Code (with Java extensions)
- **Build Tool**: Maven (Optional) or Manual Compilation
- **Design Pattern**: MVC (Model-View-Controller)

---

## Prerequisites

- Java Development Kit (JDK) 8 or higher
- MySQL Server installed and running
- MySQL JDBC Driver (mysql-connector-java)
- Basic knowledge of Java and SQL
- IDE or Text Editor for Java development

---

## Setup Instructions

### 1. Install MySQL Server

- Download MySQL from [mysql.com](https://www.mysql.com/downloads/)
- Install and start the MySQL service
- Note down the root username and password

### 2. Create Database and Tables

**For Part A:**

```sql
CREATE DATABASE jdbc_demo;
USE jdbc_demo;

CREATE TABLE employees (
    id INT PRIMARY KEY AUTO_INCREMENT,
    name VARCHAR(100) NOT NULL,
    department VARCHAR(50),
    salary DECIMAL(10, 2),
    hire_date DATE
);

INSERT INTO employees (name, department, salary, hire_date) VALUES
('John Doe', 'IT', 50000, '2020-01-15'),
('Jane Smith', 'HR', 45000, '2019-03-22'),
('Mike Johnson', 'IT', 55000, '2021-06-10');
```

**For Part B:**

```sql
CREATE TABLE product (
    product_id INT PRIMARY KEY AUTO_INCREMENT,
    product_name VARCHAR(100) NOT NULL,
    category VARCHAR(50),
    price DECIMAL(10, 2),
    quantity INT,
    created_date TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);
```

**For Part C:**

```sql
CREATE TABLE student (
    student_id INT PRIMARY KEY AUTO_INCREMENT,
    first_name VARCHAR(100) NOT NULL,
    last_name VARCHAR(100) NOT NULL,
    email VARCHAR(100) UNIQUE,
    phone_number VARCHAR(15),
    date_of_birth DATE,
    registration_date TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);
```

### 3. Download MySQL JDBC Driver

- Download from [MySQL Connector/J](https://dev.mysql.com/downloads/connector/j/)
- Extract and copy `mysql-connector-java-*.jar` to the `lib/` folder of each part

### 4. Clone the Repository

```bash
git clone https://github.com/yourusername/jdbc-mvc-demo.git
cd jdbc-mvc-demo
```

### 5. Configure Database Connection

Update the database credentials in the connection files:

```java
private static final String URL = "jdbc:mysql://localhost:3306/jdbc_demo";
private static final String USER = "root";
private static final String PASSWORD = "your_password";
```

---

## Usage Instructions

### Part A: MySQL Connection and Data Fetching

1. Navigate to `Part-A-MySQL-Connection/`
2. Compile the Java files:
   ```bash
   javac -cp lib/mysql-connector-java-*.jar src/com/example/*.java
   ```
3. Run the application:
   ```bash
   java -cp lib/mysql-connector-java-*.jar:src com.example.Main
   ```

**Output:**
Displays all employees from the employees table with formatted output.

### Part B: CRUD Operations

1. Navigate to `Part-B-CRUD-Operations/`
2. Compile the Java files:
   ```bash
   javac -cp lib/mysql-connector-java-*.jar src/com/example/**/*.java
   ```
3. Run the application:
   ```bash
   java -cp lib/mysql-connector-java-*.jar:src com.example.Main
   ```

**Menu Options:**
```
========== PRODUCT MANAGEMENT SYSTEM ==========
1. Create New Product
2. Read Product Details
3. Update Product
4. Delete Product
5. View All Products
6. Exit

Enter your choice: 
```

### Part C: MVC Student Management

1. Navigate to `Part-C-MVC-Student-Management/`
2. Compile the Java files:
   ```bash
   javac -cp lib/mysql-connector-java-*.jar src/com/example/**/*.java
   ```
3. Run the application:
   ```bash
   java -cp lib/mysql-connector-java-*.jar:src com.example.Main
   ```

**Features:**
- Add new students
- View all students
- Search for student by ID
- Update student information
- Delete student records
- Clean MVC architecture

---

## Key Features

### Part A
- ✓ Simple JDBC connection establishment
- ✓ SQL SELECT query execution
- ✓ Result set processing
- ✓ Exception handling
- ✓ Formatted data display

### Part B
- ✓ Menu-driven interface
- ✓ CRUD operations implementation
- ✓ Transaction management
- ✓ Input validation
- ✓ Error handling and logging
- ✓ Batch operations support

### Part C
- ✓ MVC design pattern implementation
- ✓ Separation of concerns
- ✓ Modular and scalable architecture
- ✓ Business logic layer
- ✓ Data access layer (DAO)
- ✓ User interface layer
- ✓ Full CRUD functionality

---

## Learning Outcomes

After completing this project, you will understand:

1. **JDBC Fundamentals**
   - Database connection management
   - Query execution and result processing
   - Exception handling in database operations

2. **CRUD Operations**
   - Create: INSERT operations with validation
   - Read: SELECT queries and result retrieval
   - Update: Modifying existing records
   - Delete: Removing records safely

3. **Transaction Management**
   - ACID properties
   - Commit and rollback operations
   - Data integrity maintenance

4. **MVC Architecture**
   - Model: Data models and business logic
   - View: User interface and presentation
   - Controller: Request handling and flow control
   - Benefits of separation of concerns

5. **Best Practices**
   - Proper resource management
   - Connection pooling basics
   - Error handling strategies
   - Code organization and modularity

---

## Common Issues and Solutions

### Issue: "No suitable driver found for jdbc:mysql://"

**Solution:** Ensure MySQL JDBC driver is properly added to the classpath:
```bash
-cp lib/mysql-connector-java-*.jar:src
```

### Issue: "Access denied for user 'root'@'localhost'"

**Solution:** Verify MySQL credentials in the connection file. Ensure MySQL service is running.

### Issue: "Unknown database 'jdbc_demo'"

**Solution:** Create the database using the SQL scripts provided in the Setup Instructions.

### Issue: "Table doesn't exist"

**Solution:** Execute the CREATE TABLE statements for the respective part.

---

## Database Connection Pattern

```java
public class DatabaseConnection {
    private static final String URL = "jdbc:mysql://localhost:3306/jdbc_demo";
    private static final String USER = "root";
    private static final String PASSWORD = "your_password";
    
    public static Connection getConnection() throws SQLException {
        return DriverManager.getConnection(URL, USER, PASSWORD);
    }
}
```

---

## Contributing

Contributions are welcome! Please feel free to:

- Report issues
- Suggest improvements
- Submit pull requests
- Share feedback

---

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

## Author

Created as an educational resource for learning JDBC and MVC architecture in Java.

---

## Resources

- [Official Java Documentation](https://docs.oracle.com/javase/)
- [MySQL Documentation](https://dev.mysql.com/doc/)
- [JDBC Tutorial](https://docs.oracle.com/javase/tutorial/jdbc/)
- [MVC Pattern](https://en.wikipedia.org/wiki/Model%E2%80%93view%E2%80%93controller)

---

## Support

For questions or issues, please create an issue in the GitHub repository.

---

**Last Updated:** November 2025
