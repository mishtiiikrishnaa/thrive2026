# graphic.ai — prompt log

every prompt that built this site lives here, for the record.

---

## the full build — everything in one pass

- **single-file dark-mode site** — `index.html` only, no dependencies, deploys to vercel at `/` via `vercel.json` rewrite
- **brand: `graphic.ai`** in cmu serif (`Computer Modern Serif`), gradient treatment; everything else in cmu typewriter (`Computer Modern Typewriter`, `CMU Typewriter Text`)
- **pastel palette** centred on `#ffa6c9` (pink, lilac, mint, peach, sky, cream) — dark mode everywhere, all lowercase

---

### the graph (the whole point)

- **starts empty** — blank canvas with "the graph is empty — ask a question and it will grow". no pre-seeded nodes. it only grows when you actually prompt.
- **persists across reloads** — localStorage (`graphicai_graph_v1`) saves every node and edge; the graph remembers everything. chat resets on reload (fresh session), graph does not.
- **obsidian-style camera** — scroll wheel zooms toward cursor, drag empty space pans, touch has one-finger pan + two-finger pinch, `+` / `−` / `⌂` controls in corner. world coordinates with device-pixel-ratio scaling.
- **force-directed layout** — spring/repulsion physics, pinned nodes, age-based spawn pop (new nodes bloom with a fading halo), label collision avoidance (labels skip if they'd overlap an already-drawn label).
- **legend** — pink = keyword cluster, lilac = fact node, mint = shared-word connector.

---

### prompt → keywords → facts → graph growth

- **type a prompt** (e.g. "why is the sky blue?")
- **extract keywords** — known words from a curated whitelist + unknown words from the prompt (up to 3)
- **real facts per keyword** — each keyword spawns 3 substantive facts:
  - whitelisted words (ai, learning, neural, attention, transformer, etc.) have hand-written facts
  - unknown words (sky, blue, colour, light, gravity, love, brain, sleep, dream, etc.) get generated real facts from a large concept bank (rayleigh scattering, wavelength physics, brain chemistry, etc.) — **no generic filler metatext**
- **rapid-fire spawn** — facts appear one by one (~260ms each) with a pop animation, linked to their keyword cluster node
- **shared-word connectors** — after each prompt, the system finds words that appear in facts across two or more clusters (stemming: wavelengths↔wavelength, colours↔colour, particles↔particle). every connector node gets a **distinct label** — never "data, data, data". connectors sit between clusters and link both.

---

### the answer lives in the chat window

- **no separate answer panel** — the bot's "assembling…" bubble becomes the final structured answer in place
- **answer format**:
  - plain-language conclusion: "putting it together: the graph connects sky, blue through the shared idea colour. click the facts in the graph to see how each one feeds the answer."
  - keyword chips (clickable topics)
  - shared-word chips (the mint connector nodes that bridge clusters)
  - fact sources list (up to 8 facts with truncated labels)
- **click any node** in the graph → re-posts a fresh answer reflecting the current graph state

---

### layout: graph front and centre

- **top**: the graph — full width, tall (68vh, min 460px). the star of the page.
- **middle**: prompt controls centered below the graph
- **bottom**: workings — two-column row: left = chat (where the answer appears), right = fact generation feed

---

### surrounding content (below the graph)

- **how do machines learn to think?** — 9 detailed cards:
  1. training (data writes the rules)
  2. weights (millions of nudged numbers)
  3. attention (every word weighs every other)
  4. inference (forward prediction loop)
  5. loss & backprop (error walked backwards)
  6. generation (probable pieces recombined)
  7. tokenization (text → tokens → numbers)
  8. creativity & temperature (randomness dial)
  9. hallucination (confident invention without grounding)
- **anatomy of a transformer** — 8-step pipeline: embed → positional → attention stack → feed-forward → norm/residual → output head → sample → repeat
- **go deeper** — 6 deep-dive cards: scaling laws, embedding space, gradient flow, alignment/rlhf, sampling & temperature, myth vs reality
- **glossary** — 12 accordion terms: token, embedding, attention, backprop, hallucination, temperature, context window, weight, inference, alignment, scaling law, loss
- **scroll-reveal animations** — sections and cards fade up as you scroll into them
- **parallax effects** — hero ambient graph responds to scroll + mouse; per-card DOM parallax by `data-deep` depth

---

### technical

- **zero external deps** — vanilla JS, canvas, localStorage
- **defensive rendering** — try/catch around every frame, `roundRect` polyfill
- **fonts loaded via google fonts** — cmu serif + cmu typewriter
- **vercel.json** rewrites root `/` → `index.html`

---

### git history

- `972bc51` — initial obsidian-style graph, richer landing
- `4e4281e` — graphic.ai v1: growable fact-graph, cmu typewriter, parallax
- `1fe3136` — obsidian zoom/pan, growing chat with cumulative memory, cmu serif brand
- `0c5dd5e` — graph empty start, answer in chat, label collision-avoidance, deeper content + go-deeper section, spawn pop, scroll reveal
- **HEAD** — real facts for any keyword, distinct connectors, graph-front-and-centre layout, self-tested end-to-end