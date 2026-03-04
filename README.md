
# Zerodha — Fullstack Trading Dashboard (Learning Project)

This repository contains a small fullstack trading-dashboard project inspired by Zerodha. It includes:

- `backend/` — Node.js + Express API using MongoDB (Mongoose). Provides holdings, orders, and positions models and endpoints.
- `dashboard/` — React dashboard app (Material UI + charts) for authenticated users and internal views.
- `frontend/` — Marketing / landing React app (public site, signup, info pages).

Quick summary:

- Backend listens on port `3002` and reads `MONGO_URL` from `backend/.env`.
- Dashboard app served on port `3000` (or via Docker) and uses the backend API.
- Frontend marketing site served on port `3001` in the compose setup.

Local development
1. Install Node.js (v16+ or v18+) and npm.
2. Set your MongoDB connection string in `backend/.env` as `MONGO_URL=...` (use MongoDB Atlas or a local MongoDB).
3. Open three terminals and run each service:

```powershell
# Backend
cd backend
npm install
npm start

# Dashboard
cd ../dashboard
npm install
npm start

# Frontend
cd ../frontend
npm install
npm start
```

Docker (recommended for consistent setup)

From the repository root (where `docker-compose.yml` is located):

```powershell
# Build and run all services (backend will read backend/.env)
docker compose up --build

# Run in background
docker compose up -d --build
```

Notes
- Keep `backend/.env` out of version control (already ignored in `.gitignore`).
- If you don't have MongoDB locally, use MongoDB Atlas and paste the connection string into `backend/.env`.
- To use a local MongoDB container instead, I can add a `mongo` service to `docker-compose.yml` and update `MONGO_URL` to `mongodb://mongo:27017/zerodha`.

Want me to add a GitHub Actions workflow or a local `mongo` service in `docker-compose.yml`?
