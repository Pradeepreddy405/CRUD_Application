# CRUD Application Version 02

A simple **Flask-based CRUD (Create, Read, Update, Delete) application** using SQLite for database storage. This project allows you to add, edit, and delete users through a web interface.

---

## Table of Contents

- [Project Structure](#project-structure)  
- [Features](#features)  
- [Requirements](#requirements)  
- [Setup & Installation](#setup--installation)  
- [Running the Application](#running-the-application)  
- [Dockerization](#dockerization)  
- [Usage](#usage)  
- [Screenshots](#screenshots)  

---

## Project Structure

```
CRUD_Application_Version_02/
├── instance/
├── static/css/
│   └── style.css
├── templates/
│   ├── add.html
│   ├── base.html
│   ├── edit.html
│   ├── index.html
│   └── layout.html
├── venv/
├── app.py
├── Dockerfile
├── models.py
├── requirements.txt
├── users.db
├── README.md
└── flask_crud_readme.md
```

---

## Features

- Create a new user  
- View all users  
- Edit existing users  
- Delete users  
- Uses **Flask** for the backend and **SQLite** as the database  

---

## Requirements

- Python 3.x  
- Flask  
- Flask SQLAlchemy  

Install the dependencies:

```bash
pip install -r requirements.txt
```

---

## Setup & Installation

1. Clone the repository:

```bash
git clone <repository-url>
cd CRUD_Application_Version_02
```

2. (Optional) Create a virtual environment:

```bash
python3 -m venv venv
source venv/bin/activate  # On Linux/macOS
venv\Scripts\activate     # On Windows
```

3. Install dependencies:

```bash
pip install -r requirements.txt
```

4. Initialize the database (tables are created automatically when app runs):

```bash
python app.py
```

---

## Running the Application

Start the Flask server:

```bash
python app.py
```

Open your browser and go to:

```
http://localhost:5000
```

---

## Dockerization

1. Build the Docker image:

```bash
docker build -t flask-crud-app .
```

2. Run the Docker container:

```bash
docker run -d -p 5000:5000 flask-crud-app
```

The application will now be accessible at `http://localhost:5000`.

---

## Usage

- Go to the home page to see the list of users.  
- Click **Add User** to create a new user.  
- Click **Edit** next to a user to update their name.  
- Click **Delete** to remove a user.

---

## Screenshots

*(Add your screenshots here, e.g., `index.html` view, add/edit forms, etc.)*

---

## Notes

- Database file is `users.db`.  
- `app.py` contains all routes and configuration.  
- Templates are located in the `templates/` folder.  
- Static CSS is located in `static/css/style.css`.

