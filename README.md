# 🚀 Task Manager API

A production-ready Task Management REST API built using Django, Docker, and PostgreSQL.

This project demonstrates backend development and DevOps best practices including containerization, environment-based configuration, JWT authentication, and API documentation.

---

## 📌 Project Overview

The Task Manager API allows authenticated users to:

- Register and log in using JWT authentication
- Create, read, update, and delete tasks
- Access only their own tasks (user-level data isolation)
- Interact with documented API endpoints via Swagger UI

The application is fully containerized using Docker and runs with PostgreSQL as the database.

---

## 🛠 Tech Stack

- Python 3.12
- Django
- Django REST Framework
- PostgreSQL
- Docker
- Docker Compose
- Gunicorn
- drf-yasg (Swagger Documentation)

---

## 📂 Project Structure

```
task-manager/
│
├── config/                # Django project configuration
├── tasks/                 # Task app
├── Dockerfile
├── docker-compose.yml
├── requirements.txt
├── .env                   # Environment variables (not committed)
└── README.md
```

---

## 🔐 Features

- JWT-based Authentication
- Secure REST API
- PostgreSQL database integration
- Dockerized multi-container setup
- Environment variable configuration
- Interactive Swagger API documentation
- Production-ready Gunicorn server

---

## ⚙️ Setup Instructions

### 1️⃣ Clone the Repository

```bash
git clone https://github.com/YOUR_USERNAME/task-manager-api.git
cd task-manager-api
```

---

### 2️⃣ Create Environment File

Create a `.env` file in the root directory:

```
POSTGRES_DB=taskdb
POSTGRES_USER=taskuser
POSTGRES_PASSWORD=taskpass
POSTGRES_HOST=db
POSTGRES_PORT=5432
```

---

### 3️⃣ Build and Start Containers

```bash
docker-compose up --build
```

---

### 4️⃣ Run Migrations

In a new terminal:

```bash
docker-compose exec web python manage.py migrate
```

---

### 5️⃣ Create Superuser

```bash
docker-compose exec web python manage.py createsuperuser
```

---

## 🌐 Access the Application

- Admin Panel:  
  http://localhost:8000/admin/

- Swagger Documentation:  
  http://localhost:8000/swagger/

- API Base URL:  
  http://localhost:8000/api/

---

## 🔑 Authentication

### Obtain JWT Token

**POST** `/api/token/`

```json
{
  "username": "yourusername",
  "password": "yourpassword"
}
```

Response:

```json
{
  "refresh": "your_refresh_token",
  "access": "your_access_token"
}
```

Use the access token in request headers:

```
Authorization: Bearer your_access_token
```

---

## 📋 Task API Endpoints

| Method | Endpoint | Description |
|--------|----------|------------|
| GET | /api/tasks/ | List user tasks |
| POST | /api/tasks/ | Create new task |
| GET | /api/tasks/{id}/ | Retrieve task |
| PUT | /api/tasks/{id}/ | Update task |
| DELETE | /api/tasks/{id}/ | Delete task |

---

## 🐳 Docker Architecture

The application runs using two containers:

1. **web** – Django application served with Gunicorn
2. **db** – PostgreSQL database

Docker Compose manages networking between services and ensures proper startup order.

---

## 🧠 What This Project Demonstrates

- REST API design
- JWT authentication implementation
- Database integration with PostgreSQL
- Containerized application deployment
- Environment-based configuration
- Production-style application setup

This project reflects practical backend and DevOps engineering skills.

---

## 🚀 Future Improvements

- CI/CD with GitHub Actions
- AWS EC2 deployment
- Nginx reverse proxy
- Redis & Celery integration
- API rate limiting
- Logging & monitoring setup

---

## 👨‍💻 Author

**Abin Nazer**  
DevOps & Backend Developer  

---

## 📄 License

This project is for educational and portfolio purposes.
