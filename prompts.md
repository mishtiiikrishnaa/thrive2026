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

## 6 — real input, real-feeling reasoning

okay yeah — this is the right instinct twice over. a fake prompt
window with three chips was always a stand-in for "i didn't want to
build real interaction under time pressure," and you just correctly
refused to let me get away with that. and the non-determinism point is
actually the more interesting fix, because it's true: a deterministic
little animation quietly undersells the entire concept you're trying
to visualize. an ai that gives the identical response to the identical
prompt every time isn't "thinking," it's a lookup table with extra
steps.

the honest version of getting both without gambling the demo on a
live model call: **don't wire in a real ai backend.** not because you
can't, but because a live api call mid-judged-build is exactly what
goes down at minute 2:58. instead — build a *real-looking* prompt box
that does simple keyword matching against three theme-buckets, and
randomize *within* each bucket every time. from the outside
"keyword-triggered but randomized" and "actually semantic" are
indistinguishable in a 15-second demo. that's how you satisfy
"simulation" in the brief while keeping something you can trust.

better prompt themes — swap out "what should i eat" (the weakest),
use a myth/introspective bucket that pulls from the noise words so
connections feel earned:
- science — triggers: sky, blue, light, colour/color, "why is"
- craft/poetry — triggers: poem, verse, longing, "write me", love,
  line
- mythology/introspective — triggers: arjuna, dharma, hesitate,
  krishna, duty, "why did"

randomization spec, concretely:
- each bucket gets a pool of ~9 words; every submission randomly
  select 5–6 to light up. same prompt, different lit subset each time.
- each bucket gets 3 pre-written response lines; randomly pick one per
  submission. same prompt, different answer each time — the visible
  non-determinism.
- typed input matching nothing → fallback state: rays sweep the whole
  field, nothing brightens past idle, response is one of 2–3 quiet
  "still forming" lines. thematically correct, not a bug state.

the field pools (idle):
- science pool: rayleigh, wavelength, photon, scatter, atmosphere,
  spectrum, refraction, entropy, velocity
- craft pool: meter, cadence, stanza, metaphor, imagery, rhyme,
  silence, ink, verse
- myth pool: arjuna, dharma, hesitate, duty, krishna, battlefield,
  conscience, karma, doubt
- scattered noise, never matched: indigo, static, thunder, lotus,
  recursion, horizon, quartz, mirror, pulse, tide, fracture, orbit,
  whisper, carnatic, velvet, echo

interaction:
- styled text input, centered, placeholder "ask something...", submit
  button + enter-to-submit. rounded, subtle border, pink focus glow —
  an actual prompt box, not chips.
- on submit, matched bucket: random 5-6 pool words light up; typed
  prompt's words appear large bright pink top-center, staggered
  ~150ms; rays sweep, matched words brighten/scale ~20%/pink-tint with
  persistent connecting lines, others flash then fade; after ~1.5-2s
  fade in one randomly chosen response line; matched words + lines
  stay lit while the response shows.
- fallback: rays sweep the whole field, nothing brightens past idle,
  after ~1.5s fade in a random "still forming" line.
- after any submission, clear the input; field settles back toward
  idle after ~4s, ready for the next prompt.

