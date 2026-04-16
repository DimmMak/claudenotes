# 🥊 COMBOS.md — Multi-Agent Notetaking Patterns

> Living catalog of proven sequences ("wombo combos") that improve notetaking quality, recall, and organization. Add new combos as you discover them.
>
> Each combo names the move sequence, when to use it, and what it produces. Treat this like a fighting-game frame data sheet — practiced sequences beat improvised ones every time.

---

## 🎯 How to read this file

```
COMBO NAME              ← what it's called
TRIGGER                 ← the situation that calls for it
SEQUENCE                ← agent moves, in order
PRODUCES                ← what you end up with
DIFFICULTY              ← S / A / B tier (frequency you'll use it)
```

---

## ⚡ S-TIER COMBOS (use weekly+)

### 🎬 LIVE LECTURE (the new flagship)
**Trigger:** About to watch a Vanderbilt lecture (or any browser-based video lecture).
**Setup once:** Install `tampermonkey/cowatch-coursera.user.js` (see `tampermonkey/README.md`).
**Sequence:**
```
1. 🟣 /cowatch — i'm watching, follow along
   (DITTO confirms tab + Tampermonkey pipeline)
2. cue throughout the lecture: "look" / "thoughts?" / "capture that" / "explain that"
3. when lecture ends: "done"
4. paste the suggested /capture commands DITTO gives you
5. 💪 /sort                 (route everything)
6. 🦅 /map                  (refresh sitemap)
7. [next morning] 🥄 /recall (drill what stuck)
```
**Produces:** Lecture content captured at the perfect moments (not your guess), with timestamps, with proactive callouts to your existing notes — then sorted, mapped, drilled.
**Difficulty:** S — replaces the old LECTURE-TO-MEMORY combo for any browser-watched lecture.

---


### 🥇 LECTURE-TO-MEMORY
**Trigger:** Just finished watching a Vanderbilt lecture.
**Sequence:**
```
1. ⚡ /capture x3-7  (during lecture, every aha moment)
2. 💪 /sort          (immediately after lecture)
3. 🦅 /map           (refresh sitemap)
[next morning]
4. 🥄 /recall        (drill what stuck)
```
**Produces:** Lecture content moves from "watched" → "understood" → "memorized" within 24 hours.
**Difficulty:** S — your bread-and-butter rotation.

---

### 🥈 INBOX ZERO RUN
**Trigger:** Inbox has 5+ entries piled up.
**Sequence:**
```
1. 💪 /sort          (route every entry, accept or override per-entry)
2. 🦅 /map           (verify everything landed correctly)
```
**Produces:** Empty inbox. Every thought routed. Sitemap reflects reality.
**Difficulty:** S — once or twice per study session.

---

### 🥉 MORNING MEMORY DRILL
**Trigger:** Start of any day. ~5 minutes available.
**Sequence:**
```
1. 🥄 /recall        (5 questions, first-letter mechanic)
2. 🦅 /map           (skim suggested actions for the day)
```
**Produces:** Active memory of yesterday's content + agenda for today.
**Difficulty:** S — daily lockout, like a WoW daily quest.

---

## 🔥 A-TIER COMBOS (use 1-2x per week)

### 🌐 KNOWLEDGE GRAPH BURST
**Trigger:** Finished a full module. Notes feel disconnected.
**Sequence:**
```
1. 🧲 /connect       (find cross-links across new + old notes)
2. 🦅 /map           (visualize the new web)
3. 🥄 /recall        (drill the freshly linked items)
```
**Produces:** Notes that were islands now form a graph. Recall accuracy jumps because cross-links create retrieval paths.
**Difficulty:** A — after every module finish.

---

### 💎 COMPRESSION PASS
**Trigger:** Any single file in the repo is >500 words.
**Sequence:**
```
1. 😴 /distill <fat-file>     (3:1 compression, archive original)
2. 🧲 /connect <fat-file>     (re-link, since structure changed)
3. 🦅 /map                    (verify file size went down)
```
**Produces:** Dense, re-readable file. Original safely in `archive/distill/`. Cross-links restored.
**Difficulty:** A — once a week, target the bloated file.

---

### 🌌 WEEKLY EVOLUTION (Sunday Ritual)
**Trigger:** Sunday evening. End of study week.
**Sequence:**
```
1. 💪 /sort          (final inbox cleanup)
2. 😴 /distill       (any file >500w gets compressed)
3. 🦅 /map           (full sitemap snapshot)
4. ⭐ /evolve        (system writes new PREFERENCES rules)
```
**Produces:** Clean repo + sharper system + permanent rules learned.
**Difficulty:** A — once per week. Sacred. Don't skip.

---

## 🛠️ B-TIER COMBOS (situational)

