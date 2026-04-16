---
name: sort
description: >
  Routes captures from inbox/ into the right place in the hierarchy. Reads
  PREFERENCES.md routing rules. Suggests destination, asks one yes/no, moves.
  Empties the inbox without losing anything.
---

# 🗂️ /sort — Inbox Zero, Foolproof

You take entries from `inbox/` and route each one to the right destination based on `PREFERENCES.md` routing rules.

## STEP 1 — Read PREFERENCES.md

Especially the "ROUTING RULES" table.

## STEP 2 — Scan inbox

List every entry from `inbox/*-capture.md` files. Each entry = one timestamped block.

## STEP 3 — For each entry, propose a destination

Apply routing rules in order:

```
1. Match against PREFERENCES.md routing rules table
2. If multiple match, pick the most specific
3. If no rule matches, ask user where it should go
   AND propose a new rule for /evolve to consider
```

## STEP 4 — Ask one yes/no per entry

Format:

```
Entry 1/5:
> "14:32 — few-shot beats zero-shot when output format matters #pattern"

Suggested destination: modules/04-few-shot-examples/NOTES.md
                       (matched: rule "Pattern name → that pattern's section")

Confirm? [y/n/skip/new-rule]
```

User options:
- `y` — move it
- `n` — propose a different destination
- `skip` — leave in inbox
- `new-rule` — add a routing rule to PREFERENCES.md before moving

## STEP 5 — Move (don't copy)

When user confirms:
1. Append the entry to the destination file (with original timestamp preserved)
2. Remove from the inbox file
3. If inbox file is now empty, archive it to `archive/inbox/{date}.md`

## STEP 6 — Summarize

```
🗂️ Sort complete.
   Moved: 4 entries
   Skipped: 1 entry (still in inbox)
   New rules added: 1 (logged for /evolve review)
```

## RULES

- **Never move without confirmation.** Foolproof = explicit consent on each move.
- **Always preserve original timestamp** in the destination.
- **If destination file doesn't exist**, create it with a header.
- **Append, never overwrite.** Order matters.
- **Skipped entries stay in inbox** for the next sort session.

## EDGE CASES

- **Capture matches 2+ rules:** show both, let user pick.
- **No matching rule and user gives a new destination:** offer to add it as a rule.
- **Destination file is large (>500 lines):** suggest splitting or distilling first.
