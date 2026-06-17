# 🎯 Hangarin

A Django-based Task & To-Do Manager that helps users organize daily activities, manage priorities, create notes, and break large goals into smaller subtasks.

## ✨ Features

* ✅ Create and manage tasks
* 📂 Organize tasks by category and priority
* 📝 Add notes to tasks
* 📌 Break tasks into subtasks
* 📊 Track progress with status indicators
* ⚙️ Customized Django Admin
* 🎲 Generate sample data using Faker
* ☁️ Deployable to PythonAnywhere

## 🛠️ Tech Stack

* Python
* Django
* SQLite
* Faker
* Git
* PythonAnywhere

## 🚀 Run Locally

```bash
# Activate virtual environment
venv\Scripts\activate

# Install dependencies
pip install -r requirements.txt

# Navigate to project folder
cd hangarin

# Apply migrations
python manage.py migrate

# Seed sample data (optional)
python manage.py seed_hangarin_data --tasks 25

# Run the server
python manage.py runserver
```

Open:

```text
http://127.0.0.1:8000/
```

## 👨‍💻 Author

**Cyver Mahinay**

Developed for academic and educational purposes.
