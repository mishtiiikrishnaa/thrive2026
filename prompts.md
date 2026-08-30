# prompts

log of every prompt in this chat window.

---

## 1 — build the gallery piece

build a single-page website. dark near-black background (#0a0a0f).
one accent colour used sparingly: #ffa6c9 (carnation pink) — everything
else stays muted white/grey. no nav bar, no extra sections, no scroll
past one and a half screens. the animation is the point; everything
else is scaffolding.

hero (full viewport):
a canvas/svg animation. small particles enter from the top of the
screen and fall downward. they pass through three faint horizontal
translucent bands, labelled subtly along the left edge: "pattern",
"weight", "connection". crossing each band, particles split, merge,
reroute — most fade to grey/dim and vanish, a shrinking few stay lit.
by the bottom all remaining particles converge into a single pulsing
pink (#ffa6c9) node. runs automatically on loop, and also re-triggers
on click anywhere on the canvas — show "click to feed it a thought"
as a small caption under the canvas.

below hero, centred, max-width ~600px:
- serif headline: "the room where it decides"
- lighter sub-line under it: "every choice a model makes happens in
  a space you can't see. here, you can."
- one short body paragraph, generous line-height

footer:
one italic line only. quiet, small, centred.

typography: serif for headline, clean sans-serif for everything else.
keep spacing generous — this should feel like a gallery piece, not
a saas landing page.

## 2 — log the prompts

create `prompts.md` in the repo root, log this conversation so far into
it (each prompt as an entry), and log every future prompt in this chat
window to the same file as we go.

## 3 — commit after every prompt

after every prompt commit to github please! with appropriate lowercase
messages!

## 4 — scrap it, here's the real idea

oh — okay, yeah, scrap what i gave you, this is better. mine was
"generic ai-decision-tree animation #4,281." yours is actually your
idea, running the same shape as your own actual academic throughline
(a prompt as raw input, tested against existing structure, connections
lighting up, response as something that *emerges* from the pattern
rather than getting pulled off a shelf) — and it happens to also be
visually the same language as the constellation-node thing you're
already building for the swift challenge. that's not a coincidence you
need to lean into, that's just what your brain does. use it.

the sequence, staged:
1. a scatter of ~50 faint dots across the screen on load — "everything
   already known." a few loosely clustered rather than perfectly even,
   so it reads as *structured* not random, without you having to label
   anything.
2. click a prompt → its words drop in one at a time as small glowing
   seed-points.
3. from each seed, thin rays sweep out and test nearby dots — most
   fizzle, a handful catch and light up, with a line now connecting
   seed → dot.
4. where two different words' connections land near the same dots,
   those connections glow brighter — that's your "pattern" moment,
   visualized as literal overlap.
5. the brightest cluster pulses and condenses into one point.
6. a short response fades in below it — the answer arriving *from* the
   lit structure, not from nowhere.

build decision: use preset prompt chips (2–3 fixed examples), not a
free-text box.

the paste-ready brief (as given):
- background constellation: ~50 small dots (2-3px), dim grey/white
  (~30% opacity), 3-4 loose clusters, idle twinkle/drift.
- 3 preset prompt chips: "why is the sky blue", "write me a poem",
  "what should i eat". no free text.
- on click: words drop one at a time as pink seed-points (~150ms apart,
  from the top edge); rays sweep out testing nearby dots, most fade,
  4-8 per seed catch and light pink with a solid linking line; where
  lines from different words converge on the same dots, make those
  connections/dots visibly brighter and thicker; after ~1.5-2s the
  brightest connected cluster pulses once and condenses into a single
  point; a one-line response fades in below the constellation; a "run
  again" affordance resets with a fresh scatter.
- text centered above the constellation, one line only, serif:
  "not a lookup. a lighting-up."
- sans-serif for chips and response line. gallery piece, not a product
  demo.
- if the tool chokes on the full six steps, cut step 3 (brightness
  overlap) first — steps 1, 2, 4, 5 are load-bearing.

## 5 — words, not dots

yeah — no, i get it, and it's a better version of what i gave you last
time, ngl. you don't want dots pretending to be knowledge, you want the
knowledge itself sitting there, legible, so someone watching can
actually read "oh, it has 'rayleigh scattering' floating in there"
before it even connects to anything. dots are a metaphor *about*
knowledge. words are the knowledge. that's the upgrade, and it's the
right one.

revised background: replace the 50 dots with ~40 actual short text
fragments, scattered across the viewport at wildly different opacities
and sizes (10–22px, 20–50% opacity at idle) so it reads as "everything
this thing has ever absorbed," not a curated hint list. loosely cluster
a handful of them by theme — not because the viewer needs to parse the
clustering consciously, but because dense pockets read as "this is
where the deep stuff lives" even at a glance.

give the ai tool actual words, don't let it invent them on the fly.
the provided sets:
- science-adjacent cluster: rayleigh, wavelength, photon, scatter,
  atmosphere, entropy, gravity, velocity
- craft/poetry cluster: meter, cadence, stanza, metaphor, imagery,
  rhyme, silence, ink
- appetite/ritual cluster: hunger, spice, comfort, craving, warmth,
  ritual, coffee, salt
- noise (unclustered): arjuna, dharma, indigo, static, thunder, lotus,
  recursion, horizon, quartz, mirror, pulse, tide, fracture, orbit,
  whisper, carnatic, velvet, echo

the sequence, updated:
1. field idles — all ~44 words drifting faintly, unreadable-at-a-glance
   opacity, occasional slow twinkle.
2. click a chip → its actual words appear large and bright pink near
   the top, one at a time.
3. from each prompt-word, a visible ray sweeps the field. as it passes
   near a background word, that word flashes — dims back down if it's
   not a real match, but brightens, scales up ~20%, and turns
   pink-tinted if it is, with a solid line drawn from the prompt-word
   to it. so "why is the sky blue" sweeps and specifically catches
   rayleigh, scatter, wavelength, atmosphere — you *watch* it find the
   right words, not just glow randomly.
4. where lines from two different prompt-words land near the same
   background word, brighten that connection more than the rest —
   the pattern-recognition beat, with legible payloads.
5. response fades in below — and the words that fed it stay lit and
   connected the whole time, so the answer visibly has receipts.

stretch goal (only if clean with time to spare): the lit words detach
and drift into position to spell the answer. cut it without guilt.

matched sets per chip:
- "why is the sky blue" → rayleigh, scatter, wavelength, atmosphere,
  photon → "blue light scatters more than any other wavelength when it
  hits the atmosphere."
- "write me a poem" → meter, cadence, stanza, metaphor, rhyme, silence
  → "something with cadence, and one line that means more than it
  says."
- "what should i eat" → hunger, comfort, spice, warmth, craving →
  "something warm. something that isn't just calories."

text above the field, centered, max-width 500px, one line, serif:
"not a lookup. a lighting-up." serif for headline + response line,
sans-serif for chip buttons and all field words. generous spacing.
if layout chokes (overlap, unreadable at idle), drop word count from
44 to ~28 first — cut unclustered noise words, keep every
clustered/matched one.