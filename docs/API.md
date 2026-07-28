# API Reference

Base URL: `http://localhost:8000`

## Endpoints

### Health

`GET /health` — Returns service status and dependency health.

### Authentication

`POST /auth/register` — Create a new account.
`POST /auth/login` — Obtain a JWT access token.

### Profiles

`POST /profiles` — Create a profile with resume and GitHub username.
<!-- REPRODUCTION NOTE (Issue #89): No request body schema documented.
Actual endpoint (api/routes/profiles.py, create_profile_endpoint) expects
multipart/form-data with:
  - github_username (optional, string, max 255)
  - portfolio_url (optional, string, max 500)
  - resume_file (optional, file — must be application/pdf, text/markdown,
    or text/plain, else 422)
This will be replaced with the full documented schema below. -->
`GET /profiles/{profile_id}` — Retrieve a profile.
`DELETE /profiles/{profile_id}` — Delete a profile and associated data.

### Reviews

`POST /reviews` — Request a new portfolio review for a profile.
`GET /reviews/{review_id}` — Retrieve a completed review.
`GET /reviews` — List reviews for the authenticated user (paginated).

## Interactive Docs

When the API is running, visit:
- **Swagger UI:** http://localhost:8000/docs
- **ReDoc:** http://localhost:8000/redoc
