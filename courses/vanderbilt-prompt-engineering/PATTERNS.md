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

## Persona Pattern (M1 Persona)

**Formula:** `Act as [persona], provide outputs that that persona would provide`

**What it does:** Replaces the LLM's default "helpful assistant" framing with a specific role. Unlocks the persona's vocabulary, tone, knowledge base, and typical output format — all from a 2-3 word invocation.

**When to use it:** When you know who/what you'd go to in the real world for an answer but don't want to spell out their format or vocabulary. Also useful when you need a specific point of view (skeptical, optimistic, domain-expert).

**Worked example:** See [Skeptic Computer Scientist](EXAMPLES.md#skeptic-computer-scientist-m1-persona)

**Common pitfalls:** Naming a persona the LLM has thin training data on (obscure role, niche character) degrades output. Also: persona can override some safety guardrails — in the hacked-Linux-terminal demo the model initially refused, then complied once framed as "act as."

**Source:** Module 1, Persona Pattern

**Cross-links:** [Virtual Panel Pattern](#virtual-panel-pattern-m1-persona), [Persona](GLOSSARY.md#persona-m1-persona), [Specificity Injection](#specificity-injection-m1-intuition) (stacking specificity onto persona — "skeptic well-versed in computer science")

---

## Virtual Panel Pattern (M1 Persona)

**Formula:** Run the same question through N separate persona prompts, each adopting a distinct expert role. Combine outputs.

**Example syntax:**
```
Prompt 1: Act as a security expert. Analyze [decision].
Prompt 2: Act as a CFO. Analyze [decision].
Prompt 3: Act as an employee affected by [decision].
```

**What it does:** Surfaces blind spots — each persona catches issues the others miss. Approximates a committee of advisors without assembling one.

**When to use it:** High-stakes decisions where single-perspective analysis is risky — strategy docs, security reviews, launch plans, hiring decisions.

**Worked example:** Not directly demoed in this lecture — Jules describes the pattern at the close. Try it by running any real decision through 3+ relevant personas.

**Common pitfalls:** Overlapping personas produce redundant output. Pick personas that would genuinely disagree (security vs speed vs cost) rather than three flavors of the same role.

**Source:** Module 1, Persona Pattern (closing section)

**Cross-links:** [Persona Pattern](#persona-pattern-m1-persona), [Virtual Panel](GLOSSARY.md#virtual-panel-m1-persona)

---

## Pattern Composition (M1 Paper)

**Formula:** Combine 2+ named patterns within a single prompt to solve compound problems.

```
[Persona Pattern statements]
+
[Few-Shot Examples]
+
[Chain-of-Thought trigger]
= compound prompt solving a multi-dimensional problem
```

**What it does:** Lets you stack pattern capabilities. One pattern gives role + vocabulary (Persona). Another gives format (Few-Shot). Another gives reasoning (CoT). Combined = richer output than any pattern alone.

**When to use it:** When a single pattern doesn't fully solve your problem. Whenever you catch yourself wanting "X AND Y" behavior.

**Worked example:** Not yet in course — the paper promises this will be shown. Likely in Module 5-6 (Prompt Patterns II/III).

**Common pitfalls:**
- Stacking patterns that contradict each other (e.g., "be concise" + "show full reasoning")
- Loading too many patterns until the prompt becomes cluttered — quality over quantity
- Forgetting pattern ORDER matters (Persona before task usually works better than after)

**Source:** Module 1, "A Prompt Pattern Catalog" paper (abstract)

**Cross-links:** [Pattern Composition (glossary)](GLOSSARY.md#pattern-composition-m1-paper), [Persona Pattern](#persona-pattern-m1-persona), [Helpful Assistant Pattern](#helpful-assistant-pattern-m1-reading)

---

## Helpful Assistant Pattern (M1 Reading)

**Formula (fundamental contextual statements):**
```
1. You are a helpful AI assistant.
2. You will answer my questions or follow my instructions whenever you can.
3. You will never answer my questions in a way that is insulting, derogatory, or uses a hostile tone.
```

**What it does:** Anchors the LLM's default behavior toward helpfulness while blocking hostile/derogatory output. Prevents the model from refusing in unhelpful ways or snapping back with attitude.

**When to use it:** As a baseline system prompt for any customer-facing AI assistant, chatbot, or productivity tool. Combine with more specific patterns (Persona, etc.) for richer behavior.

**Worked examples:** See [Skilled AI Assistant Wording](EXAMPLES.md#skilled-ai-assistant-wording-m1-reading) and [ChatAmazing Wording](EXAMPLES.md#chatamazing-wording-m1-reading)

**Common pitfalls:**
- Relying only on helpful-tone statements without also specifying what the assistant should NOT do — the "never insulting" clause is load-bearing
- Forgetting that this is a BASELINE pattern — it gets stacked with task-specific patterns, not used alone
- Treating wording as fixed — the 3 fundamental statements are what matter, not the exact phrasing

**Source:** Module 1, "Prompt Patterns" reading

**Cross-links:** [Fundamental Contextual Statements](GLOSSARY.md#fundamental-contextual-statements-m1-reading), [Persona Pattern](#persona-pattern-m1-persona)

---
