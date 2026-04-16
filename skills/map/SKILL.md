---
name: map
description: >
  Regenerates MAP.md — a visual sitemap of every note in the repo. Tree view,
  file sizes, last-modified dates, link counts, distill status. Run after
  every session to keep the bird's-eye view current.
---

# 🗺️ /map — Bird's-Eye View, Always Current

Notion's sitemap is a sidebar you build manually. ClaudeNotes regenerates yours from disk in 3 seconds.

## STEP 1 — Read PREFERENCES.md

Note hierarchy depth + naming conventions.

## STEP 2 — Walk the tree

Recursively scan the repo, ignoring:
- `.git/`
- `archive/` (referenced separately at the bottom)
- `inbox/` (referenced separately as "pending")
- `skills/` (referenced separately as "system")

For each markdown file found, capture:
- Path
- Size (lines or words)
- Last modified date
- Link count (out + back-references)
- Distill status (✓ if "Distilled" footer present)
- Tag count

## STEP 3 — Render MAP.md

```markdown
# 🗺️ MAP — Auto-generated {YYYY-MM-DD HH:MM}

## 📌 Pinned

- MEMORIZE.md          (124w | mod 2d ago | 5 links | 8 tags)
- PREFERENCES.md       (412w | mod 1h ago | 0 links | 0 tags)
- PROGRESS.md          (340w | mod 1w ago | 0 links | 0 tags)

## 📚 Modules

modules/
├── 01-course-intro/
│   ├── NOTES.md       (220w | mod 3d ago | 4 links | 2 tags)
│   └── QUOTES.md      (45w  | mod 3d ago | 0 links | 0 tags)
├── 02-intro-to-prompts/
│   └── NOTES.md       (180w | mod 5d ago | 2 links | 1 tag)
├── 03-prompt-patterns-1/
│   └── NOTES.md       (520w | mod 1d ago | 8 links | 5 tags) 💎
├── 04-few-shot-examples/
│   └── NOTES.md       (340w | mod 1h ago | 6 links | 4 tags)
├── 05-prompt-patterns-2/  [empty]
└── 06-prompt-patterns-3/  [empty]

## 📥 Inbox

inbox/
└── 2026-04-16-capture.md  (3 entries — run /sort)

## 🗄️ Archive

archive/
├── distill/   (4 files)
└── recall/    (12 sessions logged)

## 📊 Stats

Total notes:           14
Total words:           4,820
Cross-links:           37
Distilled files:       3 💎
Files needing distill: 2 (>500w and not yet distilled)
Pending inbox items:   3
Days since last /sort: 1
Days since last /recall: 4

## ⚡ Suggested next actions

  1. 🗂️ /sort — 3 inbox items pending
  2. 🧠 /recall — last session 4 days ago, momentum slipping
  3. 💎 /distill modules/03-prompt-patterns-1/NOTES.md (520w, getting long)
```

## STEP 4 — Write MAP.md to repo root

Overwrite `MAP.md` (this file is auto-generated, no archive needed).

## STEP 5 — Confirm

```
🗺️ Map updated. 14 notes, 4,820 words, 37 cross-links.
   3 suggested actions queued.
```

## RULES

- **Always overwrite MAP.md** — it's a snapshot, not history.
- **Sort folders alphabetically.** Sort files within folders by last-modified DESC.
- **Suggested actions section is dynamic** — change based on actual repo state.
- **Distill marker (💎)** appears for files with the "Distilled" footer.
- **Files >500w with no distill marker** appear in "needs distill" list.

## EDGE CASES

- **Empty repo:** show empty tree with "Run /capture to get started."
- **Very deep nesting:** truncate at depth 4 with `[...]` indicator.
- **Binary files in repo:** skip, don't list.
