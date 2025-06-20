#  Django Healthcare Backend

This is a secure RESTful API backend for a healthcare application built using **Django**, **Django REST Framework**, **PostgreSQL**, and **JWT authentication**.

##  Features

- User registration and login with **JWT**
- Full CRUD operations for:
  - Patients
  - Doctors
  - Patient-Doctor mappings
- Secure endpoints (only authenticated users can modify data)
- Clean RESTful architecture using Django ORM
- Environment-based configuration for sensitive settings

---

##  Tech Stack

- Python 3.10+
- Django 4.x
- Django REST Framework
- djangorestframework-simplejwt
- PostgreSQL
- Postman (for API testing)

---

##  Setup Instructions

### 1. Clone the project
```bash
git clone https://github.com/your-username/healthcare-backend.git
cd healthcare-backend
````

### 2. Create and activate a virtual environment

```bash
python -m venv venv
venv\Scripts\activate
```

### 3. Install dependencies

```bash
pip install -r requirements.txt
```

### 4. Configure environment variables

Create a `.env` file in the root and set:

```
SECRET_KEY=your_secret_key
DEBUG=True
DATABASE_NAME=your_db_name
DATABASE_USER=your_db_user
DATABASE_PASSWORD=your_db_password
DATABASE_HOST=localhost
DATABASE_PORT=5432
```

### 5. Run migrations

```bash
python manage.py makemigrations
python manage.py migrate
```

### 6. Create a superuser (optional)

```bash
python manage.py createsuperuser
```

### 7. Start the development server

```bash
python manage.py runserver
```

---

##  API Endpoints

###  Auth

| Method | Endpoint              | Description       |
| ------ | --------------------- | ----------------- |
| POST   | `/api/auth/register/` | Register new user |
| POST   | `/api/auth/login/`    | Obtain JWT token  |

###  Patients

| Method | Endpoint              | Description         |
| ------ | --------------------- | ------------------- |
| POST   | `/api/patients/`      | Add new patient     |
| GET    | `/api/patients/`      | List all patients   |
| GET    | `/api/patients/<id>/` | Get patient details |
| PUT    | `/api/patients/<id>/` | Update patient      |
| DELETE | `/api/patients/<id>/` | Delete patient      |

###  Doctors

| Method | Endpoint             | Description        |
| ------ | -------------------- | ------------------ |
| POST   | `/api/doctors/`      | Add new doctor     |
| GET    | `/api/doctors/`      | List all doctors   |
| GET    | `/api/doctors/<id>/` | Get doctor details |
| PUT    | `/api/doctors/<id>/` | Update doctor      |
| DELETE | `/api/doctors/<id>/` | Delete doctor      |

###  Mappings

| Method | Endpoint                      | Description                   |
| ------ | ----------------------------- | ----------------------------- |
| POST   | `/api/mappings/`              | Assign doctor to patient      |
| GET    | `/api/mappings/`              | Get all mappings              |
| GET    | `/api/mappings/<patient_id>/` | Get mappings for a patient    |
| DELETE | `/api/mappings/delete/<id>/`  | Remove doctor-patient mapping |

---

##  Project Structure

```
healthcare/
├── myapp/
│   ├── models.py
│   ├── views.py
│   ├── serializers.py
│   ├── urls.py
│   └── ...
├── healthcare/
│   └── settings.py
├── manage.py
└── .env
```

##  Postman Testing
https://www.postman.com/maintenance-cosmologist-12845390/workspace/anirudh/collection/31320871-379b38eb-f7f0-4b43-adbe-d8a74c3f49bf?action=share&creator=31320871

