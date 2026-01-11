# Flask Single-Tier CRUD Application

A simple Flask-based Single-Tier CRUD (Create, Read, Update, Delete) application using **SQLite** and **SQLAlchemy ORM**.  
This project demonstrates basic CRUD operations with a clean folder structure and local database storage.

---

## 1. Project Overview

This application allows users to:  
- Add users  
- View users  
- Edit users  
- Delete users  

It follows a single-tier architecture, where:  
- Flask handles backend logic and UI rendering  
- SQLite stores data locally on the same server  

---

## 2. Project Directory Structure

```
flask-crud/
├── app.py                 # Main Flask application
├── models.py              # Database model definition
├── users.db               # SQLite database (auto-created)
│
├── templates/             # Jinja2 HTML templates
│   ├── base.html
│   ├── index.html
│   ├── add.html
│   └── edit.html
│
└── README.md              # Project documentation
```

---

## 3. Technology Stack

- **Language:** Python  
- **Framework:** Flask  
- **ORM:** Flask-SQLAlchemy  
- **Database:** SQLite  
- **Frontend:** HTML, Jinja2 Templates  

---

## 4. Prerequisites

Ensure the following are installed:  
- Python 3.8+  
- pip (Python package manager)  

Verify installation:

```bash
python --version
pip --version
```

---

## 5. Application Setup

**Step 1: Clone the Repository**

```bash
git clone YOUR_REPO_URL
cd flask-crud
```

**Step 2: Create Virtual Environment (Optional)**

```bash
python -m venv venv
```

Activate the environment:

- **Windows**  
  ```bash
  venv\Scripts\activate
  ```
- **Linux / macOS**  
  ```bash
  source venv/bin/activate
  ```

**Step 3: Install Dependencies**

```bash
pip install flask flask-sqlalchemy
```

---

## 6. Running the Application

Start the Flask server:

```bash
python app.py
```

Access the application in your browser:  
[http://127.0.0.1:5000/](http://127.0.0.1:5000/)

---

## 7. Database Details

- **Database Type:** SQLite  
- **Database File:** `users.db`  
- **Creation:** Automatically created on first run  
- **Table Name:** `user`  

**Table Schema:**

| Column | Type                |
|--------|-------------------|
| id     | Integer (Primary Key) |
| name   | String             |

You can inspect the database using:  
- DB Browser for SQLite  
- SQLiteStudio  

---

## 8. Application Routes

| Operation  | Endpoint      | Method     |
|------------|---------------|------------|
| View Users | `/`           | GET        |
| Add User   | `/add`        | GET, POST  |
| Edit User  | `/edit/<id>`  | GET, POST  |
| Delete User| `/delete/<id>`| GET        |

---

## 9. Application Flow

1. Open home page to view users  
2. Click **Add User** to create a new record  
3. Edit or delete users from the list  
4. Data is persisted in SQLite database  

---

## 10. Notes & Limitations

- Designed for learning and development  
- Debug mode enabled  
- SQLite not suitable for production  
- Delete operation uses GET (can be improved with POST)  

---

## 11. Future Enhancements

- Dockerize the application  
- Add authentication  
- Use PostgreSQL/MySQL  
- Convert to REST API  
- Deploy on cloud (AWS / Azure)  

---

## 12. Author

**Pradeep Reddy**  

---

## 13. License

This project is intended for educational and learning purposes.
