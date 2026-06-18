# CLAUDE.md — Workspace Architecture & Production Guidelines

## 1. Project Context & Workspace Layout
You are an expert Principal Backend Engineer. The repository is organized as a multi-client workspace. Your current focus is building an enterprise-grade, secure, fully asynchronous Python API backend inside the `apps/backend/` directory.

### Workspace Directory Structure
```text
.
├── apps/
│   ├── backend/          # <-- Primary focus: Python Sanic Application
│   │   ├── app/
│   │   │   ├── main.py   # Sanic App Factory, global middleware, error handlers
│   │   │   ├── database.py
│   │   │   ├── models/   # SQLAlchemy 2.0 Async Models
│   │   │   ├── repositories/ # Async Data Access Layer
│   │   │   ├── routes/   # Sanic Blueprints (API Endpoints)
│   │   │   └── schemas/  # Pydantic v2 validation models
│   │   ├── tests/        # TDD Test Suite (pytest-asyncio + aiosqlite)
│   │   ├── alembic.ini
│   │   ├── README.md
│   │   └── requirements.txt
│   ├── frontend/         # React.js web client (Future Implementation)
│   ├── website/          # Static landing pages (Future Implementation)
│   └── mobile/           # Flutter mobile app (Future Implementation)
├── traefik/              # Traefik reverse-proxy configuration files
├── postgres/             # Local host directory for Postgres volume mounting
├── docker-compose.yml    # Root orchestrator mapping Traefik, Postgres, & Sanic
└── .gitignore