# 🃏 PATTERNS — Vanderbilt Prompt Engineering

> Named frameworks and formulas. The "how" of the course.

---

## Pattern Invocation (M1 Intuition)

**Formula:** Feed the LLM the opening of a strongly-trained sequence → it completes along the learned pattern.

**What it does:** Gets consistent, predictable output by tapping into a pattern the model saw many times during training.

**When to use it:** When you want reliable, repeatable output for a well-known structure (nursery rhymes, poem formats, common code templates, boilerplate language).

**Worked example:** See [Mary Had a Little Lamb](EXAMPLES.md#mary-had-a-little-lamb-m1-intuition)

**Common pitfalls:** If you DON'T want the trained completion, pattern invocation traps you into it. Break the pattern with specific words ("microscopic" instead of "lamb" territory).

**Source:** Module 1, Intuition About Prompts

**Cross-links:** [Pattern Escape](#pattern-escape), [Specificity Injection](#specificity-injection)

---

## Pattern Escape (M1 Intuition)

**Formula:** Introduce a distinctive word BEFORE the pattern would lock in to force the LLM off the trained completion rails.

**What it does:** Breaks away from strong common patterns when you want novel output instead of the expected completion.

**When to use it:** When a familiar phrase would trigger a locked-in response but you want something original.

**Worked example:** See [Microscopic Mary Variant](EXAMPLES.md#microscopic-mary-variant-m1-intuition)

**Common pitfalls:** Adding weak specificity doesn't escape — needs a genuinely distinctive word ("microscopic" > "girl named Mary" on its own).

**Source:** Module 1, Intuition About Prompts

**Cross-links:** [Pattern Invocation](#pattern-invocation)

---

## Specificity Injection (M1 Intuition)

**Formula:** `[Broad query] with respect to [specific entity/aspect]`

**What it does:** Narrows a generic query into a focused one. The specific term becomes the keyword that pulls in specialized training data.

**When to use it:** Whenever the generic version of your question would return a Wikipedia-tier summary and you want depth.

**Worked example:** See [Vanderbilt + Kirkland Hall](EXAMPLES.md#vanderbilt--kirkland-hall-m1-intuition)

**Common pitfalls:** Specificity must be EARNED by training data — if you name an entity the LLM doesn't know, you get worse output, not better.

**Source:** Module 1, Intuition About Prompts

**Cross-links:** [Specificity](GLOSSARY.md#specificity), [Persona Pattern](#persona-pattern) (later)

---

## Structure Imprinting (M1 Intuition)

**Formula:** Show the exact output structure in the prompt. The LLM tries to replicate the shape.

**Example syntax:**
```
Title: [blank]
Author: [blank]
Summary: [blank]
```

**What it does:** Communicates format expectations cheaply. Saves hundreds of words of format instructions.

**When to use it:** When output format matters (reports, structured data, consistent layouts).

**Worked example:** See [Title/Author Structure](EXAMPLES.md#titleauthor-structure-m1-intuition)

**Common pitfalls:** LLM may not follow the structure perfectly on the first try — sometimes needs a re-run or an explicit instruction alongside the structure.

**Source:** Module 1, Intuition About Prompts

**Cross-links:** [Template Pattern](#template-pattern) (later in course, formal version)

---
