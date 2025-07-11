# fastAPI-folder-structure-manager

app/
├── api/                      # FastAPI routes grouped by modules
│   ├── v1/
│   │   ├── users.py
│   │   ├── auth.py
│   │   └── __init__.py
│   └── __init__.py
│
├── core/                     # Core configs and global utilities
│   ├── config.py             # Pydantic settings
│   ├── security.py           # Password hashing, JWT, etc.
│   ├── celery_utils.py       # Optional Celery config
│   └── __init__.py
│
├── db/                       # Database connection and models
│   ├── base.py               # Base for models
│   ├── session.py            # AsyncSession or DB engine
│   ├── models/               # SQLAlchemy models
│   │   ├── user.py
│   │   └── __init__.py
│   └── __init__.py
│
├── crud/                     # Database queries (like repositories)
│   ├── user.py
│   └── __init__.py
│
├── schemas/                  # Pydantic models (request/response)
│   ├── user.py
│   ├── auth.py
│   └── __init__.py
│
├── services/                 # Business logic layer
│   ├── auth_service.py
│   └── user_service.py
│
├── tasks/                    # Background tasks / Celery jobs
│   ├── send_email.py
│   └── __init__.py
│
├── deps/                     # Common dependencies (e.g., get_current_user)
│   ├── auth.py
│   └── __init__.py
│
├── main.py                   # FastAPI app instance
├── initial_data.py           # Script to initialize DB
└── __init__.py

tests/
├── api/
├── services/
├── conftest.py
└── __init__.py

.env                         # Environment variables
requirements.txt
alembic.ini                  # Alembic config
migrations/                  # Alembic migrations
README.md
