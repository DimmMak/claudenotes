# 🧠 MEMORIZE — Don't Forget These

> The single most important file in this repo. Things from the Vanderbilt prompt engineering course I want to burn into long-term memory.
>
> Add to this as I go. Pin the top 10 once the course is done.

---

## 🥇 The Big Ideas

_Add the 1-3 sentence summaries that change how I think. The stuff I'd tell a friend at a coffee shop._

- **Separation of concerns** — one job per file, one job per agent, one job per command. The oldest rule in software engineering. Applies to file structure, prompt design, agent factories, and how you organize your study notes. Same principle, infinite domains.
- **Persona = the role the LLM is acting out** — every prompt invokes one (explicit or default). Specificity of persona = specificity of output. (M1 L2)
- **You're ALWAYS using a persona** — even silence about it defaults to "helpful hedging assistant." The pattern doesn't ADD personality, it OVERRIDES the default.
- **LLMs are autoregressive next-token predictors** — every output is built one token at a time, each becoming input for the next. (M1 fundamentals)
- **Leverage scales with constraint** — the more power an agent has, the tighter its contract must be. Max power + max discipline = safe leverage. Remove either side and you get rigidity (too tight) or data loss (too loose). Like an F1 car: wide possibility space + tight guardrails = fast AND survivable.
- _(Module 2) ..._
- _(Module 3) ..._

---

## 🃏 Patterns Cheat Sheet

Quick recall reference. One line per pattern — what it is, when to use it.

| Pattern | When to reach for it |
|---|---|
| Persona | _"act as a..."_ — set role + expertise |
| Question Refinement | Get the LLM to fix your bad question first |
| Cognitive Verifier | Force breakdown of complex Q into sub-Qs |
| Audience Persona | "Explain to a 10-year-old / a CFO / etc." |
| Flipped Interaction | LLM asks ME questions until it has enough info |
| Few-Shot | Show 3-5 examples, let pattern do the work |
| Chain of Thought | "Think step by step" — forces reasoning |
| ReAct | Reasoning + acting (search, calc) interleaved |
| Game Play | Frame task as a game with rules + scoring |
| Template | Fill-in-the-blank scaffold for consistent output |
| Meta Language | Define a mini-DSL the LLM understands |
| Recipe | Sequence of explicit ordered steps |
| Alternative Approaches | Force LLM to give 3+ different solutions |
| Ask for Input | LLM pauses and asks for missing input |
| Outline Expansion | Sketch outline → fill in detail iteratively |
| Menu Actions | Numbered options the user picks from |
| Fact Check List | LLM lists every factual claim for verification |
| Tail Generators | Auto-suggest "what's next?" follow-ups |
| Semantic Filter | Strip/keep info matching a meaning, not a regex |

_(I'll add personal one-liners as I learn each one.)_

---

## ⚡ Mental Models

_Frameworks Jules uses that reframe how I think about LLMs._

- _Tokens are the atom, not words_
- _Randomness is a feature, not a bug — temperature controls it_
- _Patterns > examples — patterns transfer, examples don't_
- _..._

---

## 💬 Quotes that hit

_Verbatim things Jules said that I want to remember._

> _"..."_
> — Jules White, Module N

---

## 🎯 What I'd tell my past self

_End-of-course reflection. Update once I finish._

---

## 🔁 Recall checklist

Things I want to be able to recite from memory at a job interview:

- [ ] All 19 patterns by name
- [ ] What each pattern's "trigger" use case is
- [ ] Few-shot vs Chain-of-Thought vs ReAct — when to use which
- [ ] Why temperature matters
- [ ] What a token is and why it matters for cost & context
- [ ] How to design a system prompt for a customer-facing chatbot
- [ ] At least 3 of the named patterns I've used in production work
