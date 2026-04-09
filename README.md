# 1slash
One hit. One decision. One slash.  A real-time multiplayer duel game focused on reaction, mind games, and precision. Built with WebSocket and terminal-style UI. Server-authoritative WebSocket multiplayer duel engine. Focused on low-latency combat, prediction, and hit validation.

# 1SLASH

One hit. One decision. One slash.

1SLASH is a fast-paced 1v1 duel game inspired by fighting games like Street Fighter 6, reimagined into a minimal, one-hit kill system.

The game features a side-view combat perspective with a terminal-style visual aesthetic, focusing on timing, mind games, and precise decision-making.

---

## 🎯 Core Concept

A strict two-player duel.

No crowds. No chaos. Just you and your opponent.

There are:
- No combos
- No health bars
- No complex move lists

Only positioning, timing, and psychological pressure.

One clean hit decides everything.

---

## ⚔️ Gameplay Design

### 🎮 Controls

- Move Left / Right
- Charge (hold)
- Confirm Attack
- Parry

---

### 🧠 Combat Mechanics

#### Charge
- Holding charge creates pressure
- Limits defensive options
- Forces opponent reaction

#### Confirm Attack
- Attack only executes when confirmed
- Mistimed attacks are punishable

#### Feint
- Releasing charge without attack triggers a fake
- Feints create mind games but leave vulnerability

#### Parry
- Tight timing window defensive action
- Successful parry counters attack
- Failed parry results in heavy punishment

---

## 🔁 Core Gameplay Loop

Charge → Pressure → Reaction →  
Attack or Feint → Parry / Punish → Reset

---

## 🖥️ Visual Style

- Side-view (fighting game perspective)
- Terminal-style UI
- Minimalist stickman characters

---

## 🏗️ Tech Stack

Frontend:
- HTML / Canvas

Backend:
- Node.js
- WebSocket

Architecture:
- Server-authoritative
- Real-time 1v1 synchronization
- Deterministic combat resolution

---

## 📂 Project Structure (Planned)

1slash/
│
├── client/
├── server/
├── protocol/
└── README.md

---

## 🚧 Development Scope

Focused on:
- 2-player duel only
- Real-time interaction
- Tight combat timing

Not targeting:
- Large-scale multiplayer
- MMO systems
- Complex matchmaking (for now)

---

## 📌 Roadmap

Phase 1:
- Local / LAN 1v1 duel
- Core combat system

Phase 2:
- Online 1v1 play
- Latency handling

Phase 3:
- Matchmaking (optional)
- Ranking system

---

## 📜 License

MIT License

---

## ⚡ Author

Smokie
