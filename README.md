# 🚀 AI Chatbot Application (Real-Time)

A full-stack real-time AI chatbot application built using modern web technologies. This project integrates the **Gemini AI model** to generate intelligent and context-aware responses, providing a smooth conversational experience.

---

## 🧠 Tech Stack

### 🔹 Backend

- Node.js
- Express.js
- Socket.IO
- Gemini AI API

### 🔹 Frontend

- React.js
- Socket.IO Client
- CSS / Tailwind (optional)

---

## ⚡ Features

- 💬 Real-time chat using WebSockets (Socket.IO)
- 🤖 AI-powered responses using Gemini model
- ⚡ Instant message delivery (no page reloads)
- 🎯 Clean and responsive UI
- 🔄 Bi-directional communication (client ↔ server)
- 🧩 Scalable and modular architecture

---

## 📂 Project Structure

```
backend/
  ├── src/
  │   ├── app.js          → Express application
  │   └── service/
  │       └── ai.service.js → AI response generation (Gemini)
  ├── public/             → Compiled frontend assets
  ├── server.js           → Socket.IO server & main entry point
  └── package.json

frontend/
  ├── src/
  │   ├── App.jsx         → Main chat component
  │   ├── App.css         → Component styles
  │   └── main.jsx        → React entry point
  ├── vite.config.js      → Vite configuration
  └── package.json
```

---

## 🛠️ Installation & Setup

### 1️⃣ Clone the repository

```bash
git clone https://github.com/PuneetVerma07/Chat-Bot
cd Chat-Bot
```

### 2️⃣ Setup Backend

```bash
cd backend
npm install
```

Create a `.env` file in the backend directory and add:

```
GEMINI_API_KEY=your_api_key_here
```

Start the backend server (runs on port 3000):

```bash
npm start
```

The backend serves the frontend from the `public/` directory and handles all Socket.IO connections.

---

### 3️⃣ Setup Frontend

```bash
cd frontend
npm install
npm run dev
```

The frontend will be available at `http://localhost:5173` during development. The app will connect to the backend at `http://localhost:3000` (for local development) or the production URL when deployed.

---

## 🔌 How It Works

### Real-Time Communication Flow

1. **User sends message**: User types a message in the React component and hits send
2. **Emit to backend**: Frontend emits the message via Socket.IO using the `ai-message` event
3. **Store in history**: Backend adds the user message to `chatHistory` array (maintains conversation context)
4. **Generate response**: Backend calls `generateResponse()` from `ai.service.js` with the entire chat history
5. **Store AI response**: AI response is added to `chatHistory` for future context
6. **Send back to client**: Backend emits the response via Socket.IO using the `ai-message-response` event
7. **Display in UI**: Frontend receives the response and displays it with a timestamp

### Key Features

- **Chat History Maintained**: The server keeps the full conversation context to provide better AI responses
- **Real-Time Updates**: No page reloads needed; messages appear instantly via WebSockets
- **Multi-turn Conversations**: AI understands the complete conversation history for contextual responses
- **User/AI Distinction**: Messages are clearly marked as user or AI for visual distinction

---

## 📡 Socket.IO Events

### Frontend → Backend

- **`ai-message`**: Sends user message text to the backend

### Backend → Frontend

- **`ai-message-response`**: Sends AI-generated response back to frontend

---

## 🎨 UI Features

- **Message Container**: Clean, scrollable chat interface
- **Timestamps**: Each message shows when it was sent
- **Empty State**: "Start a conversation..." message when no messages exist
- **Responsive Design**: Form input with send button at the bottom
- **Visual Separation**: User messages and AI responses are visually distinct

---

## 🔐 Environment Variables

Create a `.env` file in the `backend/` directory:

```env
GEMINI_API_KEY=your_gemini_api_key_here
```

Get your Gemini API key from [Google AI Studio](https://aistudio.google.com)

---

## 📸 Demo

Add a screenshot of the chatbot UI here:

```
![Chatbot UI](./assets/chatbot.png)
```

---

## 🌐 Deployment

### Deploying Backend (on Render)

1. Push your code to GitHub
2. Go to [Render.com](https://render.com)
3. Create a new Web Service
4. Connect your GitHub repo
5. Set the start command: `npm start`
6. Add environment variables (GEMINI_API_KEY)
7. Deploy

### Deploying Frontend (on Vercel/Netlify)

1. Build the frontend: `npm run build` (in frontend directory)
2. Deploy the `dist/` folder to Vercel or Netlify
3. Update the Socket.IO connection URL in [App.jsx](frontend/src/App.jsx) to your deployed backend URL

**Current Production URL**: `https://chat-bot-4bca.onrender.com`

---

## 🚀 Future Improvements

- 🔐 User authentication (JWT)
- ✏️ Typing indicators ("AI is typing...")
- 👥 Multi-user chat rooms
- 🎤 Voice-based interaction
- 📎 File upload support
- 🌙 Dark/Light theme toggle
- 📱 Mobile-responsive improvements
- 🔄 Message retry mechanism

---

## 🤝 Contributing

Contributions are welcome! Feel free to fork this repo and submit a PR.

---

## 📜 License

This project is licensed under the MIT License.

---

## 👨‍💻 Author

**Puneet Verma**

- GitHub: https://github.com/PuneetVerma07
- LinkedIn: https://www.linkedin.com/in/puneetdotio

---
