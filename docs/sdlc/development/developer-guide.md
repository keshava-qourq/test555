# Developer Guide

> Maintained by QuorQ AI SDLC. Text between `sdlc:auto` markers is regenerated; anything outside them is yours and is kept.

<!-- sdlc:auto:start status -->
_Up to date._
<!-- sdlc:auto:end status -->

<!-- sdlc:auto:start source -->
Generated from commit `bc8e1bf` · model `claude-sonnet-5`
<!-- sdlc:auto:end source -->

<!-- sdlc:auto:start overview -->
TEST555 ("Chatbot") is a two-part generated project from the Quorq AI SDLC platform: a Vite + React 19 single-page frontend containing the approved, reviewed screens (currently running on seeded sample data, not wired to any API), and a FastAPI 0.115 backend that is a scaffold exposing only a `/health` endpoint, with SQLAlchemy models/schemas ready but no implemented business routes yet. The backend defaults to a local SQLite database so it runs standalone, while docker-compose.yml provides optional PostgreSQL and Redis services for the approved architecture (Postgres 16, AWS) once real endpoints are built.
<!-- sdlc:auto:end overview -->

<!-- sdlc:auto:start prerequisites -->
- Node.js (for Vite 6 / React 19 frontend tooling)
- Python 3.12 (per backend/Dockerfile)
- pip
- Docker and Docker Compose (optional, for Postgres/Redis services in docker-compose.yml)
<!-- sdlc:auto:end prerequisites -->

<!-- sdlc:auto:start setup -->
1. Clone the repository
2. Copy .env.example to .env and fill in any required values
3. cd frontend && npm install
4. cd backend && pip install -r requirements.txt
5. (Optional) From the repo root, run `docker-compose up -d` to start Postgres and Redis if the backend will use them instead of its default SQLite
<!-- sdlc:auto:end setup -->

<!-- sdlc:auto:start run -->
| Name | Command | Description |
|---|---|---|
| frontend dev | `cd frontend && npm run dev` | Starts the Vite dev server for the React SPA (seeded sample data) |
| frontend build | `cd frontend && npm run build` | Bundles the app with Vite (does not typecheck) |
| frontend preview | `cd frontend && npm run preview` | Serves the production build locally |
| backend dev | `cd backend && uvicorn app.main:app --reload` | Runs the FastAPI backend with auto-reload; creates SQLite tables on startup |
| compose up | `docker-compose up -d` | Starts the PostgreSQL 16 and Redis services defined in docker-compose.yml |
<!-- sdlc:auto:end run -->

<!-- sdlc:auto:start structure -->
| Path | Purpose |
|---|---|
| `.devcontainer` | VS Code devcontainer configuration |
| `.quorq` | Platform metadata (handoff.json) for the Quorq AI SDLC tooling |
| `backend` | FastAPI service: app code, tests, Dockerfile, requirements |
| `backend/app` | Application package: main.py entrypoint, database.py, models.py, schemas.py, services.py, routers/ |
| `backend/tests` | Pytest suite, split into unit/ and integration/ (integration includes test_health.py) |
| `frontend` | Vite + React SPA: approved screens, lib utilities, e2e tests, config files |
| `frontend/src` | Application source: main.tsx entrypoint, lib/ (api client, icons, ui, navigate), index.css |
| `frontend/e2e` | Playwright end-to-end specs and support helpers |
| `docker-compose.yml` | Defines Postgres and Redis services for local/approved-architecture use |
| `README.md` | Top-level run instructions for both apps |
| `.env.example` | Template for environment variables |
<!-- sdlc:auto:end structure -->

<!-- sdlc:auto:start conventions -->
- Backend organizes endpoints as one router per architecture component under app/routers/ (none implemented yet beyond main.py's /health)
- Every generated backend route is a stub returning schemas.StubResponse until implemented, keeping OpenAPI complete before behavior is written
- SQLAlchemy models inherit from the shared Base in app/database.py; models.py is imported in main.py before Base.metadata.create_all runs on startup
- Backend config (DATABASE_URL, ALLOWED_ORIGINS) is read via os.getenv with sensible local defaults (SQLite, localhost CORS origins)
- Frontend screens currently render seeded sample data rather than calling the API; src/lib/api.ts (apiFetch, API_BASE_URL, session token helpers) is the designated seam for wiring real calls later
- Frontend API base URL and secret key are injected via VITE_API_BASE_URL / VITE_API_SECRET_KEY env vars at build time, with localhost fallback
- Vitest component tests live beside the components they test under src/ (pattern src/**/*.{test,spec}.{ts,tsx}); Playwright specs live separately under e2e/
<!-- sdlc:auto:end conventions -->

<!-- sdlc:auto:start testing -->
| Name | Command | Description |
|---|---|---|
| backend test | `cd backend && pytest` | Runs the pytest suite (tests/unit, tests/integration) |
| backend lint | `cd backend && ruff check .` | Lints the backend code with ruff |
| backend format | `cd backend && ruff format .` | Formats backend code with ruff |
| frontend test | `cd frontend && npm test` | Runs Vitest component tests |
| frontend lint | `cd frontend && npm run lint` | Runs ESLint over the frontend app (CI gate) |
| frontend format | `cd frontend && npm run format` | Formats frontend code with Prettier |
| frontend typecheck | `cd frontend && npm run typecheck` | Runs tsc --noEmit (not run by build) |
| frontend e2e install | `cd frontend && npm run test:e2e:install` | Installs the Chromium browser for Playwright |
| frontend e2e | `cd frontend && npm run test:e2e` | Runs Playwright acceptance tests; boots backend (via .venv) and frontend locally unless E2E_BASE_URL is set |
<!-- sdlc:auto:end testing -->

<!-- sdlc:auto:start troubleshooting -->
| Problem | Solution |
|---|---|
| `npm run build` succeeds but the app fails elsewhere due to type errors | Run `npm run typecheck` (tsc --noEmit) separately, since build does not typecheck |
| Frontend calls to the backend are blocked by the browser (CORS) | Set ALLOWED_ORIGINS (comma-separated) as an env var for the backend, or rely on the default dev origins http://localhost:5173 / http://127.0.0.1:5173 |
| Backend fails to start because DATABASE_URL points to a database server that isn't running | Either unset DATABASE_URL to use the default local SQLite file (sqlite:///./app.db), or start Postgres via `docker-compose up -d` and set DATABASE_URL accordingly |
| `pytest` run from backend/ can't import `app` | pytest.ini sets pythonpath = . so running pytest from the backend/ directory resolves imports correctly; ensure you run it from backend/ |
| Playwright e2e tests fail to start the backend | The webServer config expects a Python venv at ../backend/.venv; create and install backend requirements there, or set E2E_BASE_URL to point at an already-running deployment |
<!-- sdlc:auto:end troubleshooting -->
