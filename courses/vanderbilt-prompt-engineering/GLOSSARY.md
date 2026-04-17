# 📖 GLOSSARY — Vanderbilt Prompt Engineering

> Key terms with definitions.

---

## Pattern (M1 Intuition)

**Definition:** A recurring sequence of words the LLM saw many times during training. When you feed the first part, the model has a strong tendency to continue with the learned completion.

**Why it matters:** If you recognize strong trained patterns, you can either INVOKE them (for consistent output) or ESCAPE them (for novel output). Most prompt engineering is pattern management.

**First introduced:** Module 1, Intuition About Prompts

**Cross-links:** [Pattern Invocation](PATTERNS.md#pattern-invocation), [Pattern Escape](PATTERNS.md#pattern-escape)

---

## Specificity (M1 Intuition)

**Definition:** The degree to which the words in a prompt narrow the generation space. Concrete nouns, named entities, and precise technical terms score high; generic words score low.

**Why it matters:** Generic input → generic output. Specific input → specific output. Most users accept mediocre answers because they ask mediocre questions.

**First introduced:** Module 1, Intuition About Prompts (Vanderbilt/Kirkland Hall example)

**Cross-links:** [Specificity Injection](PATTERNS.md#specificity-injection)

---

## Structure Imprinting (M1 Intuition)

**Definition:** The technique of showing the LLM the output shape inside the prompt itself (e.g., "Title: / Author: / Summary:"). The model tries to replicate that structure in its response.

**Why it matters:** Formats that would take a long paragraph to describe can be communicated in 3 words by just showing the shape.

**First introduced:** Module 1, Intuition About Prompts

**Cross-links:** [Structure Imprinting](PATTERNS.md#structure-imprinting), [Template Pattern](PATTERNS.md#template-pattern) (later in course)

---

## "With respect to..." (M1 Intuition)

**Definition:** A power phrase that forces specificity by narrowing a broad topic to a specific sub-topic.

**Why it matters:** Adds specificity without requiring the user to rewrite the whole prompt. Low effort, high impact.

**First introduced:** Module 1, Intuition About Prompts (Vanderbilt/Kirkland Hall example)

**Cross-links:** [Specificity](GLOSSARY.md#specificity)

---

## Persona (M1 Persona)

**Definition:** A role, point-of-view, or character the LLM is instructed to adopt for its responses. Can be a person (accountant), a perspective (skeptic), or even an inanimate system (Linux terminal, API response).

**Why it matters:** A persona packs vocabulary, tone, output format, and domain knowledge into a 2-3 word invocation. Saves massive prompt space vs describing these dimensions individually.

**First introduced:** Module 1, Persona Pattern

**Cross-links:** [Persona Pattern](PATTERNS.md#persona-pattern-m1-persona), [Virtual Panel Pattern](PATTERNS.md#virtual-panel-pattern-m1-persona)

---

## Virtual Panel (M1 Persona)

**Definition:** A composition of multiple persona prompts, each analyzing the same question from a different expert perspective (e.g., security expert, CFO, employee).

**Why it matters:** Simulates the "committee of experts" approach without assembling actual experts. Each persona independently surfaces blind spots the others miss.

**First introduced:** Module 1, Persona Pattern

**Cross-links:** [Virtual Panel Pattern](PATTERNS.md#virtual-panel-pattern-m1-persona), [Persona](#persona-m1-persona)

---

## Fundamental Contextual Statements (M1 Reading)

**Definition:** The minimal set of written descriptions that communicate the essential ideas behind a prompt pattern. The "required ingredients" of the pattern — independent of any specific wording.

**Why it matters:** A pattern is the ESSENCE, not the exact words. Two prompts using completely different phrasing can implement the same pattern as long as they both convey the same fundamental contextual statements. This is the meta-framework used to describe every pattern in this course.

**First introduced:** Module 1, "Prompt Patterns" reading

**Cross-links:** [Helpful Assistant Pattern](PATTERNS.md#helpful-assistant-pattern-m1-reading), [Persona Pattern](PATTERNS.md#persona-pattern-m1-persona)

---

## Helpful Assistant Pattern (M1 Reading)

**Definition:** A named prompt pattern designed to keep an AI assistant helpful, responsive, and non-hostile. Documents the behavior via 3 fundamental contextual statements.

**Why it matters:** Illustrative example of how ALL patterns are documented in the course — via fundamental contextual statements rather than fixed wording. Also directly useful as a production prompt pattern for customer-facing assistants.

**First introduced:** Module 1, "Prompt Patterns" reading

**Cross-links:** [Helpful Assistant Pattern (pattern)](PATTERNS.md#helpful-assistant-pattern-m1-reading), [Fundamental Contextual Statements](#fundamental-contextual-statements-m1-reading)

---
