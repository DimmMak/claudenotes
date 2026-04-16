# 🌱 PREFERENCES.md — How Danny Likes Notes

> The shared brain of every ClaudeNotes agent. Each `.skill` reads this BEFORE acting and `/evolve` writes new rules here as the user reveals preferences.
>
> **Rule:** never delete from this file — only add or refine. Past preferences become context for new ones.

---

## 📌 CORE RULES (set by user)

1. **Emoji functional, always paired.** Single lonely emoji = bad. Stack 2+ for compound meaning. (Source: user MEMORY.md)
2. **Brevity over completeness.** Bullets > paragraphs. If a note is >5 bullets, `/distill` should suggest splitting.
3. **"So what" first.** Every note should lead with the takeaway, not the setup.
4. **Plain markdown.** No proprietary syntax. Greppable forever.
5. **Never delete, always archive.** Wrong notes go to `archive/`, not `/dev/null`.

---

## 🗂️ ORGANIZATION DEFAULTS

```
Hierarchy depth:        3 levels max (folder → file → section)
File naming:            kebab-case (e.g., few-shot-examples.md)
Folder naming:          numbered prefix for ordered modules
Tag style:              #lowercase-kebab inline at end of section
Cross-link format:      [pattern name](path/to/file.md)
Date format:            YYYY-MM-DD
```

---

## 🎯 ROUTING RULES (where /sort puts things)

| Capture contains... | Routes to... |
|---|---|
| "module N" or "lecture" | `modules/0N-*/NOTES.md` |
| Pattern name (Persona, Few-Shot, etc.) | Append to that pattern's section |
| "quote:" prefix | `modules/0N-*/QUOTES.md` |
| "memorize:" or "remember:" | `MEMORIZE.md` |
| "insight:" or "realized" | `notes/insights.md` |
| Anything else | Sits in `inbox/` for user review |

---

## 🧠 LEARNED PREFERENCES (auto-updated by /evolve)

_Empty for now. As you use the system, /evolve writes observations here:_

```
Example future entries:
- 2026-04-22: User consistently uses #interview-prep tag for career-relevant notes.
  → Suggest /sort auto-add this tag when capture mentions "job", "resume", "interview".
- 2026-04-25: User rejected 4/5 suggested cross-links to Module 1.
  → Lower /connect's confidence threshold for old modules.
```

---

## 🃏 PATTERN-SPECIFIC RULES

_How user wants each prompt pattern documented as they learn it:_

```
Persona:        [name] | [what it's for] | [example I used]
Few-Shot:       [trigger] | [3-5 example block] | [why it worked]
CoT:            [trigger phrase] | [problem type] | [accuracy lift seen]
```

---

## ⚡ AGENT BEHAVIOR DEFAULTS

| Agent | Default behavior |
|---|---|
| /capture | Fast. No questions. Timestamp + raw text into `inbox/{YYYY-MM-DD}-capture.md` |
| /sort | Suggest a destination, ask one yes/no. Default = yes after 3 sec. |
| /connect | Surface top 3 cross-link candidates. User picks. |
| /distill | 3:1 compression by default. Ask before going harder. |
| /recall | First-letter recall mechanic (BibleMemory-style). 5 questions per session. |
| /map | Tree view with file sizes + last-modified. Run after every session. |
| /evolve | Silent observer. Writes a single new entry per session if a pattern is detected. |

---

## 🚫 NEVER DO

- Auto-organize without showing the move first
- Delete files (use `archive/`)
- Use emojis as decoration (only as functional markers)
- Generate notes the user didn't ask for
- "Helpful" reformatting that loses the user's voice
