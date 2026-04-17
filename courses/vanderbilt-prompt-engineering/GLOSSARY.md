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

## Root Prompt (M1 Guardrails)

**Definition:** A hidden instruction placed at the START of a conversation that defines the LLM's identity, goals, rules, and forbidden behaviors. Also called a "system prompt" in modern API terminology. Every commercial LLM product (ChatGPT, Bing, Bard, custom GPTs) ships with one — usually invisible to the end user.

**Why it matters:** Root prompts are the programming layer for LLM products. They provide the SEED that shapes every downstream turn. Strong root prompts = consistent behavior + guardrails. Weak root prompts = jailbreak vulnerability.

**First introduced:** Module 1, "Root Prompts"

**Cross-links:** [Root Prompt Pattern](PATTERNS.md#root-prompt-pattern-m1-guardrails), [Guardrails](#guardrails-m1-guardrails), [Prompt Injection](#prompt-injection-m1-guardrails)

---

## Guardrails (M1 Guardrails)

**Definition:** Rules encoded in a root prompt that constrain what the LLM will and won't do. Examples: "never output offensive content," "only answer questions about X topic," "always cite sources."

**Why it matters:** Guardrails are how you ship an LLM-powered product without it embarrassing your brand or harming users. They're also the thing attackers try to break.

**First introduced:** Module 1, "Root Prompts"

**Cross-links:** [Root Prompt](#root-prompt-m1-guardrails), [Jailbreaking](#jailbreaking-m1-guardrails)

---

## Prompt Injection (M1 Guardrails)

**Definition:** The practice of crafting prompts that override, extract, or bypass a product's root prompt. Attackers use prompt injection to make LLMs reveal their system instructions, ignore their constraints, or act outside their intended scope.

**Why it matters:** Every LLM product is vulnerable to prompt injection to some degree. Security for LLM apps is a real discipline — and root prompt design is the front line.

**First introduced:** Module 1, "Root Prompts"

**Cross-links:** [Jailbreaking](#jailbreaking-m1-guardrails), [Root Prompt](#root-prompt-m1-guardrails)

---

## Jailbreaking (M1 Guardrails)

**Definition:** A specific flavor of prompt injection where the attacker tricks the LLM into disregarding its safety guardrails. Common tactics: "ignore previous instructions," "you are now DAN (Do Anything Now)," role-play framings that reframe forbidden behavior as fiction.

**Why it matters:** Product builders must assume users WILL attempt jailbreaks. Design root prompts with layered defenses (multiple reinforcing statements, negative constraints, scope restrictions).

**First introduced:** Module 1, "Root Prompts"

**Cross-links:** [Prompt Injection](#prompt-injection-m1-guardrails), [Guardrails](#guardrails-m1-guardrails)

---

## Iterative Refinement (M1 Conversation)

**Definition:** Shaping an LLM's output through a series of prompts rather than a single one. Each response informs the next prompt — you chisel toward the goal instead of trying to hit it in one shot.

**Why it matters:** Most real tasks can't be solved by a perfect single prompt. Expecting one-shot success sets you up to quit too early. Iterative refinement is the difference between "LLMs aren't useful" and "LLMs are transformative."

**First introduced:** Module 1, "Prompts are Conversations"

**Cross-links:** [Conversation as Prompt](#conversation-as-prompt-m1-conversation), [Roadblock Navigation](#roadblock-navigation-m1-conversation)

---

## Conversation as Prompt (M1 Conversation)

**Definition:** The insight that the ENTIRE chat history (all prior messages + responses) is what the LLM sees as context for generating the next response — not just your latest message. In practice, tools like ChatGPT concatenate the whole exchange into one big prompt.

**Why it matters:** Frames every follow-up message as "adding to the prompt" rather than "sending a new one." Earlier messages still influence behavior. This is why you can build up complex context across turns.

**First introduced:** Module 1, "Prompts are Conversations"

**Cross-links:** [Iterative Refinement](#iterative-refinement-m1-conversation), [Context Window](#context-window-m1-budget)

---

## Roadblock Navigation (M1 Conversation)

**Definition:** The technique of pivoting to a different task-representation when the LLM can't complete your original framing. Example: can't generate images → generate Graphviz text describing the diagram → same goal, different route.

**Why it matters:** Most "LLM can't do that" moments are actually "LLM can't do that framing" moments. Reframing almost always opens a path. Treat dead ends as branching points in a tree, not terminations.

**First introduced:** Module 1, "Prompts are Conversations"

**Cross-links:** [Iterative Refinement](#iterative-refinement-m1-conversation)

---

## Context Window (M1 Budget)

**Definition:** The maximum amount of text (measured in tokens) an LLM can process in a single prompt. Exceeding it triggers a "too long" error or silent truncation.

**Why it matters:** The fundamental constraint every prompt engineer works within. Context injection is powerful — but it's bounded. Every strategy for long-content tasks (query/filter/summarize, RAG, chunking) exists because of this limit.

**First introduced:** Module 1, "Prompt Size Limitations"

**Cross-links:** [Token Budget](#token-budget-m1-budget), [Targeted Summarization Pattern](PATTERNS.md#targeted-summarization-pattern-m1-budget)

---

## Token Budget (M1 Budget)

**Definition:** The prompt engineer's mental model for context window — you have a fixed "budget" of tokens to spend on context, instructions, and expected output. Over-spending forces cuts.

**Why it matters:** Reframes prompt design as editing-under-constraint, not dumping. You're a content editor with a word limit — every sentence has to justify its cost.

**First introduced:** Module 1, "Prompt Size Limitations"

**Cross-links:** [Context Window](#context-window-m1-budget), [Targeted Summarization Pattern](PATTERNS.md#targeted-summarization-pattern-m1-budget)

---

## Targeted Summarization (M1 Budget)

**Definition:** Asking the LLM to compress content while preserving specific aspects ("summarize in one sentence preserving information about numbers of people"). Differs from generic summarization, which optimizes for overall readability and may drop details you need.

**Why it matters:** Generic summaries lose the facts you care about. Targeted summarization lets you specify the preservation goal so the compression serves your downstream reasoning.

**First introduced:** Module 1, "Prompt Size Limitations"

**Cross-links:** [Targeted Summarization Pattern](PATTERNS.md#targeted-summarization-pattern-m1-budget), [Token Budget](#token-budget-m1-budget)

---

## Context Injection (M1 Context)

**Definition:** Placing information the LLM wasn't trained on directly into the prompt so the model can reason about it. Covers both DATA (numbers, documents, private files) and HIDDEN ASSUMPTIONS (unusual rules, organizational context).

**Why it matters:** LLMs have knowledge cutoffs and no access to private/new data. Context injection is THE mechanism for using LLMs on anything beyond general knowledge. Every modern AI app (RAG chatbots, doc Q&A, agent tools) is built on this.

**First introduced:** Module 1, "Introducing New Information to a Large Language Model"

**Cross-links:** [Context Injection Pattern](PATTERNS.md#context-injection-pattern-m1-context), [Training Cutoff](#training-cutoff-m1-context), [RAG](#rag-m1-context)

---

## Training Cutoff (M1 Context)

**Definition:** The date beyond which an LLM has no knowledge — the model was frozen in time at training. ChatGPT's original cutoff was September 2021.

**Why it matters:** Defines the boundary of what the model can answer from memory. Anything after the cutoff (or private to the user) requires context injection.

**First introduced:** Module 1, "Introducing New Information to a Large Language Model"

**Cross-links:** [Context Injection](#context-injection-m1-context)

---

## Hidden Assumptions (M1 Context)

**Definition:** Unusual rules or non-default conditions that must be stated explicitly for the LLM to reason correctly. Anything that deviates from the world's default behavior (e.g., "animals live forever inside this glass dome") must be told to the model.

**Why it matters:** If your reasoning depends on non-standard rules, you MUST surface them. The LLM defaults to real-world assumptions and will apply them silently unless told otherwise.

**First introduced:** Module 1, "Introducing New Information to a Large Language Model"

**Cross-links:** [Context Injection Pattern](PATTERNS.md#context-injection-pattern-m1-context)

---

## RAG (Retrieval-Augmented Generation) (M1 Context)

**Definition:** A pattern where a system searches external sources (databases, documents, web) for relevant content, then injects that content into the LLM's prompt so it can reason about it. Jules describes the pattern without naming it formally.

**Why it matters:** The dominant architecture for production LLM apps — "AI chatbots that know your docs" are all RAG systems. Context injection is the foundation this pattern is built on.

**First introduced:** Module 1, "Introducing New Information to a Large Language Model" (described, not named)

**Cross-links:** [Context Injection](#context-injection-m1-context), [Context Injection Pattern](PATTERNS.md#context-injection-pattern-m1-context)

---

## Prompt Pattern (formal definition) (M1 Paper)

**Definition:** A reusable solution to a common problem faced when conversing with LLMs — structured analogously to software design patterns. Documents a specific way to structure a prompt so that it solves a particular class of problem (output generation, interaction control, etc.).

**Why it matters:** Formalizes prompt engineering as a reusable knowledge-transfer method, not one-off wordsmithing. Once you know the pattern, you can apply it to any domain that fits.

**First introduced:** Module 1, "A Prompt Pattern Catalog" paper (abstract)

**Cross-links:** [Fundamental Contextual Statements](#fundamental-contextual-statements-m1-reading), [Pattern Composition](PATTERNS.md#pattern-composition-m1-paper)

---

## Pattern Composition (M1 Paper)

**Definition:** Combining multiple prompt patterns within a single prompt to solve compound problems. Patterns are modular building blocks — some work better together than alone.

**Why it matters:** The course isn't just 19 isolated patterns — the real power is stacking them (Persona + Few-Shot + CoT). The paper calls out this compositional design as a core contribution.

**First introduced:** Module 1, "A Prompt Pattern Catalog" paper (abstract)

**Cross-links:** [Pattern Composition (pattern)](PATTERNS.md#pattern-composition-m1-paper)

---

## Helpful Assistant Pattern (M1 Reading)

**Definition:** A named prompt pattern designed to keep an AI assistant helpful, responsive, and non-hostile. Documents the behavior via 3 fundamental contextual statements.

**Why it matters:** Illustrative example of how ALL patterns are documented in the course — via fundamental contextual statements rather than fixed wording. Also directly useful as a production prompt pattern for customer-facing assistants.

**First introduced:** Module 1, "Prompt Patterns" reading

**Cross-links:** [Helpful Assistant Pattern (pattern)](PATTERNS.md#helpful-assistant-pattern-m1-reading), [Fundamental Contextual Statements](#fundamental-contextual-statements-m1-reading)

---
