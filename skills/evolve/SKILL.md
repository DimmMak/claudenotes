---
name: evolve
description: >
  Silent observer that watches the user's choices across sessions and writes
  observed preferences to PREFERENCES.md. The system gets sharper over time.
  Never auto-acts on observations — only proposes new rules.
---

# 🌱 /evolve — The Learning Loop

This is the agent that makes ClaudeNotes > Notion. Every session, /evolve watches what you accepted, what you rejected, and writes a new line to PREFERENCES.md if a pattern is detected.

**This is the system literally getting sharper at organizing YOUR notes.**

## STEP 1 — Read PREFERENCES.md (CURRENT)

Note especially the "LEARNED PREFERENCES" section.

## STEP 2 — Scan recent activity

Look at the last 7 days of activity:
- `inbox/` history (what got captured)
- `archive/inbox/` (what got sorted, where to)
- `archive/distill/` (what got distilled, what ratio)
- `archive/recall/` (what got drilled, what missed)
- Git log (what got committed, when)

## STEP 3 — Detect patterns

Look for:

| Signal | Detected pattern |
|---|---|
| Same tag appears in 5+ recent captures | User cares about this topic, propose auto-tag rule |
| User rejected /sort suggestion 3+ times for same destination | Lower confidence for that route |
| User /distill ratio overrides 3+ times to same value | New default ratio |
| User /recall accuracy improves on a topic | Reduce drill frequency for that topic |
| User /capture at consistent time of day | Suggest a daily reminder pattern |
| User uses a specific catchphrase 3+ times | Add to "voice" preservation list |
| User connects two specific notes manually 2+ times | Permanent cross-link, suggest pinning |

## STEP 4 — Propose new rules

For each detected pattern, draft a new entry for PREFERENCES.md "LEARNED PREFERENCES" section:

```
🌱 EVOLVE — 3 observations this week

Observation 1:
  You captured 8 notes tagged #interview-prep this week.
  → Propose: /sort auto-suggests this tag when capture mentions
    "interview", "job", "resume", or "career."
  Accept? [y/n/refine]

Observation 2:
  You overrode /distill ratio to 5:1 four times.
  → Propose: change default distill ratio from 3:1 to 5:1.
  Accept? [y/n/refine]

Observation 3:
  You /recall accuracy on "Persona Pattern" hit 95% three sessions in a row.
  → Propose: drop Persona Pattern from default drill rotation.
  Accept? [y/n/refine]
```

## STEP 5 — Write accepted rules to PREFERENCES.md

For each accepted observation:
1. Append a dated line to PREFERENCES.md → "LEARNED PREFERENCES"
2. Format: `- {YYYY-MM-DD}: {observation}. → {action taken}.`
3. NEVER delete prior rules. Refinements add new lines.

Example:
```markdown
- 2026-04-22: User consistently uses #interview-prep tag for career notes.
  → /sort now auto-suggests this tag when capture mentions
    interview/job/resume/career.
```

## STEP 6 — Confirm

```
🌱 Evolved.
   Accepted: 2 new rules
   Rejected: 1 observation
   Total learned preferences: 7 (up from 5)
   
   System is now sharper at organizing your notes.
```

## RULES

- **NEVER auto-act on observations.** Always propose, always wait for accept.
- **NEVER delete prior LEARNED PREFERENCES.** History is context.
- **ONE evolution session per week max.** Pattern detection needs data.
- **If <7 days of activity:** reply "🌱 Need more data. Use the system more, then run /evolve again."
- **All other agents READ from LEARNED PREFERENCES** but only /evolve writes there.

## THE BET

After 30 sessions, PREFERENCES.md will have ~20 learned rules.
After 100 sessions, the system will organize your notes BETTER than you would manually.

**That's the difference between a SaaS and an agent factory.**

## EDGE CASES

- **Conflicting observations:** show both, let user pick which to encode.
- **Observation contradicts a CORE RULE:** flag it explicitly, ask user to override the core rule (high friction by design).
- **No patterns detected:** reply "🌱 Stable system. No new patterns this week. (That's fine.)"
