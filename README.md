# 🌐 **Meetio**  

## 🌍 Seamless Video Conferencing with Real-Time Translation  

---

## 💡 About The Project  

**TalentIQ** is a next-generation video conferencing platform designed to **eliminate language barriers**.

By integrating **real-time translation** into chat, live captions, and collaborative notes, participants can communicate naturally in their own language.

---



---

# 🚀 Key Features  

---

## 🗣️ Real-Time Live Captions  

Understanding different accents and languages can be challenging.

TalentIQ provides **live translated captions** for every speaker.

- ⚡ **Instant Translation** — Speak in Hindi, a Spanish user reads Spanish captions  
- 🎙️ **Accent Handling** — Advanced speech recognition adapts to various accents  
- ♿ **Accessibility** — Inclusive for hearing-impaired users and non-native speakers  

---

## 💬 Multilingual Chat Translation  

No more switching tabs to translation tools.

- 🌐 **Auto-Translation** — Messages are instantly translated into the receiver's preferred language  
- 🤝 **Seamless Experience** — Everyone reads chat in their native language  

---

## 📝 Collaborative Translated Notes  

Never miss key information during meetings.

- 🧑‍🤝‍🧑 **Synced Editing** — Real-time collaborative editor (like Google Docs)  
- 🌎 **Personalized View** — Same notes displayed in each user’s selected language  
- 🔄 **Zero Information Loss** — Notes sync and translate instantly  

---

## 📹 Crystal Clear Video Calls  

- 🚀 **Low Latency** — Optimized streaming for smooth communication  
- 🔒 **Secure Sessions** — End-to-end encrypted signals  
- 🙌 **Interactive Tools** — Raise hand, screen sharing, reactions  

---

# 🏗️ System Architecture  

Our system handles **real-time streams for video, audio, and text** while orchestrating translation services dynamically.
```mermaid
%%{init: {'theme': 'base', 'themeVariables': {
  'primaryColor': '#E3F2FD',
  'primaryBorderColor': '#1E88E5',
  'primaryTextColor': '#0D47A1',
  'lineColor': '#455A64',
  'fontSize': '16px'
}}}%%

graph TD

UserA["User A (English)"]:::user <-->|WebSocket| SocketServer["Socket.IO Server"]:::server
UserB["User B (Spanish)"]:::user <-->|WebSocket| SocketServer

subgraph Frontend [React PWA]
UI["Video Interface"]:::frontend
Speech["Web Speech API"]:::frontend
Editor["Quill Editor"]:::frontend
end

subgraph Backend [Node.js Cluster]
SocketServer

Trans["Lingo Translation Service"]:::ai
DB[("MongoDB")]:::db
end

UserA -- Audio/Video --> StreamSDK["Stream.io Servers"]:::video
StreamSDK -- Audio/Video --> UserB

Speech -- "Audio Text (en)" --> SocketServer
SocketServer -- "Translate (en→es)" --> Trans
Trans -- "Translated Text (es)" --> SocketServer
SocketServer -- "Caption (es)" --> UserB

Editor -- "Note Update (en)" --> SocketServer
SocketServer -- "Translate (en→es)" --> Trans
Trans -- "Translated Note (es)" --> SocketServer
SocketServer -- "Sync Update (es)" --> UserB

classDef user fill:#E1F5FE,stroke:#1E88E5,stroke-width:2px,color:#0D47A1;
classDef frontend fill:#E8F5E9,stroke:#43A047,stroke-width:2px,color:#1B5E20;
classDef server fill:#FFF3E0,stroke:#FB8C00,stroke-width:2px,color:#E65100;
classDef ai fill:#F3E5F5,stroke:#8E24AA,stroke-width:2px,color:#4A148C;
classDef db fill:#ECEFF1,stroke:#546E7A,stroke-width:2px,color:#263238;
classDef video fill:#FBE9E7,stroke:#F4511E,stroke-width:2px,color:#BF360C;
```
# 📁 Project Structure

```text
talentiq/
|
├── backend/
|   ├── controllers/        # Business logic
|   ├── routes/             # API routes
|   ├── middleware/         # Auth & error middleware
|   ├── services/           # Translation & external services
|   ├── models/             # MongoDB schemas
|   ├── socket/             # Socket.IO event handlers
|   ├── config/             # DB and environment configs
|   └── server.js           # Backend entry point
|
├── frontend/
|   ├── src/
|   |   ├── components/     # UI components
|   |   ├── pages/          # App pages
|   |   ├── hooks/          # Custom React hooks
|   |   ├── context/        # Global state
|   |   ├── services/       # API & socket services
|   |   └── main.jsx        # Frontend entry point
|   └── vite.config.js
|
├── .env.example
└── README.md
```

---

# ⚙️ Installation Guide

Follow these steps to set up the project locally.

---
## 1️⃣ Clone the Repository

```bash
git clone https://github.com/yourusername/talentiq.git
cd talentiq
```
## 2️⃣ Install Dependencies
```bash
npm install
cd backend && npm install
cd ../frontend && npm install
```

## 🔐 Environment Variables
# Create .env files in both backend/ and frontend/ directories.

📌 Backend .env
```bash

PORT=5000
MONGO_URI=your_mongodb_connection_string
JWT_SECRET=your_secret_key
STREAM_API_KEY=your_stream_key
LINGO_API_KEY=your_translation_service_key

```
📌 Frontend .env
```bash

VITE_BACKEND_URL=http://localhost:5000
VITE_STREAM_API_KEY=your_stream_key


```

## ▶️ Running the Application
🚀 Start Backend Server

```bash
cd backend
npm start
```
Runs on http://localhost:5000

## 💻 Start Frontend

```bash
cd frontend
npm run dev

```
Runs on http://localhost:5173



## 🧪 Future Improvements


### 🌍 Add more supported languages
### 🤖 Improve AI accent detection
### 📱 Mobile application support
### 📊 Meeting analytics dashboard
