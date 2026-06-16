# Hangarin

## Hangarin: Task & To-Do Manager

Hangarin is a Django-based task and to-do management web application that helps users organize daily activities, manage priorities, create notes, and break down large goals into smaller subtasks.

The project demonstrates Django fundamentals, database relationships, admin customization, data seeding, version control, and deployment.

---

## Features

* Create and manage tasks
* Organize tasks using categories and priorities
* Add notes to tasks
* Break down tasks into subtasks
* Track task progress using status indicators
* Customized Django Admin interface
* Generate sample data using Faker
* Deployable to PythonAnywhere

---

## Project Requirements

### Environment Setup

* Create and use a Python virtual environment
* Use Git for version control
* Deploy the application to PythonAnywhere

---

## Models

### Requirements

* Inherit a `BaseModel` containing:

  * `created_at`
  * `updated_at`
* Implement `__str__()` for all models
* Use field choices for status fields

Example:

```python
status = models.CharField(
    max_length=50,
    choices=[
        ("Pending", "Pending"),
        ("In Progress", "In Progress"),
        ("Completed", "Completed"),
    ],
    default="Pending"
)
```

---

## Data Population

### Static Data

Populate the following manually:

### Priorities

* High
* Medium
* Low
* Critical
* Optional

### Categories

* Work
* School
* Personal
* Finance
* Projects

### Fake Data Generation

Use the Faker package to generate sample records for:

* Task
* Note
* SubTask

Examples:

```python
fake.sentence(nb_words=5)

fake.paragraph(nb_sentences=3)

fake.random_element(
    elements=["Pending", "In Progress", "Completed"]
)

from django.utils import timezone

deadline = timezone.make_aware(
    fake.date_time_this_month()
)
```

---

## Django Admin Customization

### Task Admin

Display:

* Title
* Status
* Deadline
* Priority
* Category

Features:

* Filter by status
* Filter by priority
* Filter by category
* Search by title and description

### SubTask Admin

Display:

* Title
* Status
* Parent task name

Features:

* Filter by status
* Search by title

### Category Admin

Display:

* Name

Features:

* Searchable

### Priority Admin

Display:

* Name

Features:

* Searchable

### Note Admin

Display:

* Task
* Content
* Created at

Features:

* Filter by created_at
* Search by content

---

## Refactoring

Fix incorrect plural names in Django Admin using `verbose_name_plural`.

Example:

```python
class Category(models.Model):
    name = models.CharField(max_length=100)

    class Meta:
        verbose_name = "Category"
        verbose_name_plural = "Categories"

    def __str__(self):
        return self.name
```

---

## Run Locally

### 1. Activate Virtual Environment

```bash
psusenv\Scripts\activate
```

### 2. Install Dependencies

```bash
pip install -r requirements.txt
```

### 3. Navigate to Project Directory

```bash
cd hangarin
```

### 4. Apply Migrations

```bash
python manage.py makemigrations
python manage.py migrate
```

### 5. Seed Sample Data

```bash
python manage.py seed_hangarin_data --tasks 25
```

Keep existing data:

```bash
python manage.py seed_hangarin_data --tasks 25 --keep-existing
```

### 6. Start the Development Server

```bash
python manage.py runserver
```

Open:

```text
http://127.0.0.1:8000/
```

---

## Tech Stack

* Python
* Django
* SQLite
* Faker
* Git
* PythonAnywhere
