<div align="center">

# 🏛️ Nepal Constitution Chatbot

### *Ask anything about Nepal's Constitution of 2015 — powered by AI*

[![FastAPI](https://img.shields.io/badge/Backend-FastAPI-009688?style=for-the-badge&logo=fastapi&logoColor=white)](https://fastapi.tiangolo.com)
[![React](https://img.shields.io/badge/Frontend-React_19-61DAFB?style=for-the-badge&logo=react&logoColor=black)](https://react.dev)
[![Groq](https://img.shields.io/badge/LLM-LLaMA_3.3_70B-F55036?style=for-the-badge)](https://groq.com)
[![RAG](https://img.shields.io/badge/Search-Hybrid_RAG-purple?style=for-the-badge)](https://www.langchain.com)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow?style=for-the-badge)](LICENSE)

</div>

---

## 🏗️ Architecture

![AI Project Architecture — Chat Application](./frontend/architecture.jpg)

> *Full-stack AI chat app: **React UI** → **FastAPI Backend** → **RAG Pipeline** (ChromaDB + BM25 + LLaMA 3.3 70B via Groq) → **JSON Response** → **React displays the answer.***

---

## 📂 Repository Structure

```
Constitution-chatbot/
├── backend/           # FastAPI server + RAG engine
│   ├── main.py        # REST API endpoints
│   ├── rag_engine.py  # PDF → Embeddings → Hybrid Search → LLM
│   ├── requirements.txt
│   └── README.md      ← detailed backend docs
│
├── frontend/          # React + Vite + Tailwind chat UI
│   ├── src/
│   │   ├── components/
│   │   │   ├── Header.jsx
│   │   │   ├── ChatBox.jsx
│   │   │   └── Message.jsx
│   │   └── App.jsx
│   ├── package.json
│   └── README.md      ← detailed frontend docs
│
└── README.md          ← you are here
```

---

## ⚡ Quick Start

### 1. Backend
```bash
cd backend
python -m venv myenv && myenv\Scripts\activate
pip install -r requirements.txt
# Add GROQ_API_KEY to .env
uvicorn main:app --reload --port 8001
```

### 2. Frontend
```bash
cd frontend
npm install
npm run dev
```

Open **`http://localhost:5173`** — start chatting! 🎉

---

## 📚 Detailed Documentation

| | Link |
|---|---|
| 🖥️ Backend | [backend/README.md](./backend/README.md) |
| 📱 Frontend | [frontend/README.md](./frontend/README.md) |

---

<div align="center">

**Made with ❤️ for the people of Nepal 🇳🇵**

</div>