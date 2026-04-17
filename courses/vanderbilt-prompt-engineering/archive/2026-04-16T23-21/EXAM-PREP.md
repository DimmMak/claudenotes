# 📝 EXAM-PREP — Vanderbilt Prompt Engineering

> Likely test questions with answers. The "what would they ask?"

---

## Q: What three levers does a prompt pull when generating output?

**A:** Pattern invocation (tapping into trained sequences), specificity injection (narrowing the generation space with concrete words), and structure imprinting (showing the output shape inside the prompt).

**Difficulty:** Medium

**Tests knowledge of:** [Pattern Invocation](PATTERNS.md#pattern-invocation), [Specificity Injection](PATTERNS.md#specificity-injection), [Structure Imprinting](PATTERNS.md#structure-imprinting)

**Source:** Module 1, Intuition About Prompts

**Common wrong answer:** "A prompt just asks a question and gets an answer" — treats the prompt as one-dimensional instead of multi-leveraged.

---

## Q: Why does "Mary had a little..." produce the same completion every time?

**A:** Because the phrase is part of a nursery rhyme that appeared thousands of times in the training data paired with "lamb." This creates a very strong trained pattern, locking the next-token prediction to the learned completion.

**Difficulty:** Easy

**Tests knowledge of:** [Pattern](GLOSSARY.md#pattern-m1-intuition), [Pattern Invocation](PATTERNS.md#pattern-invocation)

**Source:** Module 1, Intuition About Prompts

**Common wrong answer:** "Because the LLM is deterministic" — it's not. The consistency comes from pattern strength, not determinism.

---

## Q: How do you escape a strong trained pattern when you want novel output?

**A:** Inject a distinctive word that breaks the expected sequence before the pattern locks in. Example: replacing "Mary had a little" with "A girl named Mary had a microscopic" — the word "microscopic" forces the model off the lamb rails.

**Difficulty:** Medium

**Tests knowledge of:** [Pattern Escape](PATTERNS.md#pattern-escape)

**Source:** Module 1, Intuition About Prompts

**Common wrong answer:** "You tell it not to use the pattern" — direct instruction is weaker than breaking the pattern at the token level.

---

## Q: What's the effect of asking "Discuss Vanderbilt University" vs "Discuss Vanderbilt University with respect to Kirkland Hall"?

**A:** The generic query returns a Wikipedia-tier summary. The specific query pulls in specialized content about Kirkland Hall specifically. Adding a concrete entity narrows the generation space and activates training data associated with that entity.

**Difficulty:** Medium

**Tests knowledge of:** [Specificity Injection](PATTERNS.md#specificity-injection), ["With respect to..." power phrase](GLOSSARY.md#with-respect-to-m1-intuition)

**Source:** Module 1, Intuition About Prompts

**Common wrong answer:** "The outputs are the same, just longer" — they're structurally different, not longer.

---

## Q: Why does putting "Title: / Author: / Summary:" in a prompt influence the output format?

**A:** The LLM recognizes that structure as a common pattern from articles and papers in its training data. It attempts to replicate the shape in its response, filling in values under each key instead of producing a freeform paragraph.

**Difficulty:** Medium

**Tests knowledge of:** [Structure Imprinting](PATTERNS.md#structure-imprinting)

**Source:** Module 1, Intuition About Prompts

**Common wrong answer:** "The LLM can't follow structure without explicit instructions" — it often follows implicit structure just from showing the shape.

---
