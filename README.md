# Mini CRM (Backend)

![CI](https://github.com/arki-s/mini-crm-api/actions/workflows/ci.yml/badge.svg)

A small CRM backend API built with Django REST Framework for learning and practice.

## Purpose

This project is a small CRM backend built to practice a real-world backend stack
(Django REST Framework, JWT authentication, PostgreSQL)
used in my current work.

The focus is not feature completeness, but:

- API design and responsibility boundaries
- Data modeling and query patterns
- Authentication and authorization flow
- Frontend–backend integration via REST APIs

This repository is intentionally separated from the frontend to mirror
a real production setup.

## Planned Features (MVP)

- JWT-based authentication
- Deal CRUD API
- Deal list with filters
  - status (multiple)
  - keyword search (deal name / client name)
  - date range (created / updated)
- Activity timeline per deal
- Create and update activities
- Owner-based data access control

## API Overview (Planned)

### Auth

- `POST /auth/login`
- `POST /auth/refresh`

### Deals

- `GET /deals`
- `POST /deals`
- `GET /deals/{id}`
- `PATCH /deals/{id}`
- `DELETE /deals/{id}` (optional)

### Activities

- `GET /deals/{id}/activities`
- `POST /deals/{id}/activities`
- `PATCH /activities/{id}`
- `DELETE /activities/{id}`

## Tech Stack

- Python
- Django
- Django REST Framework
- JWT (djangorestframework-simplejwt)
- PostgreSQL (production / CI)
- SQLite (local development)
- Ruff (linting)
- GitHub Actions (CI)

## Project Structure

```text
mini-crm-api/
├── config/          # Django project settings
├── crm/             # Core CRM app (models, views, serializers)
├── requirements.txt
├── pyproject.toml   # Tooling configuration (ruff, etc.)
└── manage.py
```

## Development Setup

python -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
python manage.py migrate
python manage.py runserver

## Status

🚧 Work in Progress

- Django + DRF project initialized
- Health check endpoint implemented
- CI setup (lint + test)
- Core models and APIs under development
