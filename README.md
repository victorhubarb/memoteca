# Memoteca 📝
 
![Status](https://img.shields.io/badge/status-completed-green?style=for-the-badge)
![JavaScript](https://img.shields.io/badge/HTML5%20%2B%20CSS3%20%2B%20JavaScript-Frontend-yellow?style=for-the-badge)
 
A memory and thoughts collector built with vanilla JavaScript and Axios — full CRUD operations backed by a JSON Server REST API, with search, favorites, and date management.
 
---
 
## Live Application
 
[Memoteca Demonstration](https://memoteca-rust.vercel.app)
 
---
 
## Overview
 
Memoteca lets users store, organize, and revisit their thoughts and memories. What makes it more than a simple list app is the architecture — all data operations go through a real REST API (JSON Server), consumed asynchronously with Axios. The `api.js` module handles every endpoint, and `ui.js` takes care of rendering and DOM interaction. Clean separation of concerns without any framework.
 
---
 
## Features
 
- **Create Memories** — add a thought with content, author, and date
- **Edit Memories** — update existing entries through a pre-filled form
- **Favorite** — toggle memories as favorites with a PATCH request
- **Delete** — remove memories with a DELETE request
- **Search** — filter memories by content or author in real time
- **Persistent Storage** — all data lives in JSON Server, survives page reloads
- **Responsive Design** — works across different screen sizes
---
 
## Architecture
 
```
memoteca/
├── index.html              # Main page — memory list and form
├── css/
│   └── styles.css          # All styles
├── js/
│   ├── api.js              # All API calls — GET, POST, PUT, PATCH, DELETE via Axios
│   ├── ui.js               # DOM manipulation — renders memories, fills form, handles events
│   └── main.js             # Entry point — wires api and ui together
├── assets/
│   └── imagens/            # Icons and images
└── backend/
    ├── db.json             # JSON Server database
    └── package.json        # JSON Server setup
```
 
### Key Concepts Applied
 
| Concept | How it shows up |
|---|---|
| **Axios** | All HTTP requests use Axios instead of native fetch — GET, POST, PUT, PATCH, DELETE |
| **async/await** | Every API call is async with try/catch error handling |
| **ES Modules** | `api.js` uses `export default`; `ui.js` imports it with `import` |
| **REST API** | JSON Server exposes `/pensamentos` as a full REST endpoint |
| **Date handling** | Dates are converted between ISO string (API) and Date objects (UI) |
| **Separation of concerns** | `api.js` never touches the DOM; `ui.js` never makes HTTP calls directly |
 
---
 
## How to Run
 
**Prerequisites:** Node.js installed
 
```bash
# Clone the repository
git clone https://github.com/victorhubarb/memoteca.git
cd memoteca
 
# Start JSON Server (separate terminal)
cd backend
npm install
npm start
 
# Open index.html in your browser (use Live Server or similar)
```
 
The API runs at `http://localhost:3000/pensamentos`.
 
---
 
## Technologies
 
- **HTML5 / CSS3 / JavaScript**
- **Axios** — HTTP client for REST API calls
- **JSON Server** — local REST API from `db.json`
- **ES Modules** — native JavaScript module system
---
 
## Author
 
**Victor Hugo Barbosa**
[GitHub](https://github.com/victorhubarb) · [LinkedIn](https://www.linkedin.com/in/victorhbarbosa/)
