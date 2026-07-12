# 📝 Simple To-Do Web Application

A simple and user-friendly **To-Do List Web Application** built using **Python Flask** and **Microsoft SQL Server**. This application allows users to create, edit, complete, and delete tasks while storing all data persistently in a SQL Server database.

---

## 📌 Features

* ➕ Add new tasks
* ✏️ Edit existing tasks
* ✅ Mark tasks as completed
* ❌ Delete tasks
* 🕒 Display the task creation date and time
* 💾 Store tasks permanently in Microsoft SQL Server
* 🎨 Clean and responsive user interface

---

## 🛠️ Technologies Used

### Backend

* Python 3.x
* Flask

### Frontend

* HTML5
* CSS3
* JavaScript (for client-side interactions)

### Database

* Microsoft SQL Server 2022
* PyODBC
* Microsoft ODBC Driver 18 for SQL Server

### Development Tools

* Visual Studio Code
* SQL Server Management Studio (SSMS)
* Git & GitHub

---
## ⚙️ Installation

### 1. Clone the Repository

```bash
git clone https://github.com/your-username/simple-todo.git
cd simple-todo
```

---

### 2. Create a Virtual Environment

Windows

```bash
python -m venv venv
venv\Scripts\activate
```

Linux/Mac

```bash
python3 -m venv venv
source venv/bin/activate
```

---

### 3. Install Dependencies

```bash
pip install flask
pip install pyodbc
```

or

```bash
pip install -r requirements.txt
```

---

## 🗄️ Database Setup

### Install

* Microsoft SQL Server 2022 Developer Edition
* SQL Server Management Studio (SSMS)
* Microsoft ODBC Driver 18 for SQL Server

---

### Create Database

```sql
CREATE DATABASE TodoDB;
```

---

### Create Tasks Table

```sql
CREATE TABLE Tasks(
    id INT IDENTITY(1,1) PRIMARY KEY,
    content NVARCHAR(255) NOT NULL,
    completed BIT DEFAULT 0,
    created_at DATETIME DEFAULT GETDATE()
);
```

---

## 🔌 Configure Database Connection

Update the connection details in `app.py`.

```python
server = 'localhost'
database = 'TodoDB'
username = 'sa'
password = 'YourPassword'
driver = '{ODBC Driver 18 for SQL Server}'
```

Connection:

```python
conn = pyodbc.connect(
    f"DRIVER={driver};SERVER={server};DATABASE={database};UID={username};PWD={password};TrustServerCertificate=yes"
)
```

---

## ▶️ Running the Application

Activate the virtual environment and run:

```bash
python app.py
```

Open your browser and visit:

```text
http://127.0.0.1:5000
```

---

## 💡 Application Workflow

1. User enters a task.
2. Flask receives the request.
3. Task is stored in Microsoft SQL Server.
4. Flask retrieves all tasks from the database.
5. Tasks are displayed dynamically using Jinja2 templates.
6. Users can edit, mark complete, or delete tasks.

---

## 🧱 Database Schema

| Column     | Data Type     | Description             |
| ---------- | ------------- | ----------------------- |
| id         | INT           | Primary Key             |
| content    | NVARCHAR(255) | Task description        |
| completed  | BIT           | Task completion status  |
| created_at | DATETIME      | Task creation timestamp |

---

## 📸 Features Demonstrated

* CRUD Operations (Create, Read, Update, Delete)
* Flask Routing
* SQL Server Integration
* Jinja2 Templates
* HTML Forms
* CSS Styling
* Database Connectivity using PyODBC

---

## 📚 Concepts Used

### Python

* Functions
* Modules
* Flask Framework
* Database Connectivity
* Exception Handling

### Flask

* Routes
* Templates
* GET & POST Methods
* Redirects
* URL Routing

### SQL Server

* Database Creation
* Tables
* INSERT
* SELECT
* UPDATE
* DELETE
* Primary Keys
* Identity Columns

### Frontend

* HTML Forms
* CSS Styling
* Flexbox Layout
* Buttons
* Lists
* Timestamps

---

## 🚀 Future Enhancements

* User authentication and login
* Task priorities
* Due dates and reminders
* Search and filter tasks
* Dark mode
* Responsive mobile design
* File attachments
* Task categories
* REST API integration
* Cloud deployment

---

## 🎯 Learning Outcomes

Through this project, I gained hands-on experience in:

* Developing web applications using Flask
* Integrating Python with Microsoft SQL Server
* Implementing CRUD operations
* Designing responsive user interfaces
* Managing databases using SQL queries
* Debugging and resolving database connectivity issues
* Using GitHub for version control and project sharing

---
