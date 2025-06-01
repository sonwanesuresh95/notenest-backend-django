# NoteNest - Notes App (Django REST API)

NoteNest is a backend RESTful API for a collaborative note-taking app built using Django and Django REST Framework.

## Features Implemented

- User Registration and Login (JWT authentication)
- Create, Read, Update, Delete (CRUD) for Notes
- Notes linked to their respective users
- Private note access (users can only access their own notes)
- Project containerized using Docker

## Project Structure

```
notenest/
├── config/              # Django project settings
├── notes/               # Notes app with models, views, serializers, etc.
├── manage.py
├── requirements.txt
├── Dockerfile
├── docker-compose.yml
└── README.txt
```

## Tech Stack

- Python 3.11
- Django 5.2
- Django REST Framework
- Simple JWT (via djoser)
- PostgreSQL (via Docker Compose)
- Gunicorn (for production)
- Docker

## Setup Instructions

### Prerequisites

- Docker & Docker Compose installed

### Running the App Locally

```bash
# Build and run the containers
docker-compose up --build

# The app will be available at http://localhost:8000/
```

### Running Migrations

```bash
docker-compose exec web python manage.py migrate
```

### Creating a Superuser

```bash
docker-compose exec web python manage.py createsuperuser
```

## API Endpoints (Sample)

- `/api/auth/users/` – Register
- `/api/auth/jwt/create/` – Login
- `/api/auth/jwt/refresh/` – Token refresh
- `/api/notes/` – List/Create notes (authenticated)
- `/api/notes/<id>/` – Retrieve/Update/Delete individual note

---
