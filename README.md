# NOVA-NEXUS---IN-TIME-CODERS
# 🏭 Nova Nexus — AI Manufacturing Order Management

> *Nova Nexus Hackathon 2025* · DSATM College · Built with React + Claude AI

An AI-powered manufacturing order management system where users interact entirely through natural language to place orders, update statuses, and log quality checkpoints.

---

## ✨ Features

| Feature | Description |
|---|---|
| 🤖 NLP Chat Interface | Natural language order placement & management via Claude AI |
| 📦 Order Management | Create, track, and update orders through conversation |
| 👤 User (Client) Auth | Place orders, view own orders |
| 🏭 Vendor Auth | Update statuses, log quality notes |
| 📊 Live Dashboard | Real-time order tracking with status & quality logs |
| 🔍 Multi-Order Queries | "Show all accepted orders" — bonus feature |
| 💾 Persistent Storage | localStorage-based persistence across sessions |

---

## 🚀 Quick Start

### Prerequisites
- *Node.js* v18+ → [Download](https://nodejs.org)
- *npm* v9+ (comes with Node.js)
- A terminal (VS Code integrated terminal works great)

### Step 1 — Clone / Setup
bash
# If you have git:
git clone <your-repo-url>
cd nova-nexus

# OR if you downloaded the zip:
cd nova-nexus


### Step 2 — Install Dependencies
bash
npm install

> This installs React, React Router, Framer Motion, date-fns, uuid — takes ~1 minute.

### Step 3 — Run the App
bash
npm start

> Opens at *http://localhost:3000* automatically.

---

## 🔑 Demo Accounts

### Client (User) Accounts
| Email | Password | Name |
|---|---|---|
| alice@client.com | user123 | Alice Chen |
| bob@client.com | user123 | Bob Mercer |

*Client can:* Place orders via chat, view own orders, query order status.

### Vendor Accounts
| Email | Password | Name |
|---|---|---|
| ops@vendor.com | vendor123 | Rajan Kumar |
| quality@vendor.com | vendor123 | Sneha Patel |

*Vendor can:* Update order status, log quality inspection notes, view all orders.

> You can also register new accounts from the login page.

---

## 💬 Example Chat Commands

### As a Client (User):

"I need 200 titanium flanges, 80mm bore, delivered by July 20"
"Place an order for 500 stainless steel brackets, 5mm thick, by June 15"
"Show me all my orders"
"What's the status of order #1?"


### As a Vendor:

"Mark order #1 as in review"
"Order #2 has been reviewed and accepted"
"Quality update on order #3 — passed visual inspection, no surface defects"
"Show all orders in review"
"List all accepted orders"


---

## 🏗️ Tech Stack

| Layer | Technology |
|---|---|
| Frontend | React 18 + CSS Modules |
| Routing | React Router v6 |
| AI / NLP | Claude API (claude-sonnet-4) with regex fallback |
| State | React Context API |
| Persistence | localStorage |
| Animations | CSS Animations + Framer Motion |
| Dates | date-fns |
| IDs | uuid |
| Fonts | Syne, JetBrains Mono, Instrument Serif (Google Fonts) |

---

## 📁 Project Structure


nova-nexus/
├── public/
│   └── index.html
├── src/
│   ├── components/
│   │   └── ProtectedRoute.jsx       # Auth guard
│   ├── context/
│   │   ├── AuthContext.jsx          # Authentication state & logic
│   │   └── OrdersContext.jsx        # Order management state
│   ├── pages/
│   │   ├── Auth.jsx / .module.css   # Login + Register
│   │   ├── Dashboard.jsx / .css     # Layout with sidebar
│   │   ├── Overview.jsx / .css      # Dashboard home
│   │   ├── Chat.jsx / .css          # AI Chat interface
│   │   ├── Orders.jsx / .css        # Order dashboard
│   │   └── QualityPage.jsx / .css   # Quality logs (vendor)
│   ├── utils/
│   │   └── nlpParser.js             # Claude API + regex NLP parser
│   ├── styles/
│   │   └── global.css               # Design system variables
│   ├── App.jsx                      # Router & providers
│   └── index.js                     # Entry point
└── package.json


---

## 🌐 Deployment

### Deploy to Vercel (Recommended — Free, Fast)

bash
# Install Vercel CLI
npm i -g vercel

# Build & deploy
npm run build
vercel --prod


*OR via Vercel Dashboard:*
1. Push code to GitHub
2. Go to [vercel.com](https://vercel.com) → New Project
3. Import your GitHub repo
4. Click Deploy — done! ✅

### Deploy to Netlify

bash
# Build the app
npm run build

# Install Netlify CLI
npm i -g netlify-cli

# Deploy
netlify deploy --prod --dir=build


*OR drag & drop* the build/ folder at [app.netlify.com/drop](https://app.netlify.com/drop).

---

## 🎯 Judging Criteria Coverage

| Criteria | Max | Coverage |
|---|---|---|
| NLP Extraction Accuracy | 30 | ✅ Claude API + regex fallback for part, qty, deadline, material, status, order ID |
| Token Efficiency | 25 | ✅ Stateless extraction, context trimming (last 10 orders only), no conversation history sent |
| UI / Dashboard Clarity | 20 | ✅ Industrial dark theme, status badges, order cards, detail drawer |
| Functionality & Completeness | 15 | ✅ All 4 features + auth |
| Multi-Order Awareness (Bonus) | 10 | ✅ "Show all accepted orders", "list orders in review" |

---

## 🔒 Authentication Architecture

- *Role-based*: user (client) or vendor — enforced in UI, NLP parser, and route guards
- *localStorage-based*: Accounts and session stored in browser
- *Pre-seeded accounts* for demo; registration supported
- Route-level protection via <ProtectedRoute> component

---

## 📝 Notes

- Claude API calls are made from the browser — no backend required
- If Claude API is unavailable, regex fallback parser activates automatically
- All data is in-memory/localStorage — resets on browser clear
- The app works fully offline with regex fallback

---

Built for Nova Nexus Hackathon 2025 · MCA Department · DSATM College
