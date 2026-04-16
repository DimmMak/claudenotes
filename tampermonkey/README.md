# 🐒 Tampermonkey Scripts for ClaudeNotes Cowatch

User scripts that capture live lecture transcripts so the `/cowatch` skill can read them on demand.

---

## 📜 Available scripts

| Script | Site | What it does |
|---|---|---|
| [`cowatch-coursera.user.js`](cowatch-coursera.user.js) | coursera.org/learn/* | Captures Coursera transcripts to `localStorage` every 3 seconds |

---

## 🛠️ Installation

1. Install [Tampermonkey](https://www.tampermonkey.net/) (Chrome / Firefox / Safari / Edge)
2. Click the Tampermonkey icon → **Create a new script**
3. Replace the default content with the contents of the relevant `.user.js` file
4. **Cmd/Ctrl + S** to save
5. Refresh any matching page (e.g., a Coursera lecture)
6. You should see a green badge in the bottom-right corner: `📺 Cowatch: 1432c | t=2:14`

That badge proves the script is working. Click it to copy the current transcript to your clipboard.

---

## 🤝 How `/cowatch` uses these

When you cue the cowatch skill (e.g., "look" / "thoughts?"), it executes:

```js
// Read the latest transcript chunk
JSON.parse(localStorage.getItem('cowatch_meta'))    // { url, title, videoTime, activeText, charCount }
localStorage.getItem('cowatch_transcript')           // full transcript text so far
```

Via the Claude in Chrome browser MCP. Clean text, no OCR, no screenshot lag.

---

## 🧱 Storage schema

Two `localStorage` keys are used:

```
cowatch_transcript   string            // full transcript text up to current moment
cowatch_meta         JSON object       // see below
```

The `cowatch_meta` shape:

```json
{
  "url": "https://www.coursera.org/learn/prompt-engineering/lecture/...",
  "title": "Module 1 - Overview of Large Language Models | Coursera",
  "timestamp": "2026-04-16T15:42:18.123Z",
  "videoTime": "2:14",
  "activeText": "they're learning patterns from our human language",
  "charCount": 1432,
  "phraseCount": 87
}
```

---

## 🌱 Adding a new site

To add support for YouTube, Vimeo, etc., copy `cowatch-coursera.user.js` and:

1. Update the `@match` directive to the new URL pattern
2. Update the transcript selector inside `captureTranscript()` (each site uses different DOM)
3. Test that the green badge appears and counts characters
4. Commit it here as `cowatch-{site}.user.js`

---

## 🔒 Privacy

The script writes to YOUR browser's localStorage only. No external network calls. No telemetry. The transcript stays on your machine until you (or `/cowatch`) reads it.

---

🃏📺👥
