# Student Registration Web Application

A lightweight Java EE web application for registering students using **Java Servlets, JDBC, Maven, and MySQL**. This project demonstrates form handling, server-side validation, database integration, and secure SQL operations.

## ✨ Features

- **Student Registration:** Register students using HTML forms.
- **Dynamic Form Rendering:** Generate registration forms using Java Servlets.
- **Input Validation:** Validate student details on the server side.
- **Database Integration:** Store student information in MySQL using JDBC.
- **SQL Injection Prevention:** Use parameterized `PreparedStatement` queries.
- **PRG Pattern:** Prevent duplicate form submissions using Post/Redirect/Get.
- **Success Page:** Display confirmation after successful registration.

## 🛠️ Technologies Used

- **Language:** Java 11+
- **Web Technology:** Java Servlets 4.0.1
- **Server:** Apache Tomcat 9
- **Database:** MySQL 8.0+
- **Database Connectivity:** JDBC
- **Build Tool:** Apache Maven

## 📁 Project Structure

```text
StudentServletApp/
├── pom.xml
├── README.md
└── src/
    └── main/
        ├── java/
        │   └── com/
        │       └── example/
        │           ├── StudentController.java
        │           └── DBConnection.java
        └── webapp/
            ├── index.html
            ├── success.html
            └── WEB-INF/
                └── web.xml
```

## 🗄️ Database Setup

Create the database and table in MySQL:

```sql
CREATE DATABASE IF NOT EXISTS studentdb;

USE studentdb;

CREATE TABLE IF NOT EXISTS students (
    id INT AUTO_INCREMENT PRIMARY KEY,
    name VARCHAR(255) NOT NULL,
    email VARCHAR(255) NOT NULL,
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);
```

Update the database URL, username, and password in `DBConnection.java` according to your MySQL configuration.

**Security Note:** Avoid committing database passwords to public repositories. Use environment variables to manage credentials securely.

## 🚀 Getting Started

### Prerequisites

- JDK 11 or higher
- Apache Maven 3.6+
- Apache Tomcat 9
- MySQL Server 8.0+

### 1. Clone the Repository

```bash
git clone <your-repository-url>
cd StudentServletApp
```

### 2. Build the Project

Run the following command from the project root:

```bash
mvn clean package
```

The generated WAR file will be available in the `target/` directory.

### 3. Deploy the Application

Copy the generated WAR file into the Tomcat `webapps/` directory and start the server.

**Windows:**
```bat
bin\startup.bat
```

**Linux/macOS:**
```bash
./bin/startup.sh
```

### 4. Open the Application

Visit the following URL in your browser:

`http://localhost:8080/student-app/`

*Replace `student-app` with your deployed WAR filename if different.*

## 🌐 Application Endpoints

| Endpoint | Method | Description |
|---|---|---|
| `/` | GET | Displays the static registration form |
| `/student` | GET | Displays the dynamic registration form |
| `/student` | POST | Processes registration and saves student details |
| `/success.html` | GET | Displays the registration success page |

*The actual endpoint mappings depend on your servlet configuration and deployed application context.*

## 🔒 Security

- Use `PreparedStatement` to help prevent SQL injection.
- Validate user input on the server side.
- Keep database credentials out of source control.
- Configure appropriate database permissions.

## 📄 License

This project is licensed under the **Apache License 2.0**. See the `LICENSE` file for details.
