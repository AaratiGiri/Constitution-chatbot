<div align="center">

# 🇳🇵 Nepal Constitution Chatbot — Frontend

### *A Beautiful React Chat Interface for Nepal's Constitution of 2015*

[![React](https://img.shields.io/badge/React-19.2-61DAFB?style=for-the-badge&logo=react&logoColor=black)](https://react.dev)
[![Vite](https://img.shields.io/badge/Vite-8.0-646CFF?style=for-the-badge&logo=vite&logoColor=white)](https://vitejs.dev)
[![TailwindCSS](https://img.shields.io/badge/Tailwind_CSS-4.3-38B2AC?style=for-the-badge&logo=tailwind-css&logoColor=white)](https://tailwindcss.com)
[![JavaScript](https://img.shields.io/badge/JavaScript-ES2024-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)](https://developer.mozilla.org/en-US/docs/Web/JavaScript)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow?style=for-the-badge)](LICENSE)

---

> **A stunning, responsive chat interface that connects directly to the RAG-powered backend — letting citizens explore Nepal's Constitution of 2015 through natural conversation.**

</div>

---

## 🏗️ System Architecture

![AI Project Architecture — Chat Application](./architecture.jpg)

> *This frontend is the **React Chat UI** layer at the top of the architecture above. It sends API requests to the **FastAPI Backend**, receives JSON responses, and displays the AI's answer beautifully in the chat window.*

---

## ✨ Features

| Feature | Description |
|---|---|
| 💬 **Real-time Chat** | Live chat with the AI — streaming-style typing indicator while waiting |
| 📝 **Markdown Rendering** | Bot responses rendered with full Markdown & GitHub Flavored Markdown |
| ⏱️ **Timestamped Messages** | Every message shows its send/receive time |
| 💡 **Suggestion Chips** | Quick-access question suggestions on the welcome screen |
| 📜 **Welcome Card** | Namaste greeting with constitution image on app launch |
| 🖼️ **Hero Header** | Full-width banner with Nepal ceremony photo + Nepal flag SVG |
| 🏛️ **Side Panels** | Parliament building & constitution book decorative panels (desktop) |
| 📱 **Fully Responsive** | Mobile-first design that works on all screen sizes |
| 🎨 **Nepal Color Palette** | Authentic Nepal flag colors — crimson red `#DC143C` & royal blue `#003893` |
| ⌨️ **Auto-Grow Input** | Textarea grows with content; `Enter` sends, `Shift+Enter` for new line |
| ♿ **Accessible** | Proper ARIA labels, semantic HTML, keyboard navigation |

---

## 📁 Project Structure

```
frontend/
├── src/
│   ├── components/
│   │   ├── Header.jsx          # Hero banner — Nepal flag, title, info badges
│   │   ├── ChatBox.jsx         # Main chat logic — messages, API calls, input
│   │   └── Message.jsx         # Individual message bubble with Markdown support
│   ├── App.jsx                 # Root layout — Header + side panels + ChatBox
│   ├── App.css                 # Component-level styles (side panels, animations)
│   ├── index.css               # Global styles & Tailwind base
│   └── main.jsx                # React DOM entry point
├── public/
│   ├── constitution.webp       # Constitution book illustration (chat avatar)
│   ├── parliament.jpg          # Nepal parliament — left side panel
│   ├── book.webp               # Constitution book — right side panel
│   └── nepal-ceremony.jpg      # Header background photo
├── index.html                  # HTML shell with SEO meta tags
├── vite.config.js              # Vite configuration with React plugin
├── package.json                # NPM scripts and dependencies
├── eslint.config.js            # ESLint rules
└── architecture.jpg            # Project architecture diagram
```

---

## 🎨 Component Overview

### `Header.jsx`
Full-width hero banner with:
- Blurred Nepal ceremony photo as background
- Dark blue gradient overlay for readability
- Nepal flag SVG + chatbot title
- Info badges: **272 Articles**, **35 Parts**, **9 Schedules**, **Promulgated 2015**

### `ChatBox.jsx`
The heart of the app — manages all state and API communication:
- **Welcome Card** with constitution image and suggestion chips
- Calls `POST http://localhost:8001/chat` with the user's message
- Shows animated **typing indicator** (3 bouncing dots) while waiting
- Graceful **error messages** if the backend is unreachable
- Auto-scroll to the latest message

### `Message.jsx`
Individual chat bubble with:
- **User** messages: Crimson red gradient, aligned right
- **Bot** messages: White bubble with `ReactMarkdown` rendered content
- Sender label (`You` / `🇳🇵 Constitution Bot`)
- Message timestamp in italic

---

## 🚀 Getting Started

### Prerequisites

- Node.js 18 or higher
- npm or yarn
- The [backend server](../backend/README.md) running on `http://localhost:8001`

### 1️⃣ Clone the Repository

```bash
git clone https://github.com/your-username/constitution-chatbot.git
cd constitution-chatbot/frontend
```

### 2️⃣ Install Dependencies

```bash
npm install
```

### 3️⃣ Start the Development Server

```bash
npm run dev
```

The app will open at: **`http://localhost:5173`**

> ⚠️ Make sure the [backend](../backend/README.md) is running first, or you'll see a connection error message in chat.

---

## 🖥️ Available Scripts

| Command | Description |
|---|---|
| `npm run dev` | Start Vite development server with HMR |
| `npm run build` | Build optimized production bundle to `dist/` |
| `npm run preview` | Preview the production build locally |
| `npm run lint` | Run ESLint on the source files |

---

## 📦 Dependencies

### Runtime Dependencies

| Package | Version | Purpose |
|---|---|---|
| `react` | ^19.2.4 | Core React library |
| `react-dom` | ^19.2.4 | React DOM renderer |
| `react-markdown` | ^10.1.0 | Renders Markdown in bot messages |
| `remark-gfm` | ^4.0.1 | GitHub Flavored Markdown plugin |

### Dev Dependencies

| Package | Version | Purpose |
|---|---|---|
| `vite` | ^8.0.0 | Lightning-fast build tool & dev server |
| `@vitejs/plugin-react` | ^6.0.0 | React Fast Refresh via Oxc |
| `tailwindcss` | ^4.3.3 | Utility-first CSS framework |
| `@tailwindcss/vite` | ^4.3.3 | Tailwind Vite integration |
| `eslint` | ^9.39.4 | JavaScript linter |

---

## 🎨 Design System

### Color Palette

| Color | Hex | Usage |
|---|---|---|
| 🔴 Nepal Crimson | `#DC143C` | User message bubbles, send button |
| 🔵 Royal Blue | `#003893` | Header overlay, badge borders, link colors |
| ⚪ White | `#FFFFFF` | Bot message bubbles, input background |
| 🩶 Slate | `#F8FAFC` | App background |

### Typography
- Font stack: `Inter`, `system-ui`, `sans-serif`
- Message text: `15px` with relaxed line height
- Sender labels: `11px` uppercase tracked

### Animations
- **Typing indicator**: 3 dots bouncing with staggered delays (0ms / 150ms / 300ms)
- **Message bubbles**: Fade-in slide animation on arrival (`animate-bubble`)
- **Avatar hover**: Subtle `scale(1.05)` on hover
- **Suggestion chips**: Color-invert transition on hover

---

## 🔌 API Integration

The frontend communicates with the backend via a single endpoint:

```
POST http://localhost:8001/chat
Content-Type: application/json

Body: { "message": "Your question about the constitution" }
Response: { "answer": "AI-generated answer from the RAG pipeline" }
```

**Error handling:**
- If the backend is down → Shows a friendly error message in the chat
- If the message is empty → Send button stays disabled

---

## 💬 Sample Questions to Try

```
🏛️ "What is Article 1 of the Constitution?"
📜 "How many articles does the Constitution have?"
⚖️ "What are the fundamental rights guaranteed?"
🗺️ "How many provinces does Nepal have?"
👑 "What is the structure of the government?"
🌿 "What does the Constitution say about the environment?"
👩 "What are women's rights in the Constitution?"
🏫 "What does it say about education rights?"
```

---

## 🔗 Related

- 🖥️ [Backend — FastAPI RAG API](../backend/README.md)
- 📜 [Constitution of Nepal (Official)](https://www.lawcommission.gov.np)
- ⚡ [Vite Documentation](https://vitejs.dev)
- ⚛️ [React Documentation](https://react.dev)

---

<div align="center">

**Made with ❤️ for the people of Nepal 🇳🇵**

*Empowering citizens with easy access to their constitutional rights*

</div>
