# MERN Thinkboard — Notes Application

A full-stack note-taking application built with the MERN stack (MongoDB, Express.js, React, and Node.js). It includes user authentication, protected routes, CRUD operations for notes, search and sorting, and API rate limiting.

## Features

- **Authentication:** User registration and login with JWT-based authentication.
- **Password security:** Password hashing using bcrypt.
- **Protected routes:** Authentication checks for notes-related operations.
- **Notes management:** Create, view, update, and delete notes.
- **Search and sorting:** Find notes and sort them using available options.
- **Rate limiting:** Upstash Redis-based request limiting.
- **Input validation:** Client-side and server-side validation.
- **Responsive interface:** React UI styled with Tailwind CSS and DaisyUI.
- **API integration:** Axios-based HTTP requests with authentication interceptors.

## Tech Stack

**Frontend**
- React
- Vite
- Tailwind CSS
- DaisyUI
- React Router
- Axios
- React Hot Toast

**Backend**
- Node.js
- Express.js
- MongoDB
- Mongoose
- JSON Web Tokens (`jsonwebtoken`)
- `bcryptjs`
- Upstash Redis
- CORS
- dotenv

## Project Structure

```text
MERN-Thinkboard/
├── backend/
│   ├── src/
│   │   ├── config/
│   │   ├── constants/
│   │   ├── controllers/
│   │   ├── middleware/
│   │   ├── models/
│   │   ├── routes/
│   │   ├── utils/
│   │   └── server.js
│   ├── .env.example
│   └── package.json
├── frontend/
│   ├── public/
│   ├── src/
│   └── package.json
├── .gitignore
├── package.json
└── README.md
```

## Prerequisites

- Node.js and npm
- A MongoDB database, such as MongoDB Atlas
- An Upstash Redis account for rate limiting

## Getting Started

### 1. Clone the repository

```bash
git clone https://github.com/YOUR_USERNAME/MERN-Thinkboard.git
cd MERN-Thinkboard
```

Replace `YOUR_USERNAME` with your GitHub username.

### 2. Install dependencies

From the project root:

```bash
npm run build
```

This installs the backend and frontend dependencies and builds the frontend, according to the root `package.json` scripts.

### 3. Configure environment variables

Create a `.env` file inside `backend/` by copying `.env.example`:

```bash
# Windows PowerShell
Copy-Item backend/.env.example backend/.env
```

Update `backend/.env` with your own values:

```env
MONGO_URI=your_mongodb_connection_string
JWT_SECRET=your_secure_random_secret
PORT=5001
NODE_ENV=development
UPSTASH_REDIS_REST_URL=your_upstash_redis_url
UPSTASH_REDIS_REST_TOKEN=your_upstash_redis_token
```

Generate a secure JWT secret with:

```bash
node -e "console.log(require('crypto').randomBytes(64).toString('hex'))"
```

Never commit your actual `.env` file or expose database credentials, Redis tokens, or JWT secrets.

### 4. Run the application

Open two terminals from the project root.

**Terminal 1 — Backend**

```bash
cd backend
npm run dev
```

**Terminal 2 — Frontend**

```bash
cd frontend
npm run dev
```

The development frontend normally runs at `http://localhost:5173`, and the backend uses the port configured by `PORT` (5001 in the example configuration).

A valid MongoDB connection and working Upstash Redis configuration are required for the application's full functionality.

## API Endpoints

### Authentication

| Method | Endpoint | Description |
|---|---|---|
| POST | `/api/auth/register` | Register a user |
| POST | `/api/auth/login` | Log in |
| POST | `/api/auth/logout` | Log out |

### Notes

| Method | Endpoint | Description |
|---|---|---|
| GET | `/api/notes` | Retrieve the user's notes |
| GET | `/api/notes/:id` | Retrieve a specific note |
| POST | `/api/notes` | Create a note |
| PUT | `/api/notes/:id` | Update a note |
| DELETE | `/api/notes/:id` | Delete a note |

Notes endpoints require a valid JWT. Refer to the source code for the exact request and response formats.

## Learning Goals

This project provides an opportunity to study:

- React components, hooks, and client-side routing
- REST API development with Express
- MongoDB schemas and database operations using Mongoose
- JWT authentication and password hashing
- Middleware, validation, and rate limiting
- Frontend-to-backend integration
- Environment-based configuration and deployment

## Original Project and Attribution

This repository is based on **MERN Thinkboard by Ivan Tran**.

- Original repository: https://github.com/IvanTran-2001/MERN-Thinkboard
- Original author: [Ivan Tran](https://github.com/IvanTran-2001)
- Tutorial inspiration acknowledged by the original project: [As a Programmer — MERN Stack tutorial](https://www.youtube.com/watch?v=F9gB5b4jgOI)

Please retain the original license and copyright notices. Check the included `LICENSE` file for the applicable terms before redistributing the project.

## Future Improvements

- Password reset and profile management
- Note categories and tags
- Pagination
- Rich-text editing
- Note sharing and file attachments
- Two-factor authentication

---

**Purpose:** A learning project for understanding full-stack web development with the MERN stack.
