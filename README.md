<div align="center">

# 🟣 RecallRival

**A competitive memory retention game built with React**

[![Status](https://img.shields.io/badge/status-in%20development-yellow?style=flat-square)](https://github.com)
[![React](https://img.shields.io/badge/React-18-61DAFB?style=flat-square&logo=react)](https://react.dev)
[![Node.js](https://img.shields.io/badge/Node.js-Express-339933?style=flat-square&logo=node.js)](https://nodejs.org)
[![Socket.io](https://img.shields.io/badge/Socket.io-real--time-010101?style=flat-square&logo=socket.io)](https://socket.io)
[![MongoDB](https://img.shields.io/badge/MongoDB-Mongoose-47A248?style=flat-square&logo=mongodb)](https://mongodb.com)
[![License](https://img.shields.io/badge/license-MIT-blue?style=flat-square)](LICENSE)

<br />

> Two players. One grid. A growing sequence you must never forget.

<br />

</div>

---

## What is RecallRival?

RecallRival is a competitive memory game where two players take turns building and recalling an ever-growing sequence of dots on a **5×5 grid**. Each round, one player adds a new dot to the sequence — the other must tap every dot back, in order, from memory. Miss a single one and the game is over.

It's simple to understand, genuinely difficult to master, and endlessly replayable.

---

## How It Works

```
Player 1 adds a dot  →  Player 2 recalls the full sequence
Player 2 adds a dot  →  Player 1 recalls the full sequence
         ↕
   One missed tap = game over
```

A **RecallRoom** tracks the live game state — the growing sequence of dots (RecallObjects), whose turn it is, and the outcome. Players earn a **RecallScore** across matches, combining dots reached and total wins.

---

## Four Ways to Play

| Mode | Description | Auth Required |
|------|-------------|:---:|
| 🤖 **ComputerRival** | Solo mode against an AI opponent | No |
| 👥 **LocalRival** | Pass-and-play on a single device | No |
| 🌐 **RemoteRival** | Real-time match via shareable link | Yes |
| 🎲 **RandomRival** | Matchmaking by RecallScore | Yes |

Auth is **soft-gated** — casual players can jump straight in. Signing in unlocks remote and ranked modes, cloud-saved scores, and streak tracking.

---

## Tech Stack

### Frontend
- **React 18** — component-driven UI, custom hooks, context API
- **`useGameLogic.js`** — all game decisions and state transitions in a single hook
- **RoomContext** — shared game state across the tree without prop drilling

### Backend *(in progress)*
- **Node.js + Express** — REST API
- **MongoDB + Mongoose** — persistent player profiles and RecallRoom history
- **Socket.io** — real-time synchronisation for RemoteRival mode
- **Google OAuth** — frictionless sign-in for competitive modes

### Architecture
```
src/
├── components/        # Pure display + event listeners only
├── hooks/
│   └── useGameLogic.js   # All game logic lives here
├── context/
│   └── RoomContext.js    # Global game state
└── utils/
    └── resolvePlayerId.js  # Assigns real / guest / computer IDs
```

---

## What This Project Demonstrates

This is **project 1 of 9** in a deliberate portfolio built to develop production-grade engineering skills — not tutorial clones, but real products with real architecture decisions.

RecallRival specifically demonstrates:

- **Frontend architecture discipline** — strict separation between display components, game logic hooks, and shared context; zero prop drilling
- **Progressive complexity** — four modes designed to layer in backend, auth, and real-time infrastructure incrementally
- **Domain modelling** — a consistent vocabulary (RecallRoom, RecallObject, RecallScore, RecallRival modes) that keeps the mental model clean across the entire codebase
- **Product thinking** — deliberate UX decisions like soft-gating auth, no resign button, and no timer that shape the game's character
- **Real-time engineering** — Socket.io integration for RemoteRival (planned), which is genuinely new territory being learned in public

---

## Roadmap

- [x] Architecture + schema design
- [x] Domain vocabulary + game rules finalised
- [ ] ComputerRival — pure React, no backend
- [ ] LocalRival — pass-and-play, one device
- [ ] Backend + Google OAuth
- [ ] RemoteRival — real-time via Socket.io
- [ ] RandomRival — RecallScore-based matchmaking

---

## Running Locally

```bash
# Clone the repo
git clone https://github.com/your-username/recallrival.git
cd recallrival

# Install dependencies
npm install

# Start the development server
npm run dev
```

Backend setup instructions will be added when the server is introduced in a later build phase.

---

## About

RecallRival is being built solo as part of a structured portfolio of nine projects aimed at breaking into professional web development. The approach: reason through architecture first, write clean code second, ship real products throughout.

Built by **Shubham** · [GitHub](https://github.com/shubhamwkg) · [LinkedIn](https://linkedin.com/in/shubhamwkg)

---

<div align="center">
  <sub>Made with focus, frustration, and a lot of dot-tapping.</sub>
</div>