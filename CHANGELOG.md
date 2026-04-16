# 📜 ClaudeNotes Changelog

## v0.2 — 2026-04-16 — Pokémon Team Edition

### 🎮 Added
- **Canon Gen 1 Pokémon mapping** for all 8 agents:
  - 🌸 MEW (#151) → `/notes` — orchestrator, knows every move
  - ⚡ PIKACHU (#025) → `/capture` — Quick Attack priority spam
  - 💪 MACHAMP (#068) → `/sort` — 4 arms, parallel inbox routing
  - 🧲 MAGNETON (#082) → `/connect` — magnetic network linking
  - 😴 SNORLAX (#143) → `/distill` — 460kg compressed mass + Leftovers
  - 🥄 ALAKAZAM (#065) → `/recall` — IQ 5000 perfect memory
  - 🦅 PIDGEOT (#018) → `/map` — Mach 2 bird's-eye scout
  - ⭐ EEVEE (#133) → `/evolve` — THE Evolution Pokémon
- **`COMBOS.md`** — multi-agent notetaking patterns ("wombo combos") for common workflows
- **Battle priority rotation** documented in README (frequency-based ordering)
- **`/capture` IS the rotation** as the core principle — everything else is a cooldown

### 🔧 Changed
- README restructured around the Pokémon team metaphor for memorability
- Agent table now shows Pokémon # + canonical role per slot
- Quick Start section uses Pokémon-themed command examples

### 💡 Why this matters
The Pokémon framing turns abstract agent roles into a memorable team. You don't have to remember "the agent that compresses notes" — you remember "Snorlax." Memory researchers call this **chunking with vivid mnemonics**. Same trick BibleMemory Pro uses for verse recall.

---

## v0.1 — 2026-04-16 — Bootstrap

### 🌱 Initial release
- Repo positioned as a Notion competitor: agent factory > static templates
- 8 specialized `.skill` agents scaffolded:
  - `/notes` (orchestrator) — single foolproof entry point
  - `/capture` — quick brain-dump (no friction)
  - `/sort` — routes inbox into hierarchy via PREFERENCES rules
  - `/connect` — finds semantic cross-links, builds knowledge graph
  - `/distill` — compresses verbose notes (3:1 default, archives original)
  - `/recall` — quizzes you on YOUR notes (first-letter recall mechanic)
  - `/map` — regenerates MAP.md sitemap on demand
  - `/evolve` — silent observer that writes new rules to PREFERENCES.md
- **Shared brain:** `PREFERENCES.md` — every agent reads it before acting
- **Learning loop:** `/evolve` writes new rules to PREFERENCES.md weekly
- **First proving ground:** Vanderbilt Coursera prompt engineering course
- 6 module folders scaffolded with NOTES + QUOTES templates
- Sample inbox capture seeded for first `/sort` test

### 🎯 The bet
After 30+ sessions, the system organizes notes better than the user would manually. That's the difference between a SaaS (Notion) and an agent factory (ClaudeNotes).

---

🎮💎🃏 Built in Claude Code. Designed for daily use, not demos.
