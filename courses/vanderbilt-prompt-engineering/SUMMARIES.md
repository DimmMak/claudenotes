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

## Prompts as Conversations (M1 — Iterative Refinement Lecture)

**What was covered:**
Jules reframes prompting from "one-shot questions" to "ongoing conversations." Uses the Michelangelo metaphor — a sculptor doesn't hit the stone once and give up; he iteratively chisels. Extended worked example: an entire conversation designing a line-following robot, hitting multiple roadblocks (can't do 3D models via chat → pivot to G-code → doesn't work → pivot to Python generating STL files; can't generate images → pivot to Graphviz text-based diagrams). Demonstrates how to problem-solve AROUND dead ends by reframing the task in a different representation.

**Main thesis:**
The power of LLMs comes from CONVERSATION, not single-shot answers. When a prompt hits a dead end, you don't quit — you reframe, pivot, ask follow-ups, give feedback, and try alternative representations. Every response becomes fuel for the next prompt. The whole thread IS the prompt.

**Time invested:** ~12 min

**Source:** Module 1, "Prompts are a Tool for Repeated Use" / "Prompts are Conversations"

---

## Prompt Size Limitations (M1 — Token Budget Lecture)

**What was covered:**
Jules demonstrates that every LLM has a finite context window by pasting a full French Revolution Wikipedia article into ChatGPT and hitting the "too long" error. Introduces the content-editor mindset — the user must fit information into a word/token budget like a writer fitting into a page limit. Presents 3 strategies for working around the limit: (1) QUERY (select relevant subset), (2) FILTER (remove extraneous), (3) SUMMARIZE (compress while preserving key info). Key twist: TARGETED summarization preserves specific aspects ("summarize in one sentence preserving information about numbers of people") while generic summarization loses them.

**Main thesis:**
Context injection isn't unlimited. You can't dump everything into the prompt. The user's job is to CURATE context — select, filter, compress — so the LLM gets what it needs without overflow. Targeted summarization (compression with a preservation goal) is the most powerful technique because you control what survives the compression.

**Time invested:** ~10 min

**Source:** Module 1, "Prompt Size Limitations"

---

## Introducing New Information (M1 — Context Injection Lecture)

**What was covered:**
Jules demonstrates how to reason about content the LLM wasn't trained on by injecting the information directly into the prompt. Uses the "birds outside my house" example three times — (1) no data → LLM refuses, (2) historical monthly data → LLM answers 210 for March, (3) data + hidden rule ("house is covered by a glass dome, animals live forever") → LLM correctly follows the injected rule to answer 120. Previews RAG (retrieval-augmented generation) as the future pattern for most LLM applications.

**Main thesis:**
Any fact the model needs to reason must live in the prompt — not only DATA (numbers, documents, private info) but also HIDDEN ASSUMPTIONS (unusual rules, organizational context, constraints). If the info isn't in the prompt, the LLM can't use it. This principle underlies every search + chat application going forward.

**Time invested:** ~12 min

**Source:** Module 1, "Introducing New Information to a Large Language Model"

---

## Persona Pattern — Formal Documentation (M1 — Paper Reading)

**What was covered:**
The academic paper's formal documentation of the Persona Pattern using the 2-statement fundamental contextual statement framework: (1) Act as Persona X, (2) Perform task Y. Provides five applied examples spanning human roles (speech-language pathologist, nutritionist, gourmet chef), inanimate systems (hacked Linux terminal), and characters (Mary's lamb) — demonstrating the pattern's range.

**Main thesis:**
Persona Pattern is the simplest and most composable pattern in the catalog — TWO statements cover every case. The persona slot accepts any entity with a recognizable output shape: profession, perspective, system, character. Everything else (vocabulary, tone, format) is implied by the persona itself.

**Time invested:** ~3 min (short reading)

**Source:** Module 1, Paper: Persona Pattern formal section

---

## Prompt Patterns Paper — Abstract (M1 — Academic Reading)

**What was covered:**
Abstract of the academic paper that underpins the course's pattern framework. Defines prompt engineering as a skill for conversing with LLMs, frames prompts as instructions + a form of programming, and draws an explicit analogy to software design patterns (reusable solutions to common problems in a particular context). Announces three paper contributions: (1) a framework for DOCUMENTING prompt patterns, (2) a CATALOG of tested patterns, (3) an explanation of how prompts can COMBINE multiple patterns.

**Main thesis:**
Prompt patterns are the AI-era equivalent of software patterns — reusable templates that encode proven solutions. The course's entire taxonomy (Persona, Few-Shot, CoT, etc.) fits inside this framework, and patterns can be composed together just like software components.

**Time invested:** ~3 min (reading an abstract)

**Source:** Module 1, "A Prompt Pattern Catalog to Enhance Prompt Engineering" paper (abstract)

---

## Fundamental Contextual Statements (M1 — Reading)

**What was covered:**
A foundational reading that defines the META-framework used to describe ALL prompt patterns throughout the course. Introduces "fundamental contextual statements" — the minimal set of written descriptions that communicate the essential ideas behind any prompt pattern. Uses the "Helpful Assistant Pattern" as an illustrative example, breaking it into 3 fundamental contextual statements and showing two different prompt rewordings that each implement the same pattern.

**Main thesis:**
A prompt pattern is not its exact wording — it is the set of fundamental ideas that MUST be communicated. Different surface wordings can implement the same pattern as long as they all convey the same underlying contextual statements. This separation (pattern = essence, prompt = implementation) is what makes patterns reusable and teachable.

**Time invested:** ~5 min (short reading)

**Source:** Module 1, "Prompt Patterns" (reading, not video)

---
