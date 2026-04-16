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

## 🤖 The Agent Factory

Seven specialist agents, one orchestrator. Each agent has ONE job and does it well.

```
              ┌─────────────────┐
              │   /notes        │  ← single entry point
              │  (orchestrator) │
              └────────┬────────┘
                       │ routes to:
       ┌───────┬───────┼───────┬───────┬───────┬───────┐
       ▼       ▼       ▼       ▼       ▼       ▼       ▼
   /capture /sort  /connect /distill /recall /map  /evolve
```

| Agent | Job |
|---|---|
| 📥 **/capture** | Quick brain-dump. No judgement. Lands in `inbox/`. |
| 🗂️ **/sort** | Routes captures from inbox into the right folder/file. |
| 🔗 **/connect** | Finds cross-links between new notes and existing ones. |
| 💎 **/distill** | Compresses verbose notes into bullet essentials. |
| 🧠 **/recall** | Quizzes you on YOUR notes (first-letter recall mechanic). |
| 🗺️ **/map** | Regenerates `MAP.md` — visual sitemap of all notes. |
| 🌱 **/evolve** | Watches your choices, updates `PREFERENCES.md`. |

All seven read & write to `PREFERENCES.md` — that's the "memory" of how YOU like things organized.

---

## 🚀 Quick start

```bash
# 1. In any Claude Code session inside this repo:
> /notes capture "Today learned that few-shot beats zero-shot when output format matters"

# Capture lands in inbox/, /sort routes it, /connect cross-links it, /map updates.
# Three commands later you have a permanent, hierarchical, searchable note.

# 2. Quiz yourself a week later:
> /notes recall

# /recall drills you on what you've captured, surfaces what you've forgotten.

# 3. See your knowledge graph:
> /notes map
# Opens MAP.md
```

---

## 📂 Repo layout

```
claudenotes/
├── README.md              # This file
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
    ├── notes/SKILL.md     # Orchestrator (single entry point)
    ├── capture/SKILL.md
    ├── sort/SKILL.md
    ├── connect/SKILL.md
    ├── distill/SKILL.md
    ├── recall/SKILL.md
    ├── map/SKILL.md
    └── evolve/SKILL.md
```

---

## 🌱 How "progressive learning" works

Every time you reject an agent's suggestion, override its default, or invent a new convention, `/evolve` writes the lesson to `PREFERENCES.md`.

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

**v0.1 — Bootstrap.** All 8 agents scaffolded. First capture flow works end-to-end. Course (Vanderbilt) loaded as test workspace.

📓⚡🃏
