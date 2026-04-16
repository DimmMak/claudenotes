---
name: recall
description: >
  Quizzes the user on their own notes using the first-letter recall mechanic
  from CodeRecall. Surfaces what's been forgotten. Tracks accuracy. Boosts
  spacing on weak items. Turns notes from passive storage into active memory.
---

# 🧠 /recall — Your Notes, As Active Memory

Notion stores. ClaudeNotes **drills**. This is what makes the system actually beat Notion.

Mechanic borrowed from CodeRecall (BibleMemory Pro first-letter recall, proven by cognitive science).

## STEP 1 — Read PREFERENCES.md

Note recall defaults (5 questions per session, first-letter mechanic).

## STEP 2 — Pick source

Default: 5 random items pulled from MEMORIZE.md + recently distilled notes + module NOTES.md.

User can specify:
- `/recall MEMORIZE.md` — drill only the cheat sheet
- `/recall module 4` — drill that module
- `/recall weak` — drill items missed last session

## STEP 3 — Run the drill

For each item, replace the answer's letters with underscores (preserving punctuation and spacing) but **never reveal the first letter**:

```
🧠 RECALL — Question 1 of 5

What does the Few-Shot Pattern do?

A: _ _ _ _ _   _ _ _ _ _ _   _ _ _ _ _ _ _   _ _   _ _ _ _   _ _ _   _ _ _ _ _ _.
   (Shows examples of input/output, lets the LLM figure out the pattern.)

Type the first letter of each word, separated by spaces.
Example answer: S e o i o p l t L f o t p
```

Wait for input. Check letter-by-letter.

## STEP 4 — Score

Per question:
- ✅ All letters correct → green flash, +10 pts
- ⚠️ Some correct → partial credit, show the missed words
- ❌ Asked for hint → reveal the answer, 0 pts
- 🔥 Streak of 5 correct → 1.5x multiplier on next

## STEP 5 — Track results

Append to `archive/recall/{YYYY-MM-DD}-results.md`:

```markdown
# Recall Session 2026-04-16

Questions: 5
Score: 38/50 (76%)
Streak best: 4
Weak items (drill again next time):
  - "Few-Shot Pattern definition" (got 60%)
  - "ReAct vs CoT difference" (asked for hint)
```

## STEP 6 — Suggest next action

```
🧠 Session done. 76% accuracy.
   📈 Up from 64% last week.
   ⚠️ 2 items flagged weak — they'll surface again next session.
   
   Run /recall weak to drill only the misses.
```

## RULES

- **Never show the first letter** — that's what the user types.
- **Always preserve punctuation/spacing** in the blanks.
- **5 questions max per session** (anti-burnout).
- **Track every session** — never delete results.
- **Default to spaced repetition** — weak items resurface 2-3x more often.

## EDGE CASES

- **No notes to drill from:** suggest `/capture` first.
- **User wants hints:** allow with `/hint` mid-session, but track it as a miss.
- **Long answers (>20 words):** ask user to confirm the source — long-form is hard to drill cleanly.
- **Code in answer:** skip the code block, drill only prose.

## INSPIRATION

This mechanic comes from CodeRecall (sister project). Cognitive science backing:
- Tulving (cued recall > free recall)
- Bjork (desirable difficulty)
- Karpicke & Roediger (testing effect)
