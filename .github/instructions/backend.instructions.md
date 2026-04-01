---
applyTo: "backend/**/*,*.py"
---

## Backend Guidelines

- All API endpoints must be defined in the `routers` folder.
- Load example database content from the `database.py` file.
- Error handling is only logged on the server. Do not propagate to the frontend.
- Ensure all APIs are explained in the documentation.
- Verify changes in the backend are reflected in the frontend (`src/static/**`). If possible breaking changes are found, mention them to the developer.
- Use type hints for all function signatures and return types.
- Raise `HTTPException` with appropriate status codes for error responses.
- Keep routers thin — business logic should remain close to the data layer.
- Use Argon2 for password hashing via `argon2-cffi`; never store plaintext passwords.
- Prefer loading configuration from the database or environment variables over hard-coded values.
- Validate and sanitize all user inputs at API boundaries.
