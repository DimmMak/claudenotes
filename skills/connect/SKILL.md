---
name: connect
description: >
  Finds semantic cross-links between a new note and existing notes. Surfaces
  top 3 candidates. User picks. Inserts inline links in markdown. Builds the
  knowledge graph automatically.
---

# 🔗 /connect — Build the Knowledge Graph

Notion has @mentions. ClaudeNotes has YOU writing freely and an agent finding the links FOR you.

## STEP 1 — Read PREFERENCES.md

Note the cross-link format rule (default: `[name](path/to/file.md)`).

## STEP 2 — Identify the source

Either:
- User specifies a file/section: `/connect modules/04-few-shot-examples/NOTES.md`
- User says "connect last capture" → use most recent inbox entry
- User says "connect everything new" → all entries in inbox + last 3 days of changed files

## STEP 3 — Search for candidates

For each source note, scan the rest of the repo (markdown only):
1. Extract key terms from the source (proper nouns, pattern names, distinctive phrases)
2. Grep for those terms across `modules/`, `MEMORIZE.md`, `notes/`, `archive/`
3. Score each match by: term frequency × (recency boost) × (proximity to existing links)
4. Surface the top 3 candidates

## STEP 4 — Present candidates

```
🔗 Source: modules/04-few-shot-examples/NOTES.md (line 12)
   "...few-shot beats zero-shot when output format matters..."

Top cross-link candidates:

  [1] modules/03-prompt-patterns-1/NOTES.md → "Persona Pattern" section
      Why: both discuss output format constraints
      
  [2] MEMORIZE.md → "Patterns Cheat Sheet" / Few-Shot row
      Why: this insight should be in the cheat sheet
      
  [3] modules/06-prompt-patterns-3/NOTES.md → "Template Pattern" section
      Why: templates and few-shot both enforce format

Pick: [1] [2] [3] [all] [none] [show more]
```

## STEP 5 — Insert links

For each accepted link:
1. Insert the link inline at the source location
2. ALSO insert a back-reference at the destination ("← see also: ...")
3. Bidirectional by default

## STEP 6 — Confirm

```
🔗 Linked: 2 connections made
   Forward + back-references added
   Run /map to see updated graph
```

## RULES

- **Suggest, don't insert.** User confirms every link.
- **Bidirectional always.** A link without a back-reference is half a link.
- **Don't link to self.** Skip same-file matches.
- **Threshold:** if no candidate scores above 30% confidence, say "no strong matches" instead of listing weak ones.

## EDGE CASES

- **Source has no distinctive terms:** ask user to highlight what to connect ON.
- **Candidate file already linked from source:** mark as "[already linked]" and deprioritize.
- **Circular link request:** allow but note it.
