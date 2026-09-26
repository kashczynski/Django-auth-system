# Django REST Auth & Task Management API

A robust RESTful API built with Django, Django REST Framework (DRF), and PostgreSQL. Features JSON Web Token (JWT) authentication, password reset workflows, Google/Facebook OAuth integration, and complete task management endpoints.

---

## Features

- **User Authentication:** Registration, login, token refresh via SimpleJWT (`rest_framework_simplejwt`).
- **OAuth 2.0 Integration:** Social sign-in with Google and Facebook using `django-allauth` and `dj-rest-auth`.
- **Password Management:** Password reset request and confirmation endpoints via base64 email tokens.
- **Task Management:** Full CRUD operations for user-specific tasks (create, read, update, delete).
- **Database:** PostgreSQL integration for relational data management.

---

## Tech Stack

- **Backend:** Python 3.14+, Django 5.x
- **API Framework:** Django REST Framework (DRF)
- **Authentication:** SimpleJWT, `dj-rest-auth`, `django-allauth`
- **Database:** PostgreSQL
- **Environment Management:** `python-dotenv`

---

## Project Setup Instructions

### 1. Prerequisites

Ensure you have installed:
- [Python 3.10+](https://www.python.org/)
- [PostgreSQL](https://www.postgresql.org/)
- [Git](https://git-scm.com/)

---

### 2. Environment Setup

Clone the repository and navigate into the project root:

```bash
git clone [https://github.com/YOUR_USERNAME/django_auth_tasks.git](https://github.com/YOUR_USERNAME/django_auth_tasks.git)
cd django_auth_tasks

Create and activate a virtual environment:

Bash
# Windows
python -m venv venv
.\venv\Scripts\activate

# macOS/Linux
python3 -m venv venv
source venv/bin/activate
Install the dependencies:

Bash
pip install -r requirements.txt
3. Environment Variables Configuration
Create a .env file in the root directory and define the following variables:

Code snippet
SECRET_KEY=your-django-secret-key
DEBUG=True

# Database Configuration
DB_NAME=auth_tasks_db
DB_USER=postgres
DB_PASSWORD=your_postgres_password
DB_HOST=localhost
DB_PORT=5432

4. Database Setup & Migrations

Create your PostgreSQL database (auth_tasks_db) using psql or pgAdmin, then execute:

Bash

python manage.py migrate
Optionally, create a superuser for Django Admin access:

Bash
python manage.py createsuperuser

5. Running the Application
Start the development server:

Bash
python manage.py runserver
The API will be available at http://127.0.0.1:8000/.

API Endpoints Overview
Authentication (/api/auth/)
Method	Endpoint	Description
POST	/api/auth/register/	Register a new user
POST	/api/auth/login/	Obtain JWT Access and Refresh tokens
POST	/api/auth/token/refresh/	Refresh expired Access Token
POST	/api/auth/password-reset/	Request password reset token
POST	/api/auth/password-reset-confirm/	Confirm password reset
POST	/api/auth/google/	Google OAuth login
POST	/api/auth/facebook/	Facebook OAuth login
Tasks (/api/tasks/)
Method	Endpoint	Description
GET	/api/tasks/	List user's tasks
POST	/api/tasks/	Create a new task
GET	/api/tasks/{id}/	Retrieve task details
PUT	/api/tasks/{id}/	Update task
DELETE	/api/tasks/{id}/	Delete task
License
This project is licensed under the MIT License.
