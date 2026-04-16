---
name: distill
description: >
  Compresses verbose notes into essential bullets. Default 3:1 compression.
  Always preserves user's voice and tags. Saves the original to archive/
  before replacing.
---

# 💎 /distill — Compress Without Losing Soul

Long notes rot. Short notes survive. Your job is to compress without losing meaning, voice, or tags.

## STEP 1 — Read PREFERENCES.md

Note brevity rules and the user's voice patterns.

## STEP 2 — Identify target

Either:
- User specifies a file: `/distill modules/04-few-shot-examples/NOTES.md`
- User says "this section": ask which file + section heading

## STEP 3 — Pre-flight

1. Count source word count
2. Set target = source / 3 (default 3:1 compression)
3. Show user the source word count + target + ask "go?"

```
💎 Distill preview
   Source:    modules/04-few-shot-examples/NOTES.md (846 words)
   Target:    ~280 words (3:1 compression)
   Original:  archived to archive/distill/2026-04-16-few-shot-examples-NOTES.md
   
   Continue? [y/n/different ratio]
```

## STEP 4 — Distill

Apply these compression rules in order:

1. **Strip filler.** "I think that maybe..." → drop.
2. **Bullets > prose.** Convert paragraphs to bullets where possible.
3. **Preserve all tags** (`#kebab-case` survives intact).
4. **Preserve all code blocks** (don't compress code).
5. **Preserve all cross-links** (`[text](url)` survives intact).
6. **Preserve all quotes** (`> blockquote` lines).
7. **Preserve user's distinctive phrases** (catch-phrases, jokes).
8. **Section headers stay** — content under each shrinks.

## STEP 5 — Archive original

BEFORE writing the distilled version:
1. Copy source file to `archive/distill/{YYYY-MM-DD}-{filename}`
2. Add a footer to the archived copy: `<!-- distilled to {original path} on {date} -->`

## STEP 6 — Write distilled version

Replace source file content with distilled version. Add a top-of-file note:

```markdown
<!-- Distilled 2026-04-16 — original at archive/distill/2026-04-16-NOTES.md -->
```

## STEP 7 — Confirm

```
💎 Distilled.
   846 → 274 words (3.1:1)
   12 tags preserved | 3 cross-links preserved | 2 code blocks preserved
   Original at archive/distill/2026-04-16-few-shot-examples-NOTES.md
```

## RULES

- **NEVER distill without archiving first.** Reversibility is sacred.
- **NEVER touch tags, links, code, quotes.** Those carry the meaning.
- **NEVER add new content.** Compression only.
- **If the file is already short** (<200 words), refuse: "💎 File is already lean. No distill needed."
- **If user wants harder compression** (5:1, 10:1), warn that voice will be lost.

## EDGE CASES

- **File is mostly code:** distill only the prose between code blocks.
- **File has no clear sections:** propose a section split before distilling.
- **User rejects the distilled version:** restore from archive instantly.
