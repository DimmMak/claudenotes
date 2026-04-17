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
