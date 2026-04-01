# Project Guidelines

## Overview

Mergington High School Activities — a FastAPI application for browsing and signing up for extracurricular activities. Teachers manage enrollments via authenticated endpoints.

## Tech Stack

- **Backend:** Python 3 with FastAPI + Uvicorn
- **Database:** MongoDB (`mergington_high` database)
- **Frontend:** Vanilla HTML/CSS/JS served as static files
- **Auth:** Argon2 password hashing via `argon2-cffi`

## Architecture

- `src/app.py` — Application entry point, mounts static files and includes routers
- `src/backend/database.py` — MongoDB connection and collection references
- `src/backend/routers/` — Modular API routers (`activities.py`, `auth.py`)
- `src/static/` — Frontend assets (HTML, CSS, JS)

## Code Style

- Use type hints for all Python function signatures
- Raise `HTTPException` with appropriate status codes for error responses
- Keep routers thin — business logic should remain close to the data layer
- Frontend uses vanilla JS with event delegation; no frameworks

## Build and Test

- Install dependencies: `pip install -r requirements.txt`
- Run the app: `python src/app.py` (serves on `http://localhost:8000`)
- API docs available at `http://localhost:8000/docs`

## Conventions

- API endpoints follow RESTful patterns with query parameters for filtering
- Teacher authentication is required for student enrollment operations
- Activity data uses structured `schedule_details` with day/time arrays
- CSS uses custom properties defined in `:root` for theming

## Security

- Validate input sanitization practices.
- Search for risks that might expose user data.
- Prefer loading configuration and content from the database instead of hard coded content. If absolutely necessary, load it from environment variables or a non-committed config file.

## Code Quality

- Use consistent naming conventions.
- Try to reduce code duplication.
- Prefer maintainability and readability over optimization.
- If a method is used a lot, try to optimize it for performance.
- Prefer explicit error handling over silent failures.
