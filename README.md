# ⚙️ Nova Nexus — Manufacturing Order Intelligence Platform

> NOVA NEXUS Hackathon 2025 | DSATM College | MCA Department

---

## 🚀 Quick Start (VS Code)

### Option 1 — Live Server (Recommended)
1. Open the `nova-nexus` folder in **VS Code**
2. Install the **Live Server** extension (ritwickdey.LiveServer)
3. Right-click `index.html` → **"Open with Live Server"**
4. Browser opens at `http://127.0.0.1:5500`

### Option 2 — Direct Open
- Just double-click `index.html` — it works directly in any modern browser (Chrome, Edge, Firefox)

---

## 🔑 Demo Credentials

| Role | Username | Password | Can Do |
|------|----------|----------|--------|
| User | `admin` | `admin123` | Place orders via chat, check status, query orders |
| Vendor | `vendor` | `vendor123` | Move orders: Received → In Review |
| Manufacturer | `mfg` | `mfg123` | Move orders: In Review → Accepted + Quality Logs |

> You can also **register new accounts** from the login screen.

---

## 🏗️ Architecture

```
index.html (Single File App)
├── Auth Layer         → localStorage user accounts + sessionStorage sessions
├── Chat Interface     → NLP via Groq API (llama-3.3-70b-versatile)
│   ├── Intent Classification  → Groq (create_order / status_query / list_query / quality_query)
│   └── Entity Extraction      → Groq (partName, material, quantity, unit, deadline, specs)
├── Order Dashboard    → Real-time from localStorage, filterable + searchable
├── Vendor Panel       → Status management UI (no AI — pure UI logic)
└── Data Persistence   → localStorage (orders, users, counter)
```

---

## ✅ Features Implemented

### Core Requirements (from PDF + Whiteboard)
| Feature | Status |
|---------|--------|
| NLP Chat Interface (Groq LLM) | ✅ |
| Create Order via natural language | ✅ |
| Extract: part, material, qty, deadline, specs | ✅ |
| Update status via chat (User asks, Vendor acts) | ✅ |
| Order status flow: Received → In Review → Accepted | ✅ |
| Quality log updates with timestamps | ✅ |
| Order Dashboard (read-only, all orders) | ✅ |
| Auto-updates on order create/change | ✅ |
| localStorage persistence | ✅ |
| User Authentication (register/login/logout) | ✅ |
| **Bonus: Multi-order awareness** | ✅ |

### Role System
- **User** — Interacts via chat, places orders, checks status
- **Vendor** — Manages orders panel: moves Received → In Review
- **Manufacturer** — Manages orders panel: moves In Review → Accepted, adds quality logs

### Bonus Features
- Filter orders by status
- Search orders by part name, material, order ID
- Stats bar (total, received, in review, accepted)
- Quick prompt buttons
- Live NLP indicator

---

## 🛠️ Tech Stack

| Layer | Technology |
|-------|-----------|
| Frontend | Vanilla HTML5, CSS3, JavaScript (ES2024) |
| NLP | Groq API — llama-3.3-70b-versatile |
| Storage | localStorage + sessionStorage |
| No build tools | Zero dependencies — open directly |

---

## 💬 Example Chat Commands

```
# Place an order:
"I need 200 titanium flanges, 80mm bore, delivered by July 20"
"Order 500kg of stainless steel rods grade 316L by August 1"

# Check status:
"What's the status of order #3?"
"Show order #1"

# List orders (BONUS - multi-order awareness):
"Show all accepted orders"
"List all orders in review"
"Show me all my orders"

# Quality queries:
"What are the quality notes on order #2?"
```

---

## 📊 Judging Criteria Coverage

| Criteria | Marks | Implementation |
|----------|-------|---------------|
| NLP Extraction Accuracy | 30 | Groq llama-3.3-70b with structured JSON prompts |
| Token Efficiency | 25 | Stateless extraction, minimal context, 2 API calls max |
| UI/Dashboard Clarity | 20 | Live dashboard, status badges, filters, search |
| Functionality & Completeness | 15 | All 4 features + auth working end-to-end |
| **Bonus: Multi-Order Awareness** | 10 | Intent classifier detects list queries with status filter |

---

## 🌐 Deployment (Bonus Points)

To deploy on **Vercel**:
1. Push to GitHub
2. Import repo on vercel.com
3. No build config needed — static site

---

Built for Nova Nexus Hackathon 2025 · DSATM College · MCA Department
