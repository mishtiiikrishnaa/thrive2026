# graphic.ai — prompt log

landing rebuilt: knowledge graph with nodes (cards + deep + glossary headings) positioned as an interactive obsidian-style network. clicking a node expands it; others fade to 0.35 opacity. no parallax. graph below prompt untouched. old sections (#how, #anatomy, #glossary, #deep) hidden.

---

- landing = `#landing-graph`: 26 nodes (9 cards, 6 deep headings, 11 glossary headings) as absolute-positioned `.node` circles
- click `.node` → `.expanded`: scale 1.4, full opacity, others fade + grayscale
- edges drawn with inline `<svg>` lines in `.node-connector`
- `display:none` on `#how`, `#anatomy`, `#glossary`, `#deep`
- parallax removed, obsidian `#graph-bg` canvas kept behind
- `prompts.md` updated
