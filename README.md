<!-- Updated README: improved clarity, quickstart, and dev instructions -->
# AI Interview Practice

A concise, developer-friendly README for the AI Interview Practice project — a full-stack demo that uses voice-enabled AI to simulate interview sessions.

Badges: React · Node · MongoDB · Vite

Overview

- Voice-driven interview practice with real-time Socket.IO messaging.
- Backend: Node.js + Express + Mongoose.
- Frontend: React + Vite, using the Web Speech API for mic input.
- Optional: Google Generative AI (Gemini) integration for question generation.

Quick Start (Local Development)

1) Clone the repo and install dependencies

```bash
git clone <your-repo-url>
cd AI-Interviewer-main
```

2) Backend

```bash
cd backend
npm install
```

Create a `.env` in `backend/` with the following minimal values:

```env
PORT=5000
MONGODB_URI=mongodb://localhost:27017/ai-interviewer
# GEMINI_API_KEY=your_gemini_api_key   # optional
```

Start the backend (development):

```bash
npm run dev
```

3) Frontend

```bash
cd frontend
npm install
npm run dev
```

Open the site at the Vite URL (usually http://localhost:5173 or 5174).

Available NPM scripts

- Backend (`backend/package.json`):
  - `dev` — run with nodemon
  - `start` — production start
- Frontend (`frontend/package.json`):
  - `dev` — vite dev server
  - `build` — production build
  - `preview` — preview build

Environment variables

- `MONGODB_URI` — MongoDB connection string
- `PORT` — backend port
- `GEMINI_API_KEY` — (optional) key for Google Gemini API if integrated

Project structure

- backend/
  - `server.js` — Express app and Socket.IO server
  - `models/` — Mongoose models (`User.js`, `Interview.js`)
  - `.env`, `package.json`
- frontend/
  - `src/` — React app
  - `pages/` — app pages (Login, Signup, Dashboard, Interview, etc.)
  - `index.html`, `package.json`, `vite.config.js`
- README.md — this file

API Endpoints (summary)

- `POST /api/signup` — register a user
- `POST /api/login` — login (returns session/token in this demo)
- `POST /api/interview/start` — start interview
- `POST /api/interview/stop/:interviewId` — stop interview

Socket events

- `join-interview` — join room
- `user-message` — client sends message
- `ai-response` — server broadcasts AI response

Usage notes

- For best voice recognition, use Chrome on localhost or HTTPS.
- If testing locally without Gemini, the server can run with basic mock responses.

Troubleshooting

- MongoDB connection issues: verify `mongod` is running or Atlas URI is correct.
- Port conflicts: change `PORT` in `backend/.env`.
- CORS problems: ensure frontend calls the correct backend origin and server has `cors()` enabled.

Security & Production

- This demo is not production-ready. Recommended improvements before production:
  - Hash passwords (bcrypt)
  - Use JWTs and secure cookie storage
  - Input validation and rate-limiting
  - Run behind HTTPS and configure CORS strictly

Contributing

- Open an issue or submit a PR. Keep changes small and focused.

License

- MIT

Contact / Support

- If you want me to add CI scripts, Dockerfiles, or an example `.env.example`, tell me which one and I will add it.

---

Happy coding!
