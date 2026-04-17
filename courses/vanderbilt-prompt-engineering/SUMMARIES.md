# 📑 SUMMARIES — Vanderbilt Prompt Engineering

> Populated by ingestion during cowatch sessions. One paragraph per lecture.

---

## Intuition About Prompts (M1 — Intuition Lecture)

**What was covered:**
Jules walks through the mechanical model of how prompts actually work inside an LLM. Uses four worked examples (Mary had a little lamb, microscopic/Mary variant, Vanderbilt/Kirkland Hall specificity, Title/Author structure) to demonstrate three distinct levers a prompt pulls: pattern invocation, specificity injection, and structure imprinting.

**Main thesis:**
Every prompt is either tapping INTO a strong trained pattern or trying to ESCAPE one. The more specific your words, the more specific the output. Structure you show in the prompt becomes structure in the response. These three levers are the mechanical foundation under every named pattern later in the course.

**Time invested:** ~10-15 min

**Source:** Module 1, "Intuition About Prompts"

---

## Persona Pattern (M1 — Persona Lecture)

**What was covered:**
Jules introduces the Persona Pattern — arguably the most powerful named pattern in the course. Walks through four escalating examples (skeptic computer scientist, nine-year-old skeptic, hacked Linux terminal, Mary's lamb) to show how "Act as [persona]" loads massive context — vocabulary, tone, knowledge, output format — into just a few tokens. Closes with the virtual panel application (one prompt per perspective) and notes that base LLM behavior is itself persona-configured by system prompts.

**Main thesis:**
If you know who or what you'd go to in the real world for an answer, the persona pattern lets you access that perspective without specifying its vocabulary, format, or knowledge. "Act as [persona], provide outputs that persona would provide" is an information-dense shortcut that buys back prompt space for actual content.

**Time invested:** ~10-15 min

**Source:** Module 1, "Persona Pattern"

---

## Fundamental Contextual Statements (M1 — Reading)

**What was covered:**
A foundational reading that defines the META-framework used to describe ALL prompt patterns throughout the course. Introduces "fundamental contextual statements" — the minimal set of written descriptions that communicate the essential ideas behind any prompt pattern. Uses the "Helpful Assistant Pattern" as an illustrative example, breaking it into 3 fundamental contextual statements and showing two different prompt rewordings that each implement the same pattern.

**Main thesis:**
A prompt pattern is not its exact wording — it is the set of fundamental ideas that MUST be communicated. Different surface wordings can implement the same pattern as long as they all convey the same underlying contextual statements. This separation (pattern = essence, prompt = implementation) is what makes patterns reusable and teachable.

**Time invested:** ~5 min (short reading)

**Source:** Module 1, "Prompt Patterns" (reading, not video)

---
