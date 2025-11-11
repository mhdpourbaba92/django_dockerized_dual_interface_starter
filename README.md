# Django Dockerized Dual Interface Starter  
📦 A starter template for Django projects with Docker, PostgreSQL, Virtualenv and Debug Toolbar — ready for dual‑interface (API + Web) development.

## 🛠 Tech Stack  

| Tool | Description |
|------|--------------|
| ![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white) | Programming language |
| ![pip](https://img.shields.io/badge/pip-3776AB?style=for-the-badge&logo=pypi&logoColor=white) | Python package manager |
| ![Django](https://img.shields.io/badge/Django-092E20?style=for-the-badge&logo=django&logoColor=white) | Python web framework |
| ![Django REST Framework](https://img.shields.io/badge/DRF-E03C31?style=for-the-badge&logo=django&logoColor=white) | REST API toolkit for Django |
| ![Docker](https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white) | Containerization & environment setup |
| ![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=for-the-badge&logo=postgresql&logoColor=white) | Relational database |
| ![Virtualenv](https://img.shields.io/badge/Virtualenv-14354C?style=for-the-badge&logo=python&logoColor=white) | Local virtual environment |
| ![Django Debug Toolbar](https://img.shields.io/badge/Django_Debug_Toolbar-092E20?style=for-the-badge&logo=python&logoColor=white) | Development inspection tool |


## 🚀 Why this starter?  
When starting a full‑stack Django project (for example a project with both a web interface and a REST API), you don’t want to waste time on boilerplate setup.  
This starter gives you:  
- Django configured and ready.  
- PostgreSQL as the database, running in Docker.  
- Docker & Docker Compose setup for easy, consistent environment.  
- Virtualenv support for running the project locally without Docker.
- Django Debug Toolbar enabled in development so you can debug and inspect quickly.  
- Project structure aimed at dual interface (web + API) from day one.

## 🧱 Project Structure  
```text
.
├── config/                 # Django project configuration (settings, wsgi/asgi, etc.)
├── templates/              # Shared templates (including REST‑framework UI, etc.)
├── .dockerignore
├── .gitignore
├── Dockerfile
├── docker‑compose.yaml
├── manage.py
├── requirements.txt
└── README.md
```

*(Adjust paths and names if you have additional apps/folders.)*

## ⚙️ Quick Start  
1. Clone the repository:  
   ```bash
   git clone https://github.com/mhdpourbaba92/django_dockerized_dual_interface_starter.git
   cd django_dockerized_dual_interface_starter
   ```

2. Create virtual environment and active it.
    ```bash
   python -m venv venv
   source venv/bin/activate  # On Linux/Mac
   # OR
   venv/Scripts/activate  # On Windows
   ```


3. Install dependencies.
    ```bash
   pip install -r requirements.txt
   ```

4. Create (or copy) an `.env` file and set environment variables, for example:  
   ```env
   ENVIRONMENT='development'
   SECRET_KEY=your_secret_key_here
   POSTGRES_DB=app_db
   POSTGRES_USER=app_user
   POSTGRES_PASSWORD=app_password
   POSTGRES_HOST=db
   POSTGRES_PORT=5432
   ```

5. Build and run using Docker Compose:  
   ```bash
   docker compose up --build
   ```

6. Open in browser:  
   Visit `http://localhost:8000` (or the port you configured). 

## 🧪 Development & Testing  
To get inside the Django container:  
```bash
docker compose exec web bash
```

To run Django management commands (migrations, createsuperuser, etc):  
```bash
docker compose exec web python manage.py migrate
docker compose exec web python manage.py createsuperuser
```

To run tests:  
```bash
docker compose exec web python manage.py test
```

## 🎯 Tips for Dual Interface (Web + API)  
- Separate apps for web views (HTML templates) and API views (using Django REST framework) helps maintain clarity.  
- Use the `templates/rest_framework/` directory for DRF’s browsable API UI customization.  
- In production, disable Debug Toolbar and set `DEBUG=False`, configure allowed hosts, secure settings.  
- Consider adding a custom manager or router for API endpoints to clearly separate “web” and “api” URLs.

## 📝 Note  
This repository is **not** a full application — it's a **starter template** meant to speed up project setup. Extend it, build your apps, define your models/views/serializers and you’re ready for production‑grade development.

## 🙋‍♂️ Author  
Mehdi Pourbaba – [GitHub/mhdpourbaba92](https://github.com/mhdpourbaba92)
