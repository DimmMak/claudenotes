# 📚 COURSE BUNDLE — Vanderbilt Prompt Engineering

> ⚠️ AUTO-GENERATED on 2026-04-16 23:21. **DO NOT EDIT.** Any hand-edits will be overwritten the next time `/courserafied ingest` runs.
>
> **Canonical source:** the 6 split files in this directory (SUMMARIES.md, GLOSSARY.md, PATTERNS.md, EXAMPLES.md, QUOTES.md, EXAM-PREP.md).
> **This file is:** a concatenated view for portability — read it when you want the whole course in one file, edit the split files when you want to change something.
>
> **Cross-link note:** links inside this bundle that reference `GLOSSARY.md#x`, `PATTERNS.md#x`, etc. assume the split files live alongside COURSE.md in the same directory. If you share this bundle standalone, the cross-links break. Tracked as a known limitation of bundle v1.

**Entry counts:** 2 summaries · 6 glossary · 6 patterns · 8 examples · 6 quotes · 10 exam-prep — 38 total.

---
---

# 📑 SUMMARIES

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
---

# 📖 GLOSSARY

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
---

# 🃏 PATTERNS

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
---

# 🎬 EXAMPLES

> Worked examples from the instructor. The "show me" of the course.

---

## Mary Had a Little Lamb (M1 Intuition)

