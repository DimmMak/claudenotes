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
