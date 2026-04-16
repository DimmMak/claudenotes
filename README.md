# 📓⚡ ClaudeNotes — Notes That Beat Notion

> A factory of Claude `.skill` agents that take notes WITH you, learn how YOU organize, and build a foolproof hierarchy as you go.
>
> **First proving ground:** [Vanderbilt's Prompt Engineering for ChatGPT](https://www.coursera.org/learn/prompt-engineering) (Coursera).

---

## 🆚 Why this beats Notion

| Notion | ClaudeNotes |
|---|---|
| You manually organize pages | Agents organize for you |
| Templates are static | System adapts to YOU over time |
| Search is keyword-based | Cross-linking is semantic |
| Quizzes? None. | `/recall` drills your own notes |
| Auto-summary? Manual AI block. | `/distill` compresses on demand |
| Sitemap? You build it. | `/map` regenerates it after every session |
| Lock-in to a SaaS | Plain markdown in git, runs in any Claude session |

**The killer feature:** ClaudeNotes **learns your organization style** and gets sharper every session.

---

## 🎮 The Team — Your 8 Pokémon (Gen 1)

Each agent is canonically mapped to a Gen 1 Pokémon. Treat your repo like a battle team.

```
╔═══════════════════════════════════════════════════════════════╗
║  🥇 ALAKAZAM   #065  /recall   — IQ 5000, perfect memory     ║
║  ⚡ PIKACHU    #025  /capture  — Quick Attack priority spam  ║
║  ⭐ EEVEE      #133  /evolve   — THE Evolution Pokémon       ║
║  🌸 MEW        #151  /notes    — knows every move (router)   ║
║  🦅 PIDGEOT    #018  /map      — Mach 2 scout, bird's-eye    ║
║  😴 SNORLAX    #143  /distill  — 460kg of compressed mass    ║
║  🧲 MAGNETON   #082  /connect  — 3 magnets fused as network  ║
║  💪 MACHAMP    #068  /sort     — 4 arms, 100 punches/2 sec   ║
╚═══════════════════════════════════════════════════════════════╝
```

### 📘 Pokédex roles

| Slot | Pokémon | Agent | Real Job |
|---|---|---|---|
| 1 | 🌸 **MEW** #151 | `/notes` | Orchestrator. Routes intent to right specialist. |
| 2 | ⚡ **PIKACHU** #025 | `/capture` | Spam filler. Quick Attack = priority capture, no friction. |
| 3 | 💪 **MACHAMP** #068 | `/sort` | Cleanup. 4 arms = parallel inbox routing. |
| 4 | 🧲 **MAGNETON** #082 | `/connect` | Linker. Magnetic pull between related notes. |
| 5 | 😴 **SNORLAX** #143 | `/distill` | Compressor. Massive density, holds Leftovers (archive). |
| 6 | 🥄 **ALAKAZAM** #065 | `/recall` | Memory. IQ 5000, drills first-letter recall. |
| 7 | 🦅 **PIDGEOT** #018 | `/map` | Scout. Flies at Mach 2, sees the whole map. |
| 8 | ⭐ **EEVEE** #133 | `/evolve` | Adapter. Mutates based on environment (your usage). |

### ⚔️ Battle priority (most-used first)

```
🥇 PIKACHU  ⚡ → spam during every lecture (Quick Attack priority)
🥈 MACHAMP  💪 → cleanup after sessions
🥉 ALAKAZAM 🥄 → daily morning quiz
4️⃣ MAGNETON 🧲 → burst window: link related notes
5️⃣ SNORLAX  😴 → maintenance: compress fat files
6️⃣ PIDGEOT  🦅 → passive scout: refresh sitemap
7️⃣ MEW      🌸 → fallback when intent is ambiguous
8️⃣ EEVEE    ⭐ → SUNDAY ONLY — weekly evolution event
```

> **`/capture` IS the rotation. Everything else is a cooldown.**
> Treat Pikachu's Quick Attack like a Combo Point builder — spam constantly, the finishers (Machamp, Magneton) consume what you generated.

---

## 🤖 The Agent Factory

Eight agents. One foolproof entry point. One shared brain.

```
              ┌─────────────────┐
              │   /notes  🌸    │  ← single entry point
              │  (orchestrator) │
              └────────┬────────┘
                       │ routes to:
       ┌───────┬───────┼───────┬───────┬───────┬───────┐
       ▼       ▼       ▼       ▼       ▼       ▼       ▼
   /capture /sort /connect /distill /recall /map  /evolve
      ⚡     💪     🧲       😴       🥄    🦅     ⭐
```

All agents read & write to `PREFERENCES.md` — that's how the system learns YOU.

---

## 🚀 Quick start

```bash
# 1. In any Claude Code session inside this repo:
> /notes capture "few-shot beats zero-shot when output format matters"
# ⚡ PIKACHU lands the Quick Note. Capture in inbox/ in 2 seconds.

# 2. After your study session:
> /notes sort
# 💪 MACHAMP routes everything from inbox to its proper folder.

# 3. The next morning:
> /notes recall
# 🥄 ALAKAZAM drills you on yesterday's notes (first-letter recall).

# 4. Sunday night:
> /notes evolve
# ⭐ EEVEE evolves the system based on your week's behavior.
```

See [`COMBOS.md`](COMBOS.md) for the full set of multi-agent patterns ("wombo combos").

---

## 📂 Repo layout

```
claudenotes/
├── README.md              # This file (Pokémon team + agent overview)
├── CHANGELOG.md           # Version history
├── COMBOS.md              # Multi-agent notetaking patterns (wombo combos)
├── PREFERENCES.md         # Learned rules — agents read & write here
├── MAP.md                 # Auto-generated sitemap (regenerate via /map)
├── MEMORIZE.md            # Pinned must-remember stuff
├── PROGRESS.md            # Course progress (Vanderbilt)
├── inbox/                 # Raw captures land here, /sort empties it
├── modules/               # Hierarchical course notes
│   ├── 01-course-intro/
│   ├── 02-intro-to-prompts/
│   ├── 03-prompt-patterns-1/
│   ├── 04-few-shot-examples/
│   ├── 05-prompt-patterns-2/
│   └── 06-prompt-patterns-3/
├── archive/               # Old/superseded notes (never deleted)
└── skills/
    ├── notes/SKILL.md     # 🌸 MEW
    ├── capture/SKILL.md   # ⚡ PIKACHU
    ├── sort/SKILL.md      # 💪 MACHAMP
    ├── connect/SKILL.md   # 🧲 MAGNETON
    ├── distill/SKILL.md   # 😴 SNORLAX
    ├── recall/SKILL.md    # 🥄 ALAKAZAM
    ├── map/SKILL.md       # 🦅 PIDGEOT
    └── evolve/SKILL.md    # ⭐ EEVEE
```

---

## 🌱 How "progressive learning" works

Every time you reject an agent's suggestion, override its default, or invent a new convention, **EEVEE (`/evolve`)** writes the lesson to `PREFERENCES.md`.

After 10 sessions, `PREFERENCES.md` knows:
- You prefer bullet points over prose
- You always tag `#interview-prep` for resume material
- You hate emoji headers but love emoji bullets
- You file by topic, never by date
- You always lead notes with the "so what"

**The system literally becomes sharper at organizing YOUR notes than you are.**

That's the bet. That's why ClaudeNotes > Notion.

---

## 🔗 Sister projects

- [PROMPTLATRO](https://github.com/DimmMak/promptlatro) — roguelike that drills prompt patterns
- [CodeRecall](https://github.com/DimmMak/coderecall) — first-letter recall for SQL/Python

---

## 🎯 Status

**v0.2 — Pokémon Team Edition.** All 8 agents mapped to canon Gen 1 Pokémon. COMBOS.md added for multi-agent patterns. Vanderbilt course loaded as proving ground.

🎮💎🃏
