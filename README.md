# DocMind AI — Research & Document Assistant

An AI-powered document analysis platform that lets you upload files and have intelligent conversations about their content. Built as a single-page web application with no backend required.

---

## What It Does

DocMind AI lets you drop in PDFs, Word docs, CSVs, images, and plain text files, then ask questions about them in natural language. The AI reads all your documents simultaneously and answers with citations, so you always know which file an insight came from.

---

## Features

### Document Management
- Drag-and-drop file uploads (PDF, DOCX, TXT, CSV, MD, PNG, JPG)
- Multi-file support with per-file summaries generated on upload
- File preview modal to inspect extracted text
- Duplicate detection and size warnings

### AI Chat
- Streaming responses powered by Gemini 1.5 Flash
- Full Markdown rendering with syntax-highlighted code blocks
- Conversation memory across the full session
- Regenerate, copy, and rate any AI response
- Stop generation mid-stream

### Insights Dashboard
- Auto-generated executive summary with sentiment and complexity score
- Named entity extraction (people, places, orgs, dates)
- Keyword tag cloud
- Event timeline extracted from document content
- Per-file word count, sentence stats, and size comparison charts

### Document Tools
One-click AI workflows that run on all uploaded files:
- Summarize All
- Extract Action Items
- Generate Quiz (5 MCQs)
- Find Contradictions
- Translate Document
- Simplify Language
- Generate Outline
- Citation Finder
- Key Quotes

### Export & Sessions
- Export full chat as Markdown, plain text, or JSON
- Auto-save sessions to localStorage every 30 seconds
- Session history with restore and delete
- Export insights as a text summary
- Print-friendly view

### Search & Settings
- In-chat keyword search with highlight and jump-to navigation
- Gemini model selector (Flash / Pro)
- Response style: Concise / Balanced / Detailed
- Response language: English, Spanish, French, German, Hindi, Arabic
- Font size and theme (Dark / Light / System)
- Annotation and sticky notes on extracted text

---

## Getting Started

### 1. Get a Gemini API Key

Go to [Google AI Studio](https://aistudio.google.com) and generate a free API key.

### 2. Add Your Key

Open `index.html` and find this line near the top:

```js
const GEMINI_API_KEY = "YOUR_KEY_HERE";
```

Replace `YOUR_KEY_HERE` with your actual key.

### 3. Open in Browser

No install, no server, no build step needed.

```bash
# Just open the file directly
open index.html

# Or serve locally if you prefer
npx serve .
```

---

## Usage

1. **Upload files** — drag them into the left panel or click to browse
2. **Wait for analysis** — each file gets a one-line summary automatically
3. **Ask questions** — type in the chat or click a suggested prompt chip
4. **Explore insights** — open the right panel for entities, keywords, and stats
5. **Use tools** — run one-click workflows from the left sidebar
6. **Export** — download your chat or insights in your preferred format

---

## Keyboard Shortcuts

| Shortcut | Action |
|---|---|
| `Enter` | Send message |
| `Shift + Enter` | New line in input |
| `Cmd/Ctrl + Shift + F` | Toggle Focus Mode |
| `?` | Open keyboard shortcuts help |

---

## File Support

| Format | How It's Parsed |
|---|---|
| PDF | pdf.js (client-side, no upload) |
| DOCX | mammoth.js |
| CSV | Papa Parse |
| TXT / MD | FileReader API |
| PNG / JPG / WEBP | Sent as base64 to Gemini Vision |

All parsing happens entirely in your browser. **Your files never leave your device.**

---

## Privacy

- No backend, no database, no server
- Files are read locally using browser APIs
- Only the extracted text content is sent to the Gemini API
- Session data is stored in your browser's localStorage only
- Clearing site data removes everything

---

## Limitations

- Files over 15MB are not supported
- Very long documents may be truncated to fit Gemini's context window
- CSV analysis works best on structured, well-labeled data
- Image analysis depends on Gemini Vision's capabilities for the given image type
- Session history is tied to the browser — clearing localStorage wipes it

---

## Built With

- [Gemini API](https://ai.google.dev) — AI backbone
- [pdf.js](https://mozilla.github.io/pdf.js/) — PDF text extraction
- [mammoth.js](https://github.com/mwilliamson/mammoth.js) — DOCX parsing
- [Papa Parse](https://www.papaparse.com) — CSV parsing
- [marked.js](https://marked.js.org) — Markdown rendering
- [highlight.js](https://highlightjs.org) — Code syntax highlighting
- [Inter](https://fonts.google.com/specimen/Inter) — UI font

---

## License

MIT — free to use, modify, and distribute.
