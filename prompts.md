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