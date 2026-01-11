# Flask Single-Tier CRUD Application

This is a simple **Flask-based Single-Tier CRUD (Create, Read, Update, Delete) application** using **SQLite** as the database and **SQLAlchemy ORM**.
The application allows users to add, view, edit, and delete user records.

---

## Features

- Create new users
- View all users
- Edit existing users
- Delete users
- SQLite database (local file-based DB)
- SQLAlchemy ORM
- Jinja2 templates
- Single-tier architecture

---

## Tech Stack

- Python
- Flask
- Flask-SQLAlchemy
- SQLite
- HTML (Jinja2)

---

## Project Structure

flask-crud/
├── app.py
├── models.py
├── users.db
├── templates/
│   ├── base.html
│   ├── index.html
│   ├── add.html
│   └── edit.html
└── README.md

---

## Prerequisites

- Python 3.8+
- pip

---

## Installation & Setup

### Clone repository
git clone YOUR_REPO_URL
cd flask-crud

### Create virtual environment (optional)
python -m venv venv
venv\Scripts\activate

### Install dependencies
pip install flask flask-sqlalchemy

---

## Run Application

python app.py

Open browser:
http://127.0.0.1:5000/

---

## Database Details

- Database: SQLite
- File: users.db
- Auto-created when app runs
- Table: user (id, name)

---

## CRUD Routes

| Action | URL | Method |
|------|----|-------|
| View | / | GET |
| Add | /add | GET, POST |
| Edit | /edit/<id> | GET, POST |
| Delete | /delete/<id> | GET |

---

## Notes

- Development project
- Debug enabled
- SQLite not for production

---

## Author

Pradeep Reddy

---

## License

Educational / learning purpose only
