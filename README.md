 ![logo](https://github.com/sahilatahar/Code-Sync/assets/100127570/d1ff7f52-a692-4d51-b281-358aeab9156e)

# CodeSync – Real-Time Collaborative Code Editor

CodeSync is a **real-time collaborative coding platform** where multiple users can join a shared room and edit code simultaneously. The application uses **WebSockets via Socket.IO** to synchronize updates instantly between connected users.

Users can collaborate on files, chat in real time, view each other's cursor movements, and use a shared whiteboard for collaborative drawing.

---

## 🚀 Features

* 💻 Real-time collaborative code editing
* 🚀 Unique room generation for multi-user collaboration
* 📁 Create, edit, rename, and delete files or directories
* ⏱️ Instant synchronization of code updates across all users
* 👥 User presence tracking (join / leave notifications)
* 💬 Real-time group chat inside collaboration rooms
* 🖊 Live cursor position and typing indicators
* 🌈 Syntax highlighting for multiple programming languages
* 🎨 Collaborative drawing board
* 💾 Export project files as a ZIP

---

## 🏗 Architecture Overview

CodeSync follows a **client–server architecture using WebSockets**.

1. A user joins a collaboration room using a unique room ID.
2. The frontend establishes a WebSocket connection with the backend.
3. When a user edits code or performs an action, the client emits a Socket.IO event.
4. The server receives the event and broadcasts the update to all users in the same room.
5. Other clients listen for the event and update their UI instantly.

### Real-time Synchronization Flow

```
User A edits code
        │
        ▼
Frontend emits Socket.IO event
        │
        ▼
Node.js Server receives event
        │
        ▼
Server broadcasts update to room
        │
        ▼
User B and User C receive update instantly
```

---

## 💻 Tech Stack

### Frontend

* React
* TypeScript
* Vite
* CodeMirror (Code editor)
* Socket.IO Client
* Tldraw (Collaborative drawing)

### Backend

* Node.js
* Express.js
* Socket.IO
* TypeScript

### Tools & Libraries

* Git & GitHub
* UUID (room ID generation)
* JSZip & FileSaver (export project as zip)

---

## ⚙️ Installation & Setup

### 1. Clone the repository

```
git clone https://github.com/<your-username>/Code-Sync.git
cd Code-Sync
```

### 2. Setup Backend

```
cd server
npm install
npm run dev
```

Backend server runs on:

```
http://localhost:3000
```

### 3. Setup Frontend

Open another terminal:

```
cd client
npm install
npm run dev
```

Frontend runs on:

```
http://localhost:5173
```

---

## ⚠️ Current Limitations

* Data is stored **in memory**, so sessions reset if the server restarts.
* The system currently runs on a **single server instance** and does not support horizontal scaling.

---

## 🔮 Possible Improvements

* Add **Redis Pub/Sub** for multi-server scaling
* Persist files and chat history using a **database**
* Implement **authentication (JWT or OAuth)**
* Add **conflict resolution algorithms for simultaneous edits**

---

## 🌟 Acknowledgements

This project uses several open-source libraries:

* **Socket.IO** – real-time communication between clients
* **CodeMirror** – browser-based code editor
* **Tldraw** – collaborative drawing whiteboard
* **React & TypeScript** – frontend development
* **Node.js & Express** – backend server framework

---

## 👩‍💻 Author

**Kumari Siddhi**

GitHub: https://github.com/KumariSiddhi  

---

## 📜 License

This project is licensed under the **MIT License**.
