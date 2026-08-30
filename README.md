# graphic.ai

a single-file dark-mode website that explains "how does ai work" through a living, growing knowledge graph.

## what it does

you type a question. the system extracts keywords, generates real facts for each keyword, spawns them as nodes in an interactive graph, finds shared words between topics as connector nodes, and assembles a final answer in the chat window — all from the graph you just built.

**the graph is the centerpiece** — it starts empty, grows only from your prompts, persists across reloads (localStorage), and has an obsidian-style zoom/pan camera.

## flow

```
prompt → extract keywords → 3 real facts per keyword → rapid-fire node spawn
→ shared-word connectors (distinct, never repeated) → final answer in chat
```

## layout (top to bottom)

1. **hero** — ambient parallax graph (scroll + mouse)
2. **the graph** — full-width, tall, interactive (zoom, pan, pinch, drag nodes)
3. **prompt controls** — centered below graph
4. **workings** — chat (answer lives here) + fact generation feed side by side
5. **theory sections** — how machines learn (9 cards), transformer anatomy, deep dives (6), glossary (12)

## tech

- **zero dependencies** — vanilla JS, canvas, localStorage
- **fonts** — cmu serif (`Computer Modern Serif`) for brand, cmu typewriter (`Computer Modern Typewriter`) for everything else
- **palette** — pastels around `#ffa6c9` (pink, lilac, mint, peach, sky, cream)
- **deploy** — vercel rewrite `/` → `index.html`

## run locally

```bash
# open index.html directly in a browser
# or serve
npx serve .
```

## prompt log

see `prompts.md` for the complete build history.