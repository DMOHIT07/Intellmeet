# IntellMeet — AI-Powered Meeting & Collaboration Platform

IntellMeet is a full-stack meeting and collaboration platform designed to help teams communicate, manage meetings, track tasks, and gain useful insights from their work.

The application combines secure authentication, Google Sign-In, real-time meeting features, team collaboration, task management, analytics, and AI-powered meeting intelligence in one platform.

---

## 👨‍💻 Project Information

**Developer:** Mohit Yadav  
**Project:** IntellMeet  
**Type:** Full-Stack MERN Application  
**Frontend:** React + TypeScript + Vite  
**Backend:** Node.js + Express  
**Database:** MongoDB Atlas  

---

## 🚀 Key Features

### 🔐 Authentication

- User registration
- User login
- Google Sign-In
- JWT-based authentication
- Secure password hashing
- Protected API routes

### 📹 Meeting Management

- Create meetings
- Join meeting rooms
- Meeting access control
- Public and restricted meetings
- Invite participants
- Guest lobby
- Meeting history

### 💬 Real-Time Collaboration

- Real-time communication using Socket.io
- Meeting rooms
- Participant synchronization
- In-meeting chat
- WebRTC-based communication

### 🤖 AI Meeting Intelligence

- Meeting summaries
- Action item extraction
- Meeting insights
- Transcript processing
- AI service integration
- Fallback support when an AI API key is unavailable

### ✅ Task Management

- Create tasks
- Track task progress
- Manage task status
- Organize meeting action items
- Team task collaboration

### 📊 Analytics Dashboard

- Meeting statistics
- Task progress tracking
- Meeting activity visualization
- Status breakdown
- Interactive dashboard insights

---

## 🛠️ Technology Stack

| Category | Technology |
| --- | --- |
| Frontend | React 19 |
| Language | TypeScript |
| Build Tool | Vite |
| Backend | Node.js + Express |
| Database | MongoDB Atlas |
| ODM | Mongoose |
| Authentication | JWT + Google OAuth |
| Password Security | bcryptjs |
| Real-Time Communication | Socket.io |
| Video Communication | WebRTC |
| Client State | Zustand |
| Server State | TanStack React Query |
| AI Integration | OpenAI API |
| API Communication | Axios |
| Security | Helmet + Express Rate Limit |
| Deployment | Vercel + Cloud Backend Hosting |
| Version Control | Git + GitHub |

---

## 🏗️ Project Architecture

```text
                         ┌──────────────────────┐
                         │      User Browser    │
                         └──────────┬───────────┘
                                    │
                                    ▼
                         ┌──────────────────────┐
                         │   React + TypeScript │
                         │       Frontend       │
                         └──────────┬───────────┘
                                    │
                     REST API + Socket.io + WebRTC
                                    │
                                    ▼
                         ┌──────────────────────┐
                         │  Node.js + Express   │
                         │       Backend        │
                         └───────┬───────┬──────┘
                                 │       │
                                 ▼       ▼
                    ┌────────────────┐  ┌──────────────┐
                    │ MongoDB Atlas  │  │  AI Service  │
                    └────────────────┘  └──────────────┘
```

---

## 📁 Project Structure

```text
IntellMeet/
│
├── backend/
│   ├── src/
│   │   ├── config/
│   │   ├── controllers/
│   │   ├── middleware/
│   │   ├── models/
│   │   ├── routes/
│   │   ├── services/
│   │   └── sockets/
│   │
│   ├── .env.example
│   ├── package.json
│   └── server.js
│
├── frontend/
│   ├── public/
│   ├── src/
│   │   ├── assets/
│   │   ├── components/
│   │   ├── hooks/
│   │   ├── pages/
│   │   ├── services/
│   │   └── store/
│   │
│   ├── .env.example
│   ├── package.json
│   ├── vercel.json
│   └── vite.config.ts
│
├── docs/
├── .github/
├── .gitignore
├── DEPLOYMENT.md
├── docker-compose.yml
└── README.md
```

---

## ⚙️ Local Installation

### Prerequisites

Install the following before running the project:

- Node.js 18 or newer
- npm
- Git
- MongoDB Atlas account
- Google Cloud account for Google Sign-In

---

## 1️⃣ Clone the Repository

```bash
git clone https://github.com/DMOHIT07/Intellmeet.git
```

Enter the project folder:

```bash
cd Intellmeet
```

---

