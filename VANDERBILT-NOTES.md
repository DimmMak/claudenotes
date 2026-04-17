# 📓 Vanderbilt Prompt Engineering — Key Points

Live notebook. Auto-updated by Claude as we cowatch lectures together. Will be split into per-module files when it gets too long.

**Course:** [Prompt Engineering for ChatGPT](https://www.coursera.org/learn/prompt-engineering) — Dr. Jules White, Vanderbilt

---

## 🎯 Master Takeaways (refined as we go)

- **Persona = the role the LLM is acting out.** Every prompt invokes a persona — explicit or default.
- **You're ALWAYS using a persona.** No persona = the default "helpful hedging assistant" persona kicks in.
- **Specificity of persona = specificity of output.** "Senior data analyst at fintech, 8 years experience" beats "data analyst" beats "expert."
- **Patterns unlock vocabulary you don't have.** The persona pattern gets you domain terms (cluster reduction, phonological errors) you wouldn't know to ask about.
- **Creativity is the skill ceiling.** The model is the same; the human's prompt design determines output quality.
- **You can program with words now.** Writing prompts IS programming. No CS degree needed.

---

## 📚 Module 1 — Course Introduction

### L1 — Overview of the Course

**The reframe:** LLMs are a creative medium, not a cheating tool. Skill ceiling = human creativity, not model capability.

**What you need to use these well:**
- Basic computer literacy (open files, use a text interface)
- Writing skills (Jules's father was a creative writing professor — he leans on it)
- Openness to experiment

**Patterns previewed for the course:**
- Persona Pattern
- Question Refinement
- Cognitive Verifier
- Few-Shot Examples

**Closing line:** *"Try to give your thought form through this tool, use it as a tool to accelerate your ideas into realization."*

---

### L2 — Persona Pattern Demo (Speech-Language Pathologist)

**The pattern:** `"You are a [specific role]"` or `"Act as a [specific role]"`

**Phrasing strength (weak → strong):**
1. "Help me with X" → no persona, default assistant
2. "Act like a X" → soft persona
3. "You are a X" → direct
4. "You are a senior X" → adds expertise level
5. "You are a senior X at [company], [years] experience, you [behavioral trait]" → locked in

**Why it works:**
- Vocabulary unlock — domain terms surface that you wouldn't know to ask for
- Format unlock — output structure shifts (report, prescription, recipe) to match what the role would produce
- Method unlock — you see the order an expert tackles the problem in

**Caveats:**
- Pick personas you can VALIDATE (Jules chose SLP because his wife could verify)
- LLMs make assumptions and flag them — watch for the assumption notes
- Self-hedging persists — the helpful-assistant default isn't fully suppressed
- Personas only work if the role has online training data (obscure roles → thin output)

**Deeper insight (not in lecture, surfaced in conversation):**
- Persona ≠ identity. Persona = the mask. Identity = the actor (the model weights).
- For LLMs, you only ever interact with the persona layer — there's no accessible "true self."
- Every `.skill` file you write is a persona override declaration.

**Connection to your projects:**
- ♣️ Clubs suit in Promptlatro
- Every Royal Rumble legend (Druckenmiller, Klarman, Tom Lee, etc.)
- Every Pokémon agent in ClaudeNotes (Pikachu, Mew, etc.)
- You built 4 systems on this pattern before being formally taught it

---

## 📚 Module 2 — Introduction to Prompts

_(Empty — fills as we cowatch)_

---

## 📚 Module 3 — Prompt Patterns I

_(Empty)_

---

## 📚 Module 4 — Few-Shot Examples

_(Empty)_

---

## 📚 Module 5 — Prompt Patterns II

_(Empty)_

---

## 📚 Module 6 — Prompt Patterns III

_(Empty)_

---

## 🃏 Pattern Reference (builds as we encounter them)

| Pattern | Formula | When | Where covered |
|---|---|---|---|
| Persona | "You are a [specific role]" | When you want vocab/format/method of a domain expert | M1 L2 |
| Question Refinement | _(tbd)_ | _(tbd)_ | _(tbd)_ |
| Cognitive Verifier | _(tbd)_ | _(tbd)_ | _(tbd)_ |
| Few-Shot | _(tbd)_ | _(tbd)_ | _(tbd)_ |
| Chain-of-Thought | _(tbd)_ | _(tbd)_ | _(tbd)_ |

---

## 💬 Quote Wall

> "Try to give your thought form through this tool, use it as a tool to accelerate your ideas into realization." — Jules White, M1 L1

> "I would not have known to ask ChatGPT for these things." — Jules White, M1 L2 (the core reason prompt engineering matters)

---

## 🧠 Cross-Module Insights

- **Persona is the meta-pattern that contains all the others.** Every other pattern is itself a persona instance. (After M1)
- _(more as we go)_
