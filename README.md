# FastAPI Enterprise Boilerplate (Architecture)

A scalable, modular, production-ready **FastAPI** backend architecture designed for a Enterprise-scale application. This architecture emphasizes maintainability, separation of concerns, extensibility, and high performance.

---

## 🚀 Tech Stack

- **FastAPI** – Modern, async web framework
- **PostgreSQL** – Production-grade relational DB
- **SQLAlchemy 2.x** – Async ORM
- **Alembic** – Database migrations
- **Pydantic v2** – Data validation and serialization
- **Celery** + **Redis** – Background tasks and scheduling
- **Docker** – Containerized deployment
- **Pytest** – Testing framework

---

## 🗂️ Folder Structure

```bash
app/
├── api/                      # FastAPI route declarations (modular, versioned)
│   └── v1/
│       ├── users.py          # /users endpoints
│       ├── auth.py           # /auth endpoints
│       └── __init__.py
│
├── core/                     # Application-wide core settings and utilities
│   ├── config.py             # Environment config (Pydantic BaseSettings)
│   ├── security.py           # Password hashing, JWT, OAuth2
│   ├── celery_utils.py       # Celery configuration
│   └── __init__.py
│
├── db/                       # Database management and model base
│   ├── session.py            # DB session and engine
│   ├── base.py               # Declarative base class
│   └── models/               # All SQLAlchemy models
│       ├── user.py
│       └── __init__.py
│
├── crud/                     # Data access layer: raw DB operations (repositories)
│   ├── user.py
│   └── __init__.py
│
├── schemas/                  # Pydantic request/response models
│   ├── user.py
│   ├── auth.py
│   └── __init__.py
│
├── services/                 # Business logic layer (service classes/functions)
│   ├── auth_service.py
│   └── user_service.py
│
├── deps/                     # FastAPI dependencies (e.g. auth, DB access)
│   ├── auth.py
│   └── __init__.py
│
├── tasks/                    # Background workers (Celery or asyncio)
│   ├── send_email.py
│   └── __init__.py
│
├── main.py                   # FastAPI application startup
├── initial_data.py           # Seed script to bootstrap DB with users, roles
└── __init__.py               # Makes app importable as a package

tests/
├── api/                      # API endpoint tests
├── services/                 # Unit tests for business logic
├── conftest.py               # Fixtures and shared test setup
└── __init__.py

.env                          # Environment variables
alembic.ini                   # Alembic DB migration config
migrations/                   # Auto-generated migration files
requirements.txt              # Python dependencies
README.md