## 2️⃣ Backend Setup

Enter the backend folder:

```bash
cd backend
```

Install dependencies:

```bash
npm install
```

Create a `.env` file inside the `backend` folder.

Example:

```env
PORT=5050
MONGO_URI=your_mongodb_atlas_connection_string
JWT_SECRET=your_secure_jwt_secret
NODE_ENV=development
OPENAI_API_KEY=your_openai_api_key
```

> Never upload the real `.env` file to GitHub.

Start the backend:

```bash
npm run dev
```

The backend should run at:

```text
http://localhost:5050
```

A successful startup should show:

```text
MongoDB Connected
Server running on http://localhost:5050
```

---

## 3️⃣ Frontend Setup

Open another terminal and enter the frontend folder:

```bash
cd frontend
```

Install dependencies:

```bash
npm install
```

Create a `.env` file inside the `frontend` folder.

Example:

```env
VITE_API_URL=http://localhost:5050/api
VITE_GOOGLE_CLIENT_ID=your_google_oauth_client_id
```

Start the frontend:

```bash
npm run dev
```

Open the URL displayed by Vite, usually:

```text
http://localhost:5173
```

---

## 🔑 Environment Variables

### Backend

| Variable | Description |
| --- | --- |
| `PORT` | Backend server port |
| `MONGO_URI` | MongoDB Atlas connection string |
| `JWT_SECRET` | Secret used to sign JWT tokens |
| `NODE_ENV` | Application environment |
| `OPENAI_API_KEY` | Optional AI integration key |

### Frontend

| Variable | Description |
| --- | --- |
| `VITE_API_URL` | Backend API URL |
| `VITE_GOOGLE_CLIENT_ID` | Google OAuth Web Client ID |

---

## 🔐 Google Sign-In Setup

To enable Google authentication:

1. Create a project in Google Cloud Console.
2. Configure the Google Auth Platform.
3. Create an OAuth Client ID.
4. Select **Web application**.
5. Add the local frontend URL under Authorized JavaScript Origins:

```text
http://localhost:5173
```

6. Add the generated Client ID to:

```env
VITE_GOOGLE_CLIENT_ID=your_google_client_id
```

Restart the frontend after changing environment variables.

---

## 🗄️ MongoDB Atlas Setup

1. Create a MongoDB Atlas project.
2. Create a database cluster.
3. Create a database user.
4. Add your current IP address under Network Access.
5. Copy the MongoDB connection string.
6. Add it to the backend `.env` file:

```env
MONGO_URI=your_mongodb_connection_string
```

---

## 🔒 Security Features

IntellMeet includes:

- JWT authentication
- bcrypt password hashing
- Google OAuth authentication
- Protected backend routes
- Helmet security headers
- API rate limiting
- Environment-based secret management
- MongoDB Atlas access control

Sensitive files such as `.env` are excluded from Git using `.gitignore`.

---

## 🌐 Deployment

The application is designed for separate frontend and backend deployment.

### Frontend

The React frontend can be deployed using Vercel.

### Backend

The Node.js backend can be deployed using a compatible Node.js hosting platform.

### Production Environment Variables

For production, configure:

```env
VITE_API_URL=https://your-backend-url/api
VITE_GOOGLE_CLIENT_ID=your_google_client_id
```

The deployed frontend URL must also be added to the Google OAuth Authorized JavaScript Origins.

---

## 🧪 Features Tested

The following core features have been tested in the local development environment:

- MongoDB Atlas connection
- User registration
- User login
- JWT authentication
- Google Sign-In
- Frontend and backend API connection
- Dashboard functionality
- Meeting features
- Task management features

---

## 🔗 Project Links

**GitHub Repository:**  
https://github.com/DMOHIT07/Intellmeet

**Live Application:**  
Coming soon

---

## 🔮 Future Improvements

Possible future enhancements include:

- Improved multi-user video scalability
- Advanced AI meeting summaries
- Calendar integration
- Email notifications
- Meeting recordings
- Cloud media storage
- Mobile application support
- Advanced team analytics
- Production monitoring and logging

---

## 👨‍💻 Developer

**Mohit Yadav**

B.Tech Computer Science Graduate  
Full-Stack Development | Cyber Security | AI & Machine Learning

GitHub: https://github.com/DMOHIT07

---

## 📄 License

This project is intended for educational, learning, and demonstration purposes.

---

⭐ If you find this project useful, consider giving the repository a star.