# AI Chat Bot

A full-stack AI-powered chatbot application built with React, Node.js, Express, MongoDB, Redis, and Google Generative AI.

## Features

- Real-time chat with AI using Socket.io
- User authentication with JWT
- Project management system
- WebContainer API integration for code execution
- Beautiful React UI with Tailwind CSS

## Tech Stack

### Frontend
- React 18
- Vite
- Tailwind CSS
- Socket.io Client
- React Router
- Axios
- WebContainer API

### Backend
- Node.js
- Express
- MongoDB (Mongoose)
- Redis (ioredis)
- Socket.io
- Google Generative AI (Gemini)
- JWT Authentication

## Prerequisites

Before running this project, make sure you have the following installed:

- Node.js (v16 or higher)
- MongoDB (running on localhost:27017)
- Redis (running on localhost:6379)
- Google AI API Key (from Google AI Studio)

## Installation

1. **Clone the repository** (already done)

2. **Install Backend Dependencies**
```bash
cd backend
npm install
```

3. **Install Frontend Dependencies**
```bash
cd frontend
npm install
```

## Configuration

### Backend Configuration

Create/Update `backend/.env` file with your credentials:

```env
PORT=3001
JWT_SECRET=your-secret-key-change-this-in-production-12345
MONGODB_URI=mongodb://localhost:27017/ai-chatbot
GOOGLE_AI_KEY=your-google-ai-api-key-here
REDIS_HOST=localhost
REDIS_PORT=6379
REDIS_PASSWORD=
```

**Important**: 
- Get your Google AI API key from [Google AI Studio](https://makersuite.google.com/app/apikey)
- Change the JWT_SECRET to a secure random string in production
- Make sure MongoDB is running on port 27017
- Make sure Redis is running on port 6379

### Frontend Configuration

The frontend is configured in `frontend/.env.local`:

```env
VITE_API_URL=http://localhost:3001
```

## Running the Application

### Start MongoDB
```bash
# macOS (using Homebrew)
brew services start mongodb-community

# Or run manually
mongod
```

### Start Redis
```bash
# macOS (using Homebrew)
brew services start redis

# Or run manually
redis-server
```

### Start Backend Server
```bash
cd backend
node server.js
```

The backend will run on http://localhost:3001

### Start Frontend Development Server
```bash
cd frontend
npm run dev
```

The frontend will run on http://localhost:5173

## Current Status

✅ Dependencies installed
✅ Backend server running on port 3001
✅ Frontend server running on port 5173
⚠️ **You need to configure your Google AI API Key in backend/.env**
⚠️ **Make sure MongoDB is running**
⚠️ **Make sure Redis is running**

## Usage

1. Open your browser and go to http://localhost:5173
2. Register a new account
3. Create a new project
4. Start chatting! Use `@ai` in your messages to interact with the AI assistant

## API Endpoints

- `POST /users/register` - Register a new user
- `POST /users/login` - Login user
- `GET /users/profile` - Get user profile
- `GET /users/logout` - Logout user
- `POST /projects/create` - Create a new project
- `GET /projects/all` - Get all user projects
- `GET /projects/:projectId` - Get project by ID
- `POST /ai/get-result` - Get AI response

## Socket Events

- `project-message` - Send/receive project messages
- When a message contains `@ai`, the AI will respond automatically

## Development

- Frontend runs with hot reload via Vite
- Backend needs manual restart on code changes (consider using nodemon)

## Troubleshooting

### Backend won't start
- Check if MongoDB is running: `mongosh` or `mongo`
- Check if Redis is running: `redis-cli ping` (should return "PONG")
- Check if port 3001 is available

### Frontend can't connect to backend
- Make sure backend is running on port 3001
- Check the VITE_API_URL in frontend/.env.local
- Check browser console for CORS errors

### AI not responding
- Make sure you have a valid Google AI API key
- Check backend logs for errors
- Verify the API key has proper permissions

## License

ISC

## Author

Quaiser Shahid

