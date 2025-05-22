# NoteNest - Django Backend (Feature 3: Token Authentication)

A simple collaborative notes app backend built using Django REST Framework.

This project implements essential backend features one-by-one. Current feature status:

## ✅ Implemented Features

1. CRUD with all HTTP methods  
2. Database integration with PostgreSQL  
3. Authentication: Token Authentication (DRF built-in)

---

## 🔧 Tech Stack

- Python 3  
- Django 4  
- Django REST Framework  
- PostgreSQL  
- Docker & Docker Compose

---

## 🚀 Getting Started

### 1. Clone the repository

```bash
git clone https://github.com/your-username/notenest-django.git
cd notenest-django
```

### 2. Build and start containers

```bash
sudo docker compose up --build
```

### 3. Run migrations and create superuser

```bash
sudo docker compose exec web python manage.py migrate
sudo docker compose exec web python manage.py createsuperuser
```

---

## 🗃️ API Overview

### Base URL

```
http://localhost:8000/api/
```

---

## 🔐 Authentication - Token Auth (DRF)

### Step 1: Obtain Token

**POST** to `/api/token-auth/` with:

```json
{
  "username": "your_superuser",
  "password": "your_password"
}
```

### Response:

```json
{
  "token": "abc123..."
}
```

---

### Step 2: Use Token for Authenticated Requests

Add the following header to any API request:

```
Authorization: Token your_token_here
```

---

### Example CRUD Endpoints (Authenticated)

| Method | Endpoint            | Description        |
|--------|---------------------|--------------------|
| GET    | `/api/notes/`       | List all notes     |
| POST   | `/api/notes/`       | Create a new note  |
| GET    | `/api/notes/<id>/`  | Get a single note  |
| PUT    | `/api/notes/<id>/`  | Update a note      |
| PATCH  | `/api/notes/<id>/`  | Partially update   |
| DELETE | `/api/notes/<id>/`  | Delete a note      |

> All above endpoints require authentication.

---

## 🧪 Testing

Access browsable DRF API:  
[http://localhost:8000/api/](http://localhost:8000/api/)

Use Hoppscotch or Postman to test authenticated endpoints with `Authorization: Token <your_token>`.

---

## 📂 Folder Structure (Simplified)

```
notenest/
├── notes/               # App with models, views, serializers
├── notenest/            # Project settings and root urls
├── manage.py
├── requirements.txt
├── docker-compose.yml
├── Dockerfile
```

---

## 🧱 Next Feature

- JSON Web Token (JWT) Authentication  
- OAuth2 (Google/GitHub login)

---

## 📜 License

MIT License
