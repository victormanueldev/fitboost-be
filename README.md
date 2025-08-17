# 💪 Fitboost App API

[![Tests](https://github.com/victormanueldev/fitboost-be/actions/workflows/tests.yml/badge.svg)](https://github.com/victormanueldev/fitboost-be/actions/workflows/tests.yml)
[![Coverage Status](https://coveralls.io/repos/github/victormanueldev/fitboost-be/badge.svg?branch=main)](https://coveralls.io/github/victormanueldev/fitboost-be?branch=main)

Backend API for the **Fitboost App**, a platform that helps users enroll in personalized training programs, manage exercise routines, and stream multimedia content.  
Built with **Python**, **Quart/Flask**, **Pydantic**, and **RQ** for background jobs.  

---

## ✨ Features

- RESTful API following [Google API Design Guidelines](https://cloud.google.com/apis/design) (simplified).
- Domain-driven design with Clean Architecture practices.
- Async-ready using [Quart](https://quart.palletsprojects.com/) (Flask-compatible).
- Input/output validation with [Pydantic](https://docs.pydantic.dev/).
- Background jobs via [RQ](https://python-rq.org/).
- Streaming support for video and multimedia.
- Testing with [pytest](https://docs.pytest.org/) and coverage reports.
- Modern development setup using [uv](https://github.com/astral-sh/uv).

---

## 📦 Installation

### Prerequisites
- Python **3.13+**
- [uv](https://github.com/astral-sh/uv) installed (`pip install uv` or [docs](https://docs.astral.sh/uv/getting-started/installation/))
- Redis (for RQ background jobs)

### Setup
```bash
# Clone repository
git clone https://github.com/victormanueldev/fitboost-be.git
cd fitboost-be

# Create virtual environment
uv venv

# Activate environment
source .venv/bin/activate  # Linux/Mac
.venv\Scripts\activate     # Windows PowerShell

# Install dependencies
uv sync
```

---

## 🚀 Running the App

```bash
# Start the development server
uv run dev

# Start background worker (RQ)
rq worker fitboost-queue
```

The API will be available at:
👉 `http://localhost:8000`

---

## 🧪 Testing

```bash
# Run tests
pytest

# Run tests with coverage
coverage run -m pytest
coverage report -m
coverage html  # Generates HTML report in htmlcov/
```

---

## 📁 Project Structure

```
trainer-app/
├── app/
│   ├── api/           # API routes (controllers)
│   ├── domain/        # Entities and business logic
│   ├── use_cases/     # Application services (use cases)
│   ├── infra/         # DB models, RQ, external services
│   ├── main.py        # Entry point
│   └── config.py      # Settings and environment config
├── tests/             # Unit and integration tests
├── requirements.txt   # Locked dependencies
├── pyproject.toml     # Project metadata
├── README.md
└── LICENSE
```

---

## 🛠️ Development

* **Linting & Formatting**: [ruff](https://docs.astral.sh/ruff/)
* **Type Checking**: [mypy](https://mypy-lang.org/)
* **Testing**: [pytest](https://pytest.org/)
* **Background Jobs**: [RQ](https://python-rq.org/)

```bash
# Linting
ruff check app tests

# Type checking
mypy app
```

---

## 📖 API Documentation

The API follows REST best practices:

* **GET** → Read resources
* **POST** → Create resources
* **PUT/PATCH** → Update resources
* **DELETE** → Remove resources

Error responses follow a consistent schema:

```json
{
  "error": {
    "code": "NOT_FOUND",
    "message": "User not found",
    "details": []
  }
}
```