### 🧠 PRE-EXAM BLITZ
**Trigger:** Big quiz / cert test in 24-48 hours.
**Sequence:**
```
1. 🥄 /recall MEMORIZE.md           (drill the cheat sheet)
2. 🥄 /recall weak                  (drill items missed last 3 sessions)
3. 😴 /distill MEMORIZE.md          (compress further if needed)
4. 🥄 /recall                       (final pass)
```
**Produces:** Maximum retention on the most-tested material right before the exam.
**Difficulty:** B — only when stakes are real.

---

### 🔍 DEEP CROSS-LINK
**Trigger:** You realize two notes from different modules are actually about the same thing.
**Sequence:**
```
1. 🧲 /connect [file-A]             (manually invoke, top 3 candidates)
2. 🧲 /connect [file-B]             (same)
3. 🦅 /map                          (see the new triangle)
```
**Produces:** Bidirectional cross-references between previously isolated notes.
**Difficulty:** B — when you spot a connection your sleep-deprived brain didn't catch.

---

### 📥 CAPTURE STORM
**Trigger:** Long workshop / podcast / conversation. 30+ thoughts incoming.
**Sequence:**
```
1. ⚡ /capture x30   (no breaks, no thinking, no formatting)
[then later, separate session]
2. 💪 /sort          (route everything, expect 20% will need new rules)
3. ⭐ /evolve        (likely several new patterns detected)
```
**Produces:** Massive content captured at speed-of-thought. System gets smarter from the high-volume signal.
**Difficulty:** B — long-form events only.

---

### 🌱 PREFERENCE TUNING
**Trigger:** You've overridden the same agent suggestion 3+ times.
**Sequence:**
```
1. ⭐ /evolve        (force-run; should detect the pattern)
2. [accept the proposed new rule]
3. 💪 /sort          (verify the new rule applies correctly to next entry)
```
**Produces:** The system stops asking the same question because it learned your answer.
**Difficulty:** B — when you notice friction.

---

## 🎮 ULTRA COMBOS (the fancy stuff)

### 💀 THE FULL WOMBO
**Trigger:** End of any module. Maximum cleanup + maximum learning in one session.
**Sequence:**
```
1. ⚡ /capture x5    (final thoughts)
2. 💪 /sort          (drain inbox)
3. 🧲 /connect       (link aggressively)
4. 😴 /distill       (compress fat files)
5. 🦅 /map           (snapshot)
6. 🥄 /recall x10    (long drill session)
7. ⭐ /evolve        (let system learn from the burst)
```
**Produces:** A module's worth of content fully ingested, organized, linked, compressed, and committed to memory in ~30 minutes.
**Difficulty:** ULTRA — once per module finish (~6 times for the whole Vanderbilt course).

---

### 🐉 THE GIT-PUSH FLEX
**Trigger:** You want to flex the system to a recruiter.
**Sequence:**
```
1. 🦅 /map                          (regenerate snapshot)
2. ⭐ /evolve                       (update PREFERENCES one more time)
3. [git commit "module N complete"]
4. [git push]
5. [share GitHub link in cover letter]
```
**Produces:** Public artifact proving you don't just take courses — you build systems around them.
**Difficulty:** ULTRA — once per cert milestone.

---

## 📊 Combo Usage Tracker

Track which combos you actually run. Helps `/evolve` learn what's working.

| Combo | Times used | Last used | Working? |
|---|---|---|---|
| LECTURE-TO-MEMORY | 0 | — | ⬜ |
| INBOX ZERO RUN | 0 | — | ⬜ |
| MORNING MEMORY DRILL | 0 | — | ⬜ |
| KNOWLEDGE GRAPH BURST | 0 | — | ⬜ |
| COMPRESSION PASS | 0 | — | ⬜ |
| WEEKLY EVOLUTION | 0 | — | ⬜ |
| PRE-EXAM BLITZ | 0 | — | ⬜ |
| DEEP CROSS-LINK | 0 | — | ⬜ |
| CAPTURE STORM | 0 | — | ⬜ |
| PREFERENCE TUNING | 0 | — | ⬜ |
| THE FULL WOMBO | 0 | — | ⬜ |
| THE GIT-PUSH FLEX | 0 | — | ⬜ |

---

## ➕ Add a new combo

When you discover a useful pattern, add it here using this template:

```markdown
### COMBO NAME
**Trigger:** When this combo applies.
**Sequence:**
1. Agent move 1
2. Agent move 2
3. Agent move 3
**Produces:** What you end up with.
**Difficulty:** S / A / B / ULTRA
```

Then commit it. Future you will thank present you.

---

## 🥊 The one rule of combos

> **Never sort while capturing. Never capture while sorting.**
>
> Mixing the two phases is like trying to weave a Vanish into your Sinister Strike rotation — you'll fumble both. Keep capture (filler) and sort (finisher) in separate GCD windows.

That's optimal play. 🎮💎🃏
