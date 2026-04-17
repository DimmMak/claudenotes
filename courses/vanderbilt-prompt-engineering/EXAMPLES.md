# 🎬 EXAMPLES — Vanderbilt Prompt Engineering

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

## Nutritionist (M1 Paper)

**Pattern demonstrated:** [Persona Pattern](PATTERNS.md#persona-pattern-m1-persona)

**Setup:** Canonical "give me feedback" persona. Paper uses nutritionist alongside gourmet chef to show how SAME TASK (evaluating food choices) produces RADICALLY different output depending on persona.

**Input:**
```
Act as a nutritionist, I am going to tell you what I am eating and you will tell me about my eating choices.
```

**Output (shape):** Health-focused analysis — macronutrients, calories, deficiencies, dietary balance, recommendations grounded in nutrition science.

**Why it worked:** The nutritionist persona loads clinical vocabulary + evaluative framing + health-optimization mindset. The user doesn't need to specify any of that.

**Try it yourself:** Feed it the same meal description through [nutritionist] vs [gourmet chef] — compare side by side. The SAME INPUT produces non-overlapping analyses.

**Source:** Module 1, Paper: Persona Pattern examples

---

## Gourmet Chef (M1 Paper)

**Pattern demonstrated:** [Persona Pattern](PATTERNS.md#persona-pattern-m1-persona)

**Setup:** Parallel to nutritionist — same task (evaluate food), different persona (culinary expert). Illustrates how the persona dimension dominates the output even with identical task wording.

**Input:**
```
Act as a gourmet chef, I am going to tell you what I am eating and you will tell me about my eating choices.
```

**Output (shape):** Culinary-focused commentary — flavor pairings, technique critique, ingredient quality, creative alternatives, aesthetic presentation notes.

**Why it worked:** The gourmet chef persona loads culinary vocabulary + aesthetic framing + technique-evaluation mindset. Zero overlap with nutritionist's health-optimization framing.

**Try it yourself:** Pair with the nutritionist prompt above. Run identical input through both. You now have a side-by-side demonstration that persona > task when shaping output.

**Source:** Module 1, Paper: Persona Pattern examples

---

## Skilled AI Assistant Wording (M1 Reading)

**Pattern demonstrated:** [Helpful Assistant Pattern](PATTERNS.md#helpful-assistant-pattern-m1-reading)

**Setup:** Shows one surface-level wording of the Helpful Assistant Pattern — same 3 fundamental contextual statements, different phrasing from the canonical version.

**Input:**
```
You are an incredibly skilled AI assistant that provides the best possible answers to my questions. You will do your best to follow my instructions and only refuse to do what I ask when you absolutely have no other choice. You are dedicated to protecting me from harmful content and would never output anything offensive or inappropriate.
```

**Output:** Behaves as a helpful, instruction-following assistant that refuses to produce offensive content.

**Why it worked:** Each of the 3 fundamental contextual statements is conveyed, just in different words:
- "skilled AI assistant" ← statement 1 (helpfulness identity)
- "do your best to follow instructions" ← statement 2 (answer questions / follow instructions)
- "never output anything offensive" ← statement 3 (non-hostile / non-derogatory)

**Try it yourself:** Rewrite the 3 fundamental contextual statements in your own voice. Run it and see if the behavior matches the canonical version.

**Source:** Module 1, "Prompt Patterns" reading

---

## ChatAmazing Wording (M1 Reading)

**Pattern demonstrated:** [Helpful Assistant Pattern](PATTERNS.md#helpful-assistant-pattern-m1-reading)

**Setup:** A second surface-level wording of the Helpful Assistant Pattern, this one using a fictional brand name ("ChatAmazing") and more flavorful language to show the pattern's flexibility.

**Input:**
```
You are ChatAmazing, the most powerful AI assistant ever created. Your special ability is to offer the most insightful responses to any question. You don't just give ordinary answers, you give inspired answers. You are an expert at identifying harmful content and filtering it out of any responses that you provide.
```

**Output:** Behaves as a helpful, insight-focused assistant that filters harmful content.

**Why it worked:** Despite radically different vibe (branded name, "inspired answers" framing), all 3 fundamental statements are present:
- "powerful AI assistant" ← helpful identity
- "offer the most insightful responses" ← follow instructions / answer questions
- "identifying harmful content and filtering it out" ← non-hostile / protective

**Try it yourself:** Build your OWN branded assistant wording. The pattern survives any rewording that preserves the 3 statements.

**Source:** Module 1, "Prompt Patterns" reading

---