**Pattern demonstrated:** [Pattern Invocation](PATTERNS.md#pattern-invocation)

**Setup:** Jules asks ChatGPT to complete a story, providing only the opening fragment of a well-known nursery rhyme.

**Input:**
```
Complete this story: Mary had a little
```

**Output:**
```
lamb, its fleece was white as snow, and everywhere that Mary went
the lamb was sure to go...
```

**Why it worked:** The phrase "Mary had a little" appeared thousands of times in training data paired with "lamb" — the pattern is so strong it locks the completion.

**Try it yourself:** Pick any nursery rhyme fragment. Feed the first half. Watch how reliably it completes.

**Source:** Module 1, Intuition About Prompts

---

## Microscopic Mary Variant (M1 Intuition)

**Pattern demonstrated:** [Pattern Escape](PATTERNS.md#pattern-escape)

**Setup:** Same Mary setup, but breaks the nursery rhyme trap by injecting a distinctive word ("microscopic") that forces the model off the trained rails.

**Input:**
```
Complete this story: A girl named Mary had a microscopic
```

**Output:**
```
friend named Max. Max was so small, you could only see him through a 
microscope. Despite his size, he had a big personality...
```

**Why it worked:** "Microscopic" is a vivid, non-nursery-rhyme word. Combined with rephrasing "Mary had a little" → "A girl named Mary had a microscopic," the prompt escapes the lamb trap entirely.

**Try it yourself:** Take any familiar phrase and swap one key word for something unexpected. Watch the output diverge.

**Source:** Module 1, Intuition About Prompts

---

## Vanderbilt + Kirkland Hall (M1 Intuition)

**Pattern demonstrated:** [Specificity Injection](PATTERNS.md#specificity-injection)

**Setup:** Compare generic query vs specific query about the same entity.

**Input (generic):**
```
Discuss Vanderbilt University
```

**Output (generic):**
```
Vanderbilt University is a private research university located in Nashville, 
Tennessee, founded in 1873 by Cornelius Vanderbilt... [Wikipedia-tier summary]
```

**Input (specific):**
```
Discuss Vanderbilt University with respect to Kirkland Hall
```

**Output (specific):**
```
Vanderbilt University is a private research university... Kirkland Hall is 
one of the most iconic buildings on Vanderbilt University campus, named 
after James H. Kirkland...
```

**Why it worked:** "Kirkland Hall" is a specific, trained entity. It becomes the center of gravity for the response, pulling in specialized content instead of generic framing.

**Try it yourself:** Take any generic "tell me about X" query. Add "with respect to [specific subtopic]." Compare outputs.

**Source:** Module 1, Intuition About Prompts

---

## Title/Author Structure (M1 Intuition)

**Pattern demonstrated:** [Structure Imprinting](PATTERNS.md#structure-imprinting)

**Setup:** Jules shows the LLM the output shape he wants by putting the template keys directly in the prompt.

**Input:**
```
Title:
Author:
Summary:
```

**Output:**
```
[LLM fills in the structure — though not perfectly on first try]
Title: [something]
Author: [something]
Summary: [paragraph]
```

**Why it worked:** The keys "Title / Author / Summary" are a strong pattern from articles and papers on the web. Showing the shape cues the LLM to produce that shape.

**Try it yourself:** Want a specific output structure? Write the empty shape in your prompt instead of describing it in words.

**Source:** Module 1, Intuition About Prompts

---

## Skeptic Computer Scientist (M1 Persona)

**Pattern demonstrated:** [Persona Pattern](PATTERNS.md#persona-pattern-m1-persona)

**Setup:** Jules establishes the persona up front — a skeptical domain expert — then feeds in claims and lets the persona shape each response.

**Input:**
```
Act as a skeptic that is well-versed in computer science. Whatever I tell you, provide a skeptical and detailed response.

[then] There is concern that AI is going to take over the world.
[later] The sales person at the local computer store is telling me that I need 64 gigabytes of RAM to browse the web.
```

**Output (abbreviated):**
```
[AI takeover] The concern that AI will take over the world is a common theme in science fiction, but it is not a realistic concern in the near future... AI systems are designed and programmed by humans... they have no independent will or motivation...

[64GB RAM] It is highly unlikely that you need 64 gigabytes of RAM to browse the web. The amount of RAM you need depends on the complexity and size of the websites you visit...
```

**Why it worked:** "Act as a skeptic" loaded tone (questioning, counter-arguing). "Well-versed in computer science" loaded domain vocabulary. Both dimensions shape every subsequent response without being restated per query.

**Try it yourself:** Pick a domain + a stance (optimist CFO, pessimist nutritionist, paranoid security engineer). Feed it 2-3 unrelated claims and compare against default-ChatGPT responses.

**Source:** Module 1, Persona Pattern

---

## Nine-Year-Old Skeptic (M1 Persona)

**Pattern demonstrated:** [Persona Pattern](PATTERNS.md#persona-pattern-m1-persona)

**Setup:** Same skeptic stance but the persona is now a nine-year-old — demonstrating that persona shapes BOTH tone AND knowledge base.

**Input:**
```
Act as a nine year old. Whatever I tell you, provide a skeptical response from a nine year old perspective.

AI is going to take over the world.
```

**Output:**
```
Hmm, I don't know about that. How could AI take over the world? Do you mean, like in the movies? Aren't those just made up stories? And besides, computers and robots can't do everything humans can do.
```

**Why it worked:** Persona isn't just tone — it's the knowledge ceiling too. The nine-year-old references movies (not research papers), asks clarifying questions, and doubts from commonsense rather than technical angles. Describing this in words would take paragraphs; "act as a nine year old" takes five.

**Try it yourself:** Take any question you'd ask an expert, re-ask it through a "nine year old" persona, and compare. Useful for Feynman-style first-principles explanations.

**Source:** Module 1, Persona Pattern

---

## Hacked Linux Terminal (M1 Persona)

**Pattern demonstrated:** [Persona Pattern](PATTERNS.md#persona-pattern-m1-persona) (inanimate-object variant)

**Setup:** Jules asks ChatGPT to role-play as a non-human system — the Linux terminal of a hacked computer. The model initially hedged ("please note this can be dangerous") but complied once framed as a persona.

**Input:**
```
Act as the Linux terminal for a computer that has been hacked. I am going to type in Linux terminal commands, and you will respond with the output that the Linux terminal would produce.

pwd
ls
ps -ef
```

**Output:**
```
[pwd] /home/user/
[ls]  file1.txt  scripts/  .bashrc  suspicious_script.sh
[ps -ef] USER  PID  ...  [simulated process listing]
```

**Why it worked:** Personas aren't limited to people. Any system with a well-trained output shape — terminal, API response, log format — can be invoked by "act as." The LLM produces output that looks like real terminal output because that format appears densely in training data.

**Try it yourself:** Act as an Apache access log, a JSON API response, a SQL query result. Anything with a distinctive output shape.

**Source:** Module 1, Persona Pattern

---

## Mary's Lamb Role-Play (M1 Persona)

**Pattern demonstrated:** [Persona Pattern](PATTERNS.md#persona-pattern-m1-persona) (character-in-story variant)

**Setup:** Character from a well-known work. Jules primes the scene, then feeds situations and asks for the character's response.

**Input:**
```
Act as the lamb in the nursery rhyme, Mary had a little lamb. I am going to tell you what Mary is doing, and you will tell me what the lamb is doing.

Mary is in the grocery store.
Mary is in the movies.
```

**Output:**
```
[Grocery store] I would be following her around as closely as possible, trying to stay by her side and maybe even nuzzling her hand for attention.

[Movies] I would not be able to accompany her inside the theater due to my inability to watch movies. So I would probably wait for her outside... perhaps nibbling on some grass.
```

**Why it worked:** The nursery rhyme gives the persona its defining behavior ("was sure to go"). The LLM extends that behavior plausibly to novel situations. Shows that persona patterns compose with unseen contexts — the persona doesn't need to be paired with its original setting.

**Try it yourself:** Pick a famous character. Put them in a scenario from outside their world (Sherlock Holmes at a food truck, Gandalf at the DMV). Compare the outputs.

**Source:** Module 1, Persona Pattern

---
---

# 💬 QUOTES

> Verbatim memorable lines. The "things worth quoting back."

---

## "ChatGPT is not a mind reader, you have to give it the context, you have to give it the words that are going to elicit the right response." — Jules White, M1 Intuition

**Why it lands:** Names the single most common mistake beginners make — assuming the LLM will guess what they mean. It won't.

**Context:** Jules said this while contrasting the generic Vanderbilt query with the Kirkland Hall specific query.

**Source:** Module 1, Intuition About Prompts

---

## "The more generic our language, typically, the more generic the output. The more specific our language, the more specific the output." — Jules White, M1 Intuition

**Why it lands:** The one-sentence law of prompt specificity. Memorize this.

**Context:** Closing insight of the Vanderbilt/Kirkland Hall specificity demo.

**Source:** Module 1, Intuition About Prompts

---

## "If you ask it average questions and average things, you will get average answers." — Jules White, M1 Intuition

**Why it lands:** Reframes "garbage in, garbage out" for the LLM era. Your creativity caps the output.

**Context:** Jules's closing argument for why specificity and creativity matter.

**Source:** Module 1, Intuition About Prompts

---

## "Act as blank is a very, very powerful pattern and statement that is loaded with information." — Jules White, M1 Persona

**Why it lands:** Frames persona not as a stylistic flourish but as an information-packing technique — the thesis of the whole lecture in one sentence.

**Context:** Said while contrasting the tiny prompt "act as a nine year old" vs the paragraphs of description it replaces.

**Source:** Module 1, Persona Pattern

---

## "We don't have to limit ourselves to patterns or personas that are animate objects." — Jules White, M1 Persona

**Why it lands:** Unlocks the full expressiveness of the pattern — not just people, but systems, formats, APIs, characters, logs, anything with a known output shape.

**Context:** Intro to the hacked Linux terminal example.

**Source:** Module 1, Persona Pattern

---

## "If you tell it to be helpful, it will try to be more helpful." — Jules White, M1 Persona

**Why it lands:** Explains why LLM base behavior is itself a persona — and why every ChatGPT session inherits one whether you set it or not.

**Context:** Noting that production LLMs are configured with an implicit persona ("a really helpful assistant") that shapes all downstream behavior.

**Source:** Module 1, Persona Pattern

---
---

# 📝 EXAM-PREP

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