response sets (pick one at random):
science: ["blue scatters more than the rest — that's the whole trick
  of it.", "shorter wavelengths bend easiest. blue just bends the
  most, is all.", "the sky isn't blue. it's just scattering blue at
  you loudest."]
craft: ["something with a line that means more than it says.",
  "start with an image, not a feeling. the feeling follows.", "one
  line about waiting long enough to forget what for."]
myth: ["not fear. just the weight of knowing both paths are real.",
  "duty doesn't ask if you're ready. it just arrives.", "even
  certainty pauses before it becomes action."]
fallback: ["still forming an answer to that one.", "that one hasn't
  lit up anything yet.", "not every prompt finds its shape
  immediately."]

text above the field: "not a lookup. a lighting-up." (serif); serif
for response, sans-serif for input and field words. generous spacing.

## 7 — nerve chain, spreading activation

right, ditch the poetic lines — that was me still writing gallery-copy
for something that's supposed to be explaining, not performing.

the nerve system idea is genuinely better than everything before it,
because it's not a metaphor anymore — spreading activation (one fact
fires, its shared words fire the next fact, that one fires the next)
is an actual real cognitive-science model of how association works,
and it happens to be the literal mechanism of an actual nerve impulse
too: signal arrives, cell fires, fires the next cell down the chain.
not "brain-ish vibes," the correct thing.

the mechanic, plainly:
- facts, not single words, are the nodes now. each fact is one short
  sentence sitting on screen.
- prompt comes in → any fact sharing a keyword with the prompt fires
  first (hop 1).
- hop 1 facts have their own words → any *other* fact sharing a word
  with a hop 1 fact fires next, slightly delayed (hop 2) — the actual
  nerve part, the signal visibly jumping node to node instead of
  everything lighting up at once.
- hop 2's words trigger one more fact (hop 3).
- the chain converges into one plain answer sentence at the bottom,
  built from what just lit up.

fact pools — all always visible on screen (dim at idle), grouped into
three chains (7 facts each: hop1 = facts 1-3, hop2 = 4-6, hop3 = 7):

science:
1. the sky looks blue during the day.
2. sunlight is made of many colors mixed together.
3. each color of light travels at a different wavelength.
4. blue light has a shorter wavelength than red light.
5. short wavelengths scatter more off small particles.
6. the atmosphere is full of tiny gas molecules.
7. this scattering effect is called rayleigh scattering.

craft:
1. a poem is writing arranged in lines.
2. many poems use rhythm or rhyme to shape their lines.
3. a haiku is a short poem with a fixed structure.
4. a haiku has three lines.
5. the first line of a haiku usually has five syllables.
6. free verse doesn't follow a fixed rhyme or rhythm.
7. line breaks control how a reader pauses while reading.

myth:
1. arjuna is a warrior in the mahabharata.
2. arjuna hesitates before the battle of kurukshetra.
3. he sees his own relatives on the enemy side.
4. krishna is arjuna's charioteer and guide.
5. krishna tells arjuna that fighting is his duty as a warrior.
6. this idea of duty is called dharma.
7. avoiding a duty can cause more harm than doing it.

final response lines (plain, no flourish, 2 per chain, random pick):
science: ["blue light has the shortest wavelength, so it scatters the
  most off gas molecules in the atmosphere — that's called rayleigh
  scattering, and it's why the sky looks blue.", "the sky looks blue
  because short wavelengths of light scatter more than the rest when
  they hit the atmosphere — this is rayleigh scattering."]
craft: ["a poem is shaped by its line breaks — a haiku fixes that into
  three lines, free verse uses it more loosely to control pacing
  instead of rhyme.", "poems are built from lines, not just words —
  some forms like haiku fix the structure tightly, others let it stay
  loose."]
myth: ["arjuna hesitates to fight his own relatives, so krishna tells
  him fighting is his dharma as a warrior, and avoiding it would cause
  more harm than doing it.", "before the battle, arjuna doubts
  fighting his own family — krishna's answer is that skipping his duty
  would do more harm than fulfilling it."]

interaction (paste-ready brief):
- all 21 fact sentences as small text pills, non-overlapping, dim
  (25-35% opacity, ~11-13px), same chain loosely nearer each other,
  no labels or grouping lines at idle.
- real prompt input, centered, placeholder "ask something...", enter
  or submit button, rounded + pink focus glow.
- keyword matching on submit (case-insensitive): science = sky, blue,
  light, colour, color; craft = poem, verse, haiku, rhyme, line,
  "write me"; myth = arjuna, dharma, krishna, duty, hesitate. no
  match → fallback.
- on matched chain: prompt text appears bright pink top-center; hop-1
  three nodes brighten fully, scale ~15%, tint pink, staggered
  ~150ms, with a small bright pulse dot animating from the prompt text
  to each as it fires; after ~600ms connecting lines draw to hop-2
  with pulse traveling along each line, and only 2 of 3 hop-2 nodes
  fire randomly each submission; same pulse-then-brighten for hop 3,
  connected from whichever hop-2 nodes fired; all fired nodes and
  lines stay lit; after the chain, fade in one random response line at
  the bottom, plain sans-serif, no italics, no flourish.
- fallback: pulses sweep near a few random nodes, none brighten past
  idle; after ~1s show one line at random: ["no chain fired for that
  one yet.", "that prompt doesn't connect to anything here."]
- after a response, clear the input; nodes fade back toward idle after
  ~4s, ready for the next prompt.
- text above the input, one line, plain sans-serif, no serif, no
  italics: "type something and watch what connects."
- typography: clean sans-serif throughout, no serif, no italic
  flourishes anywhere including the response line. generous spacing.
- user note: "even make the animation brain nerves like i want the
  simulation" — pulses should read as nerve impulses: signal arrives,
  cell fires, next cell down the chain.

## 8 — make it alive; brainstorm from mish-sims

this is not what i had in mind when i asked for simulating brain nerve
thing — i want to make it feel more alive first, can u do that for me?
a living breathing thing.

(then: /Users/mishti/Desktop/widgets mish/mish-sims.jsx referenced
for inspiration — a widget containing clifford attractor, diffusion-
limited aggregation, lissajous ink, murmuration (boids), and gray-
scott reaction-diffusion, all pink-on-dark with key techniques:)

borrowed from mish-sims:
- low-res offscreen buffer + layered blur compositing for soft organic
  bloom (dla/turing style) — instead of crisp 1px lines, the pink
  energy layer is rendered to a half-res canvas and drawn back
  blurred 2.5px + 9px, giving everything a breathing glow.
- energy/charge that decays — lit nodes carry a `charge` that leaks
  away each frame and edges cool to a resting hum, so the lit web
  behaves like a real fading neural trace instead of staying static.
- living motes: 60 drifting particles that curl around the field's
  core (tangential swirl) and are weakly pulled toward whichever
  nodes just fired — cytoplasm currents leaning toward active cells.
- everything already alive during idle: breathing radial glow,
  resting flicker, spontaneous sparks on idle nodes, twitch quiver,
  dendritic filaments that brighten when a neighbour fires.

## 9 — redo it: five lanes, bigger domain

(it follows the mish-sims alive pass plus feedback: "can u make it
better it looks sloppy and also can u like add more words EXPAND the
domain and it still looks bad like i dont like it either redo it or
idk looks half baked")

- replaced random scattered pills with five clean lane columns running
  top→bottom per chain, each lane a readable cascade: hop-1, hop-2,
  hop-3 terminate just above the answer card.
- the domain expanded: five chains now (science, craft, myth + new)
  mind and machine — 35 facts total, keyword sets widened.
- ~80 faint domain words drizzled through the field (including a 4th
  wordlist of sri lankan/ganga flavor) at 9-11px / 0.09-0.16 opacity
  in CMU Typewriter — reads as "everything it has absorbed".
- pulse cascade cleaned up: prompt → 3 hop-1 → 2 chosen hop-2 (each
  fed by a distinct hop-1) → hop-3. fewer crossed lines.
- weak quiver tuned down to keep text legible; pills get opaque dark
  backing so they cover the drizzle behind them; faint uppercase lane
  labels (science/craft/myth/mind/machine) that light when their chain
  fires.
- new plain response pairs for mind and machine chains.

## 10 — CMU fonts, webfont (not local)

i want cmu fonts also. and since this is going to be deployed having
fonts locally isn't gonna be enough.

- linked the computer modern unicode webfonts from cdnfonts (remote
  CDN, nothing local):
  https://fonts.cdnfonts.com/css/cmu-serif
  https://fonts.cdnfonts.com/css/cmu-sans-serif
  https://fonts.cdnfonts.com/css/cmu-typewriter-text
  with preconnect to fonts.cdnfonts.com.
- CMU Serif for the headline and the reply card; CMU Sans Serif for
  body/input/buttons/list pills/lane labels; CMU Typewriter Text for
  the faint drizzle (the machine's raw stored text).
- cdnfonts registers weights 500 and 700; canvas fonts use 700 for
  the prompt pill and 500 elsewhere (600 requested by browser gets
  synthesized).
- document.fonts.ready re-triggers resize() so canvas layout is
  re-measured with real glyph metrics after remote fonts load —
  avoids pill overlap from wrong fallback metrics on first paint.

## 11 — kill the lanes, grow a nerve plexus

still the thing doesnt quite match the vision i had. nerve endings
simulation i want not this i want nerve ending simulation this is just
looking like placeholder take inspo from sims file like messy intricate
webs like search the net for inspo also

- the five clean lane columns are gone. every fact is now a neuron
  with its own dendritic arborization (3-5 branches, each forking into
  twigs, sealed with a shimmering terminal bouton) and arbor tips that
  flare when the cell fires or an impulse brushes past.
- the whole field is one tangled plexus, grown like the mish-sims:
  fibres are straying polylines drawn every frame into a half-res
  tissue buffer with a decaying fill so they reach a stable, messy
  equilibrium — glow concentrates where fibres overlap, nothing is
  ever crisp or "placed". bloom 2.5px + 9px on top as before.
- three fibre families: per-neuron arbors (brighten with charge),
  directed axon cables between the hop cells (prompt→hop1→hop2→hop3
  impulses physically travel the actual cable paths, forking at
  branch points), and 16 wandering neuropil threads stitched across
  empty field with bouton beads en passant for texture. long chords
  also tie unrelated chains together so the web reads one organism.
- nerve impulses: bright heads + fading 18-step wakes drawn into the
  tissue, hopping a cable only after its source cell has physically
  fired. terminal endings near a passing signal flare on their own.
- rest state is alive: boutons shimmer, idle sparks crawl the neuropil
  threads every few seconds, motes drift and lean toward firing cells.
- web search inspiration: tangled surrealist nerve-ending line work,
  dendritic arborization microscopy, skeins of curling lines ending in
  glowing bouton dots on void — combined with the clifford/lissajous/
  DLA density-field idiom from mish-sims. (sources: easy-peasy
  "surrealism of tangled nerve endings", dreamstime dendritic
  arborization, stockcakes "luminous neural pathways".)
- chain identities survive as faint uppercase watermark labels
  floating above each cluster's centroid, lighting when their chain
  fires. same 35 facts, same keyword matching, same responses.
- cells scatter per-chain around jittered anchors (science/craft/myth/
  mind/machine) with relaxation so nothing stacks, clamped out of the
  reply-card window.

## 12 — nerve endings, bigger domain, any prompt answers

looks bad... like lightning struck the page. i want nerve endings.
first master that, and make the domain broader — whatever i type i
want a correct answer, i want to see the sentence form from the
existing facts.

- the jagged lightning look is dead. everything is smooth now:
  catmull-rom `smooth()` on every path, `growArbor()` draws tapered
  dendrites that fork into twigs and seal with bouton beads, cables
  hang as gentle sagging curves, and the neuropil threads are shallow
  long arcs — no sharp zigzags anywhere. tissue equilibrium for arbors
  0.009 / cables 0.006 / threads 0.005 keeps it wispy rather than
  struck-by-lightning.
- domain widened from 5 chains / 35 facts to 7 chains / ~70 facts:
  science, craft, myth, mind, machine, nature, and an "everything"
  ground-truth chain, each anchored where the plexus is spare.
- any prompt now answers. the matcher: `tokens()` strips stopwords,
  `expand()` adds a SYN synonym map (weather/water/cold/hot/sun/night/
  animal/eat/feel/fast/money/love/sad/music/language/memory/death/
  beginning/inside/together/apart/choice/grow), `scoreFacts()` scores
  per fact (raw substring +3, synonym hit +1, prefix +0.5),
  `pickChain()` takes the best chain, the top facts compose the
  sentence. if under 3 facts, it pads from the winning chain, then from
  the everything chain — so even gibberish yields a formed answer from
  stored facts.
- `compose()` rebuilds a sentence: capitals, trailing periods, joined
  with two spaces. the reply card types it out char by char (each fact
  gets a ~1s delivery window). dashed delivery threads draw from the
  lit facts into the card while it forms; discovered cable paths
  between chosen facts are added to the web as faint assocEdges that
  cool back into the tissue.
- impulses now travel the actual cable path with 14-step soft wakes
  and physical hop via charge on the target so nothing fires until the
  previous cell has fired. chain watermark labels light for the chain
  that answered.
- fixes on review before commit: `t0` was read before it was set so
  first-run impulses all fired at once — `t0 = performance.now()` now
  precedes cable construction; the delivery-thread path cache was
  sticky across runs so it is cleared at the top of every run; and the
  synthesised sentence is verified by a node smoke harness (boot +
  ten real prompts incl. gibberish → all reach forming, chains resolve:
  sky→science, recursion→machine, weather→nature, love→myth).

## 13 — staged sequence: question to the top, group of facts, nerve connections, full sentences

so like after user enters prompt the prompt goes to the top of the
page, from it the animation of keywords being chosen, and then groups
of facts are there on screen, from which connections are made just
like brain nerve connections — you watch how it's made — and then they
become sentences, and the final answer is not one sentence but full
sentences, given from the connections, from the facts.

- the piece was rebuilt around a visible four-movement sequence:
  keywords → facts → connections → answer, shown by a small stage
  indicator that lights each phase in turn (and by the actual motion
  on the plexus).
- the question itself now arrives at the top of the page (the prompt
  pill floats at ~13% height, above the plexus), and the whole run
  flows downward from it: keywords chips type themselves in beneath
  it; then the group of facts lights up; then the nerve links grow
  from the question down through the group.
- domain widened hard: ~165 facts across fourteen clusters (cosmos,
  earth, sea, life, body, mind, craft, story, machine, code, math,
  language, society, everything) with a broadened SYN synonym map, so
  almost any question has a group to wake. selection now scores every
  cell, keeps the winning chain's best up to six, then lets other
  chains' hits join the group, then fills from ground truth — the
  answer is a web, not a filing cabinet.
- the group is a real group: up to six facts (min four), each firing
  in turn with a numbered badge showing the order it was shown in;
  the winning chain watermark lights as the group wakes.
- connections are made visibly, brain-style: each link is an actual
  nerve that grows point by point with a bright tip travelling the
  path, an impulse follows over the freshly laid fibre, and the edge
  then cools into the tissue. question→fact1→fact2→… in order, plus
  one lateral skip-nerve between the first and third facts — the
  brain's redundant route — drawn but not sentenced.
- the answer is a paragraph of full sentences, not one line: every
  fact in the group becomes its own sentence (capitalised, full stop,
  joined), typed out sentence by sentence with a small breath at each
  full stop, delivered with dashed threads streaming from each lit
  fact down into the card.
- review catches: `t0` had been dropped from the state variables
  (strict-mode crash) — restored; SYN{y question} carried a stray
  `polishwed` token and DRIZZLE carried `dslswap` — scrubbed; "what
  is gravity" padded with sun/sky filler, so the cosmos chain gained
  three gravity-relevant facts (orbits as falling, the sun's pull,
  lighter/heavier falling together) and now answers head-on; answer
  card re-tuned to sit at the bottom without swallowing the stage
  line even at six sentences.
- verified by a node harness that pumps the real animation loop:
  phase sequence observed on every prompt is keywords > facts >
  connections > forming > answered > settling > idle, with group
  sizes 4–6 and full-sentence answers incl. the gibberish fallback.

## 14 — landing rebuild: centred prompt, keyword facts, brain connections, one answer sentence

looks janky as fuck. can you redo the entire thing from scratch like
(1) prompt box in the center like a landing page, (2) when clicked the
prompt goes above and keywords are chosen (with animation), (3) then
keywords should elaborate on facts each keyword represents, (4) find
connections between facts simulating brain — show nerves — they form
sentences, (5) sentence displayed.

- the whole page was rebuilt from scratch as one centred column on a
  dark landing: the ask line (input + button) floats mid-screen at
  idle, and on submit the whole column rises to the top while the
  haloed question root glows just above it — no more floating prompt
  pill, the question belongs to the page now.
- sequence is fully staged in the column itself, top to bottom:
  a "keywords" zone types the chosen chips one character at a time;
  a "the facts each keyword holds" zone lists each fact grouped under
  the question keyword it answers (keyword label + fact, reading left
  to right); a "connections" zone drops in the link chips ("1 → 2"
  etc.) as each nerve finishes; then the final "answer" sentence fades
  in at the bottom.
- the canvas is now pure brain: neurons are drawn as light only — no
  text pills on the canvas, all words live in the DOM column — so
  nothing fights the reading. fired neurons keep their numbered order
  badges; the plexus, arbors, cables, wandering threads, boutons and
  pulses are otherwise untouched from the nerve-plexus pass.
- each nerve grows crisp on the canvas the moment the DOM link chip
  appears (build scheduled at conStart + n·conEach, di-bit; lateral
  skip-nerve after the chain), then an impulse runs it and it cools
  into the tissue. delivery threads stream from each lit fact down to
  the answer while it types.
- the answer is ONE sentence composed from the group: up to four
  facts folded into a single sentence (first clause capitalised, rest
  lowercased, joined with commas and a final ", and"), typed
  character by character.
- fixes on review before commit: the answer-typing loop added dt
  inside the loop so the remainder never dropped below the char
  threshold and the whole sentence slammed out in one frame — the
  accumulator now adds dt once per frame and steps at 16ms/char, so
  the typing is actually visible; `.fkg` fact rows gained `opacity:0`
  + a transition so reveal is a fade, not a snap.
- verified by a node harness driving the real loop for five cycles:
  every prompt runs keywords > facts > connections > forming >
  answered > settling > idle, chains resolve correctly (sky/blue →
  cosmos, recursion → code, gravity → cosmos, nonsense → everything
  fallback with ≥4 facts), the answer is a single capitalised
  sentence, every fact row fades in, all zones clear between runs,
  and a quick re-run works (delivery-thread cache reset confirmed).

## 15 — don't want a single sentence, want a whole random block like a real llm

redo the entire thing, take your sweet time. i don't want a single
sentence — i want a whole block of text, sometimes a sentence,
sometimes a whole block, random each time, like a real llm (the ai is
hardly deterministic, every time it gives a different answer for the
same prompt). don't make me look like a fool. why does the landing
page already have stuff — the landing page should have nothing, just
the prompt box. the flow: i get to the page and put my prompt; i hit
enter and the prompt page goes above; the keywords are chosen; the
page splits appropriately into parts where facts related to the
keywords are generated fast with little dots next to each; another
part of the page is like a graph where as the facts are generated the
graph grows slowly and connections form like a brain's synapses; once
the graph is fully formed it disappears, only for the prompt to come
back centre; the answer — a collection of sentences relevant to the
prompt, like the graph in sentence form — is shown; and below it the
user is prompted for their next sentence.

- the answer generator is now a small llm stand-in: `generateBlock`
  rolls a shape each run — ~20% one folded sentence of 2-3 facts,
  ~35% a short 2-3 sentence paragraph, ~45% a full block of
  collapsed units — plus ~30% chance of a lead-in ("so, about
  “sky”: ", "here's how the graph answers: ", "honestly it comes
  down to this: ") and ~40% chance of a closing line ("and that is
  the shape of it." / "the nerves hold it together."), so the same
  prompt produces a different answer every time.
- fact selection is randomised too: nTarget now rolls 4-6, the
  anchor is still the best-match fact but the wander set is
  shuffled, cross-chain and filler picks are rolled fresh, and the
  display-order tie-break flips on a coin; `buildSentence` strips
  trailing `.!?` from every folded part so merges never read "…the
  moon.; and so…".
- the end-state matches the brief: when the web is fully formed it
  dissolves (delivery threads retarget to H*0.62 and the plexus
  fades twice as fast as it grew) while the answer types into the
  column; zones are cleared and the column slides back to centre;
  the answer persists below and the prompt returns to the middle and
  the input is re-enabled, refocused, placeholder "ask anything
  else…" — ready for the next sentence.
- typing speed scales with the answer: `typeRate =
  clamp(3400/len, 6, 16) ms/char` so a long block doesn't drag.
- verdict on voice sampled across two dozen throws of "sky blue",
  "recursion", "gravity", "a poem": reads like a person who folds
  connected facts — run-on mega-sentences got capped at three facts,
  and the follow-up tails were promoted to their own capitalised
  line instead of dangling off a full stop mid-thought.
- verified by the node harness at 30/30: full phase sequence with
  zones/links/dots snapshotted during connections (the zones are
  cleared when the web dissolves, so the harness looks before the
  vanish), answer typed fully and persisting into idle with the col
  centred and input handed back; recursion resolves to the code
  chain and actually mentions recursion; gibberish falls back to
  ≥4 facts; four live runs of one prompt give ≥2 distinct answer
  blocks of varying length; and both shapes are proven deterministically
  by forcing the roll through a seeded override (0.05 → one folded
  line, 0.45 → short paragraph, 0.9 → longer block) with the real
  RNG restored afterwards.

## 16 — fresh build in a NEW file (graph.html), landing page finally empty

create a new html file in this very directory — don't touch the old
one at all. the landing page should have nothing on it, just the
prompt box (the old page renders the whole plexus/neurons behind the
ask box at idle; that's the "why does the landing page already have
stuff" complaint). flow: land on a blank page with only the prompt
box → type and hit enter → the prompt goes above → keywords are chosen
→ the page splits into parts where facts are generated fast with a
little dot next to each → another part of the page is a graph that
grows slowly and forms connections like a brain's synapses as the
facts are generated → once the graph is fully formed it disappears →
only then the prompt comes back to centre → the answer (a collection
of sentences, like the finished graph in sentence form, non-
deterministic every time) is shown → and below it the user is prompted
for their next sentence.

- brand-new self-contained file `graph.html`; `index.html` is byte-for-
  byte untouched. same 14-chain domain / SYN map / stopwords as before,
  same broad keyword→fact→sentence pipeline, so any prompt still
  answers from stored facts.
- THE LANDING IS EMPTY. at idle the background canvas draws only a
  barely-there radial wash (alpha ~0.01) — no plexus, no neurons, no
  drizzle, no motes, no labels. just the centred ask line. the graph
  lives in its own panel and is only revealed during a run.
- staged flow, single centred column: submit → column rises to top →
  "keywords" zone types the chosen chips under it → the column splits
  into two side-by-side panels: the left shows the facts (each with a
  numbered little dot, revealed fast one by one) and the right is a
  dedicated graph panel whose canvas grows the plexus and lays the
  question→fact→fact… cables with travelling impulses, then the whole
  plexus dissolves (fade in `forming`/`answered`) and both panels
  collapse (`split.on` removed) — the graph visibly "disappears once
  fully formed".
- prompt returns to centre (`col.raised` removed) and the answer —
  always a collection of sentences (one folded line, a short paragraph,
  or a full block), rolled differently every run — types out below it;
  an "ask anything else…" cue pulses beneath it and the input is
  handed back, refocused for the next sentence.
- fixes caught by the drive harness before commit: `scoreFacts` keyed
  its result by the cell *object* while the selector read `scores[idx]`
  (index) — the two disagreed so scoring silently never populated and
  selection fell through to filler; and the `rest`/`everything` filler
  loops pushed `rest[r].c` on raw cells (undefined) instead of the cell
  itself. both fixed: scoring keys by index, filler pushes the raw
  cell — selection is correct for every path. a stub-dom harness boots
  the real IIFE, drives `run()` + the tick loop and confirms
  keywords → facts → connections → forming → answered on seven prompts
  incl. gibberish, 4-6 facts each, panels dissolve, column centres,
  answer shows, next-prompt cue appears.

## 17 — the graph accumulates & grows with every prompt

"the graph must grow with each prompt like accumulated — only thats
where the answers come form" and "the nodes come from facts which is
generated from keywords that is how the graph keeps growing and the
connections happen".

so the rebuild-from-scratch model is gone. the graph is no longer wiped
and redrawn each run — it now *persists and grows* for the whole
session, and every answer is read out of that accumulated web.

- new persistent model: a single `memory` list of fact-nodes, seeded
  once from the 14 curated chains (`seedMemory`), never rebuilt from
  scratch. `scoreFacts`/`pickChain`/selection now read from `memory`.
- keywords give birth to new fact-neurons: each prompt, `generateFacts`
  knits two distinct matched facts into a fresh composite statement
  ("x, which is why y…") and appends it to `memory` as a brand-new node,
  tagged with that prompt's keywords so later questions can find it
  again. one or two born per prompt — the graph visibly thickens.
- growth is deterministic and stable: positions come from a seeded PRNG
  (`srand`/`hashSeed`) so the web holds its shape across resizes; born
  nodes grow outward on a golden spiral keyed by their creation
  sequence, so old nodes don't jump when new ones appear. fired state is
  kept across every run — nodes lit in earlier prompts stay lit, so the
  graph reads as a growing, accumulating brain.
- the graph no longer "dissolves to nothing": the graph zone stays open
  through `forming`/`answered` and keeps drawing the accumulated web
  (`drawGraph` runs whenever `runCount > 0`), so you see the growth.
- the answer each run is composed from the fired graph nodes for that
  round — which now include the newly-born composites plus the best
  matched accumulated facts — so it genuinely comes from the graph.
- robustness fixes landed with this: `seedSel` treated `{c, s}` wrapper
  objects as cells (undefined `.text` → crash in `buildSentence`);
  streaming now writes to a dedicated `.ats` span instead of fragile
  `childNodes[0]`; the drive harness was rebuilt for the current DOM
  (`#log`, `#working`, `.fkg`, `.ats`) and drives many sequential prompts.
- harness check on 5+ prompts incl. gibberish: memory 154→162, grown
  nodes climbing every run (1,3,4,6,8), fired nodes accumulating
  (6,10,13,19,25), `< 6` fact rows per run (panels reset correctly),
  every run reaching `answered` with streamed text. `index.html` still
  byte-for-byte untouched.
## 18 — live browser bug: facts appeared but the graph froze and nothing followed

"i'm looking at it live — keywords show, facts show, but then it just freezes.
no answer ever comes."

the root cause was a silent NaN that had been hiding in the geometry the whole
time. `smooth()` and `catmull()` read `.x`/`.y` off their control points, but
every caller (`growCablePath`, `growArbor`) passes flat `[x, y]` arrays — so
every cable and arbor was secretly filled with NaN control points. the cable
drawing functions tolerated it (they just drew nothing), but the *fire impulse*
calls `createRadialGradient(pos.x, pos.y, ...)` on that NaN position, and that
throws — killing the whole `requestAnimationFrame` loop mid-reveal. fact rows
were revealed, then the engine died before connections/forming/answer.

fix: `catmull` now reads `p0[0]/p0[1]` and returns an array point; `smooth`
slices the end arrays. verified in a real headless Chrome session (not just the
stub-DOM harness): facts reveal, cables launch, impulses fire, the answer
streams, and the input re-enables. the same session proved it across three
consecutive accumulating prompts with no exception.

## 19 — everything CMU Typewriter, per-keyword fact series, question pinned to top, no scroll

"everything should use cmu typewriter even prompt box and each keyword should
fire a series of facts, different series of facts for each keyword, which show
in the graph and make it grow" + "the question after enter should go up and
below that only all this must happen — why scroll" + "fact series must also be
randomised across everything, nothing is fixed".

- every `font-family` is now `"CMU Typewriter Text", "Courier New", monospace`,
  including the prompt box (`#input`) and the canvas font; the now-unused
  cmu-serif and cmu-sans-serif stylesheet links were dropped (only
  cmu-typewriter-text loads).
- per-keyword fact series: new `generatePerKeyword(chips, chain)` births a
  small randomised series (2–3 fresh nodes) *per keyword*, each tagged with its
  keyword so it lands in that keyword's own panel (`fkeys` showed `sky`/`blue`,
  then `moon`/`round`/`bright`). the drawing pool is the keyword's closest
  facts **plus a shuffle of the whole memory**, so no run is fixed — every
  pair is drawn at random. all of them persist in `memory` (the graph grows);
  a capped subset joins the current round's firing and answer.
- question pinned to the top: the landing `.about` now collapses
  (`max-height:0; overflow:hidden`) when hidden instead of leaving ~600px of
  dead space, and `appendTurn` inserts the question *above* the working zone
  and appends the answer *below* it, so the column reads top-to-bottom —
  question → keywords/facts → graph → answer. `scrollBottom` anchors to
  `scrollTop = 0` instead of forcing a jump to the bottom. measured in real
  Chrome: the question sits at y=4 with the graph and answer laid out below it.

## 20 — relevance broke (blue → "borders are important"); per-keyword panels restored

"the facts arent relevant to the keyword AT ALL. like the word blue gets stuff
like 'border are important' like ????"

the relevance bug had two culprits.
- `generatePerKeyword` was drawing its fact pairs from `fam.concat(shuffle(everything))`
  — every keyword's series was mixed with a random slice of ALL memory, so
  "blue" could birth facts from the society chain ("borders are important").
  replaced with a `relatedFacts(kw, chain)` helper that only returns the keyword's
  own matches (ranked), falling back only to that keyword's chosen chain — never
  all memory.
- `keywordFor` bucketed every born fact under the FIRST chip in order, so blue-born
  facts (which carried a 'sky' tag from their source fact) landed under the sky
  panel. born facts are now assigned to the keyword they were born for
  (`cell.k[0]`), which is checked first, giving "why is the sky blue" both a
  `sky` (4) and a `blue` (3) panel, each with relevant facts.

## 21 — obsidian-style graph, no rewrite on new question, scroll fixed, named graphic.ai

"the graph looks ugly change the graph" + "asking another question it is
rewriting the graph thats already there which it shouldnt" + "scroll is not
working properly" + "name this thing graphic.ai and render it obsidian style"

- obsidian style: dropped the messy branching `arbors` and the old thick
  connectors; the graph is now a clean constellation — every node is a faint
  constellation dot (the stored web is readable before you even ask), fired
  nodes bloom as bright honey cores with a radial glow, and thin dim `drawEdge`
  lines link them. travelling fire impulses still spark along the active links.
  the graphbox got a deeper radial vignette + warmer border so the glow pops.
- no rewrite on new question: the graph panel is no longer collapsed between
  prompts (it's the accumulating brain — it stays open), removing the
  height-change re-layouts; and `buildGraphLayout` only computes node positions
  ONCE (`laidOut` guard) so later calls just re-project — the existing web never
  re-scatters. verified canvas pixel count sampled and grows cleanly across runs.
- scroll: question is inserted at the top the instant you press enter
  (`insertQuestion` + `scrollTopNow`), then the reveal unfolds below it and the
  answer is followed (scrolled-to) while it streams — no more yanking to top
  mid-answer, no forced jump to the bottom to find the question.
- branded graphic.ai in the page title, landing kicker, and graph tag.
