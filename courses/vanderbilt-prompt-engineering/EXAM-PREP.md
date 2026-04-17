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

## Q: What is the Persona Pattern formula?

**A:** `Act as [persona], provide outputs that that persona would provide.` The `[persona]` slot can be a role (accountant), a perspective (skeptic), a character (Mary's lamb), or an inanimate system (Linux terminal).

**Difficulty:** Easy

**Tests knowledge of:** [Persona Pattern](PATTERNS.md#persona-pattern-m1-persona)

**Source:** Module 1, Persona Pattern

**Common wrong answer:** "Pretend you are X" — close, but the course emphasizes "act as" specifically, and the second clause (what output the persona would produce) is what locks the pattern in.

---

## Q: Why is the persona pattern called "information-dense"?

**A:** A 2-3 word persona invocation replaces paragraphs of description — vocabulary, tone, knowledge base, and output format are all implied. Describing each dimension individually would consume valuable prompt space that could hold new information instead.

**Difficulty:** Medium

**Tests knowledge of:** [Persona Pattern](PATTERNS.md#persona-pattern-m1-persona)

**Source:** Module 1, Persona Pattern

**Common wrong answer:** "Because the persona has lots of training data" — partly true, but the density claim is about the PROMPT being short, not the data being large.

---

## Q: How does the "nine-year-old skeptic" example prove a persona changes more than just tone?

**A:** The nine-year-old response references movies and commonsense doubts, not research papers or technical arguments. Same stance (skeptical) — different knowledge ceiling and reasoning style. The persona shapes BOTH tone AND the knowledge base the model draws from.

**Difficulty:** Hard

**Tests knowledge of:** [Persona Pattern](PATTERNS.md#persona-pattern-m1-persona)

**Source:** Module 1, Persona Pattern

**Common wrong answer:** "It proves the persona just adds slang or simpler words" — misses the shift in knowledge base and argument style.

---

## Q: What is a Virtual Panel and when would you use it?

**A:** Several persona prompts run in parallel, each analyzing the same decision from a different expert viewpoint (security expert, CFO, employee). Use it for high-stakes decisions where single-perspective analysis is risky — the personas surface blind spots each other miss.

**Difficulty:** Medium

**Tests knowledge of:** [Virtual Panel Pattern](PATTERNS.md#virtual-panel-pattern-m1-persona), [Virtual Panel](GLOSSARY.md#virtual-panel-m1-persona)

**Source:** Module 1, Persona Pattern (closing section)

**Common wrong answer:** "Ask ChatGPT to consider multiple viewpoints in one prompt" — weaker. Separating personas into distinct prompts gives each one its own full context budget.

---

## Q: Why can "act as the Linux terminal for a computer that has been hacked" produce coherent terminal output?

**A:** Persona patterns aren't limited to human roles. Any system with a distinctive output shape that appears densely in training data — a terminal, an API response, a log file — can be invoked as a persona. The LLM has seen enough of the format to reproduce it plausibly.

**Difficulty:** Medium

**Tests knowledge of:** [Persona Pattern](PATTERNS.md#persona-pattern-m1-persona)

**Source:** Module 1, Persona Pattern

**Common wrong answer:** "Because the LLM can actually execute terminal commands" — it can't. It reproduces the shape from training data.

---

## Q: What are fundamental contextual statements?

**A:** The minimal set of written descriptions that communicate the essential ideas behind a prompt pattern. They define the pattern's ESSENCE, independent of any specific wording. Two prompts with different phrasing can implement the same pattern if they convey the same fundamental statements.

**Difficulty:** Easy

**Tests knowledge of:** [Fundamental Contextual Statements](GLOSSARY.md#fundamental-contextual-statements-m1-reading)

**Source:** Module 1, "Prompt Patterns" reading

**Common wrong answer:** "The exact wording of a prompt" — wrong. The wording can vary; the statements themselves are what define the pattern.

---

## Q: Name the 3 fundamental contextual statements of the Helpful Assistant Pattern.

**A:**
1. You are a helpful AI assistant.
2. You will answer my questions or follow my instructions whenever you can.
3. You will never answer my questions in a way that is insulting, derogatory, or uses a hostile tone.

**Difficulty:** Medium

**Tests knowledge of:** [Helpful Assistant Pattern](PATTERNS.md#helpful-assistant-pattern-m1-reading)

**Source:** Module 1, "Prompt Patterns" reading

**Common wrong answer:** Omitting the "never hostile" statement and only including helpfulness. The non-hostile clause is load-bearing — it prevents the assistant from refusing in a snarky way.

---

## Q: Why can two prompts with different wordings implement the same pattern?

**A:** Because a pattern is defined by its fundamental contextual statements (essential ideas), not by exact wording. As long as both prompts convey the same underlying statements, they produce the same behavior. This separation makes patterns reusable, teachable, and language-independent.

**Difficulty:** Medium

**Tests knowledge of:** [Fundamental Contextual Statements](GLOSSARY.md#fundamental-contextual-statements-m1-reading), [Helpful Assistant Pattern](PATTERNS.md#helpful-assistant-pattern-m1-reading)

**Source:** Module 1, "Prompt Patterns" reading

**Common wrong answer:** "Because LLMs are flexible" — partial truth, but misses the architectural point. The SHARED patterns are what matter, not the model's tolerance for variation.

---

## Q: What software-engineering concept are prompt patterns analogous to?

**A:** Software design patterns (the "Gang of Four" tradition) — reusable solutions to common problems in a particular context. The paper explicitly frames prompt patterns as the AI-era parallel: catalog-style, composable, domain-adaptable.

**Difficulty:** Easy

**Tests knowledge of:** [Prompt Pattern (formal definition)](GLOSSARY.md#prompt-pattern-formal-definition-m1-paper)

**Source:** Module 1, "A Prompt Pattern Catalog" paper (abstract)

**Common wrong answer:** "They're analogous to regex patterns" — wrong. Regex is for MATCHING text. Prompt patterns are for STRUCTURING behavior (which parallels how software design patterns structure code).

---

## Q: What are the three contributions claimed by the Prompt Pattern Catalog paper?

**A:**
1. A FRAMEWORK for documenting prompt patterns across domains.
2. A CATALOG of tested patterns that improve LLM outputs.
3. An explanation of how prompts can COMBINE multiple patterns.

**Difficulty:** Medium

**Tests knowledge of:** [Pattern Composition](PATTERNS.md#pattern-composition-m1-paper)

**Source:** Module 1, "A Prompt Pattern Catalog" paper (abstract)

**Common wrong answer:** Listing specific pattern names (Persona, Few-Shot, etc.) — those ARE the catalog, but the contribution is the META-framework, not the individual patterns inside it.

---

## Q: Why is "pattern composition" important in prompt engineering?

**A:** Because single patterns solve single-dimensional problems. Real tasks often need multiple kinds of behavior (a specific role AND a specific format AND explicit reasoning) which requires stacking patterns together. Composition turns a small catalog into a combinatorial library.

**Difficulty:** Medium

**Tests knowledge of:** [Pattern Composition](PATTERNS.md#pattern-composition-m1-paper)

**Source:** Module 1, "A Prompt Pattern Catalog" paper (abstract)

**Common wrong answer:** "To make prompts longer" — length isn't the goal. Compound CAPABILITY is.

---

## Q: What are the 2 fundamental contextual statements of the Persona Pattern (formal version)?

**A:**
1. Act as Persona X
2. Perform task Y

Replace X with any entity that has a recognizable output shape (profession, perspective, system, character). Replace Y with the specific task.

**Difficulty:** Easy

**Tests knowledge of:** [Persona Pattern](PATTERNS.md#persona-pattern-m1-persona)

**Source:** Module 1, Paper: Persona Pattern formal section

**Common wrong answer:** Listing more than 2 statements (e.g., "Add specificity," "Use formal tone"). The paper's formal version is exactly 2 statements; additional specificity is STACKING other patterns, not part of the base Persona Pattern.

---

## Q: How do you make an LLM reason about data it wasn't trained on?

**A:** Inject the data directly into the prompt — put the new information (documents, numbers, private facts) at the top, then ask your question below it. No retraining or fine-tuning needed; the LLM reads the context alongside your question and reasons on both together.

**Difficulty:** Easy

**Tests knowledge of:** [Context Injection](GLOSSARY.md#context-injection-m1-context), [Context Injection Pattern](PATTERNS.md#context-injection-pattern-m1-context)

**Source:** Module 1, "Introducing New Information to a Large Language Model"

**Common wrong answer:** "Fine-tune the model on your data" — possible but expensive and slow. Context injection gives 90% of the value for 0% of the work.

---

## Q: Why did adding historical bird data change the LLM's ability to answer "how many birds are outside my house"?

**A:** Without data, the model correctly refused because it couldn't reason without inputs. With the monthly data in the prompt, the model had exactly what it needed to estimate the answer for March (210). Same question → different output, entirely because of context availability.

**Difficulty:** Easy

**Tests knowledge of:** [Context Injection Pattern](PATTERNS.md#context-injection-pattern-m1-context)

**Source:** Module 1, "Introducing New Information to a Large Language Model"

**Common wrong answer:** "Because the model learned from the data" — wrong. The model doesn't LEARN from prompt content; it just has it available to reason over during generation. No memory persists.

---

## Q: What are "hidden assumptions" and why must they be injected into the prompt?

**A:** Unusual rules or non-default conditions the model can't guess (e.g., "animals live forever inside this glass dome"). The LLM defaults to real-world priors; if your scenario deviates, you MUST state the deviation explicitly. Without it, the model applies normal-world assumptions and reasons to the wrong answer.

**Difficulty:** Medium

**Tests knowledge of:** [Hidden Assumptions](GLOSSARY.md#hidden-assumptions-m1-context), [Context Injection Pattern](PATTERNS.md#context-injection-pattern-m1-context)

**Source:** Module 1, "Introducing New Information to a Large Language Model"

**Common wrong answer:** "Models can infer hidden rules from context" — unreliable. They'll apply training-data defaults unless told otherwise.

---

## Q: What production architecture is Jules describing when he talks about "search engines pulling documents and putting them in the prompt"?

**A:** Retrieval-Augmented Generation (RAG). A system searches external sources (databases, vector stores, documents) for content relevant to the user's question, then injects the retrieved content into the prompt before asking the LLM to answer. Jules describes the pattern without naming it.

**Difficulty:** Medium

**Tests knowledge of:** [RAG](GLOSSARY.md#rag-m1-context), [Context Injection](GLOSSARY.md#context-injection-m1-context)

**Source:** Module 1, "Introducing New Information to a Large Language Model"

**Common wrong answer:** "Fine-tuning" — no, RAG doesn't touch model weights. It's a prompt-engineering pattern, not a training technique.

---

## Q: The same task "evaluate what I'm eating" produces totally different output from a nutritionist vs a gourmet chef persona. Why?

**A:** Because the persona, not the task, dominates output shape. The nutritionist persona loads health-optimization vocabulary and framing; the gourmet chef persona loads culinary aesthetic and technique-critique framing. Same input, orthogonal analyses.

**Difficulty:** Medium

**Tests knowledge of:** [Persona Pattern](PATTERNS.md#persona-pattern-m1-persona)

**Source:** Module 1, Paper: Persona Pattern examples

**Common wrong answer:** "The task is ambiguous" — no, the task is identical. What differs is the PERSONA, which is the point.

---
