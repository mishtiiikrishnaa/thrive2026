# graphic.ai — prompt log

each prompt that builds this site lives here, for the record.

---

## 1 — the brief

- name the site `graphic.ai`
- front page explains "how does ai work"
- user enters a prompt → site extracts keywords → generates related facts rapid-fire
- each fact is a node in a graph (obsidian-style); nodes connect and form a displayed answer
- graph persists across the chat and grows as new prompts are added
- main theme: pastel colours adjacent to `#ffa6c9`
- main font: cmu (computer modern unicode)
- landing page adds surrounding info about how ai works
- all lowercase, dark mode across the site
- build as a single html file
- log all prompts into `prompts.md`

---

## 2 — execution

- single self-contained `index.html`
- node graph rendered with a lightweight canvas force-directed layout (no external deps)
- keyword extraction + fact generation simulated client-side
- touch + click on nodes to expand the answer
- pastel palette built around `#ffa6c9`
- cmu fonts via web font link

---

## 3 — round two: fixes, fonts, fill, flair

- fact generation was invisible / not rendering → rebuilt the engine defensively
  (try/catch around the render loop so one bad frame never kills the graph; added a
  DOM polyfill for `roundRect`; extraction verified across test prompts)
- added a **live fact feed** so generated facts are always visible as text, regardless of canvas
- switched the whole site to **cmu typewriter** fonts
  (`Computer Modern Typewriter` + `CMU Typewriter Text`, monospace fallback),
  except the `graphic.ai` brand which keeps the gradient display treatment
- filled out the content:
  - expanded "how do machines learn to think?" → six numbered cards
  - new **anatomy of a transformer** section (pipeline flow with numbered steps)
  - new **glossary** of 12 terms (token, embedding, attention, backprop, hallucination,
    temperature, context window, etc.) as an accordion
- added **parallax effects**:
  - scroll + mouse parallax on the hero ambient graph
  - per-card DOM parallax driven by `data-deep` depth
- stickied the nav with a back-to-section links
- `vercel.json` rewritten to point the root `/` at `index.html` so deploy serves the new page

---

## 4 — round three: obsidian graph, chat with memory

- made the graph **obsidian-like**: camera with zoom + pan
  - scroll wheel zooms toward the cursor, drag empty space pans, touch has
    one-finger pan + two-finger pinch, and `+` / `−` / home controls in the corner
  - nodes moved to a world coordinate system projected through the camera;
    labels scale with zoom and hide when zoomed out (like a local graph)
- added a **growing chat window** beside the feed
  - every prompt appears as a user bubble; the bot replies with a summary
  - the graph itself is the memory — the newest answer aggregates **every fact node
    in the graph**, so each new answer contains everything before it
- brand kept on **cmu serif** (`Computer Modern Serif`), not the typewriter —
  for the `graphic.ai` logo, nav wordmark and footer cap
- pushed after completion

---

## 5 — round four: the graph is the star

- **graph starts empty** — the pre-seeded demo nodes are gone. first load shows a
  blank canvas with an empty-state hint ("the graph is empty — ask a question and it
  will grow"). it only grows when you actually prompt it. persistence stays, so it
  survives reloads but never invents nodes on its own.
- **the answer moved into the chat window** — removed the separate answer panel.
  the bot's "assembling…" message now becomes the final structured answer in place:
  a plain-language conclusion, keyword chips, shared-word (connector) chips, and the
  fact sources it was built from. clicking a node re-posts the fresh answer into chat.
- **label collision-avoidance on the graph** — labels skip drawing if they overlap an
  already-drawn label, so zoomed-in text stays readable instead of stacking.
- **spawn pop effect** — new nodes bloom in with a fading halo as they're added.
- **deeper "how machines learn to think"** — expanded from six to nine cards
  (added tokenization, temperature/creativity, hallucination) with heavier detail.
- **new "go deeper" section** — six deep-dive cards (scaling laws, embedding space,
  gradient flow, alignment/rlhf, sampling & temperature, myth vs reality).
- **scroll-reveal animations** — sections and cards fade up as you scroll to them.
- pushed after completion

