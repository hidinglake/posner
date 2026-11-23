# POSNER

A speed-matching trainer that runs in your browser. Two items appear, and you decide against the clock how they are related.

**Play it: https://hidinglake.github.io/posner/**

Current iteration: **P2**.

It is free, works on desktop and phone, and needs no install and no account.

---

## Where it comes from

In 1967, the psychologist Michael Posner and Ronald Mitchell showed people pairs of letters and asked them to say, as fast as they could, whether the two were "the same". What counted as "the same" changed from block to block:

| Level | Example | Speed |
|---|---|---|
| Physical identity: they look the same | A A | fastest |
| Name identity: same letter, different form | A a | slower |
| Rule identity: same category | A e (both vowels) | slower again |

Each step down took measurably longer. From those gaps, Posner and Mitchell argued that the mind classifies things in layers: first by appearance, then by name or meaning, then by category. The method of reading mental steps from reaction times became known as *mental chronometry*.

Posner is also known for a second, separate experiment: the **cuing task** (1978–1980). There, a flash draws attention to one side of the screen, and a target then appears on the same or the other side. That task measures where attention is and how fast it moves. POSNER is built on the first experiment, letter matching, not on the cuing task.

## What the tool is trying to do

The original task asked one question per block: *are these the same at this level?* POSNER asks a harder question on every trial: **at which levels are these the same?** The player has to work out the relationship, not just confirm one that has been given.

It builds on Posner's work in four ways:

1. **All levels at once.** Instead of one yes/no judgment at a fixed level, the player has to find the most specific level at which the two items match.
2. **A new level.** POSNER adds *system* (same writing system, different meaning, such as III and XII), which the original task did not separate out.
3. **Beyond letters.** Numbers in Arabic and Roman numerals, the chemical elements of the periodic table by symbol and name, and the Greek alphabet by letter and name.
4. **Practice, not measurement.** The original was a one-session lab measure. POSNER is a repeatable drill with a response window, a pool depth, session lengths and a progress record.

### Goals

- Give a fast, honest way to practise telling *what something looks like* from *what it means* from *what kind of thing it is*.
- Keep every question fair: each pair has exactly one right answer.
- Let players track their own progress over time.

### What it does not claim

POSNER is a practice drill built on a well-studied experiment. It is not a validated training programme. No study has tested whether playing it improves attention, reasoning or speed outside the game. Scores also depend on the settings (level, content, answer mix), so compare sessions only with sessions played the same way.

---

## The screen (P2)

The play area is one compact block, placed so that the session box (the framed square that says *Waiting for session to begin* and then shows the two symbols) sits in the exact centre of the screen, across and down. The controls, answer buttons and feed are positioned around it. Both side columns are the same width, with the controls sitting against the session box. The session box and answer buttons widen with the screen, up to about 1,060 px across on large monitors, and the feed sits just beyond them. On a very short screen the block moves only as far as it can without going off the edge. The symbols and answer buttons end level with the bottom of the left-hand controls, and the block grows slightly on taller screens.

| Area | What it holds |
|---|---|
| Header | The POSNER wordmark on the left; Progress (↗) and How to play (i) on the right |
| Left column | Top to bottom: **Content** (Numbers, Elements, Greek), **Pool depth**, **Response window** and the **Auto scale** switch; then, below a divider, **Session length** (Time / Questions and its value), **START** and **STOP** |
| Centre | The two symbols in framed tiles, with the four answer buttons in a row underneath |
| Right column | The feed: your last 15 answers fill the column from the top of the game to the bottom of the answer buttons, newest on top |

- The answer buttons are white and touch each other, so the mouse only moves a short way between them. Each carries its key number (01–04). One press answers the round.
- A thin white bar between the symbols and the answer buttons shows the time left to answer. It starts full and shrinks from right to left over the response window (5.0 s down to 0.5 s), and freezes where it is when you answer.
- START and STOP sit at the bottom of the left column, level with the answer buttons.
- While a session runs, the Session length box counts down (time left, or questions left), and the rest of the left column dims so the symbols stay in focus.
- On narrower windows, four answers sit in two rows of two, and below 900 pixels wide the controls move above the symbols.


**On a phone** (900px wide or less) the screen is simplified:

- The header has a white **Setup** button beside ↗ and i. It opens a full-screen sheet with every session setting in one column (Content, Pool depth, Response window, Auto scale, Session length, with the unit beside the number, e.g. 3 min); **Done** (or `Esc`) closes it. Setup can't be opened during a session.
- The main screen is the session box, with the session length in its top-left corner (counting down during play), the time bar, one row of tall answer buttons (no key numbers) and a slimmer **START** button that turns into a red **STOP** while you play.
- The feed runs as a strip across the top of the session box, right of the session length: one small chip per answer (the pair, the result glyph and the right answer, with a coloured underline), newest on the left, pushing older ones to the right. Once the session ends you can swipe the strip sideways through every answer.
- Results appear in place of the session box.

## Design

The structure is technical and HUD-like: precise, flat and high-contrast. The colour scheme is Silver: charcoal with silver accents.

| Element | Choice |
|---|---|
| Colours | Charcoal canvas with silver accents; green START, red STOP; white answer buttons |
| Symbols and numbers | Space Grotesk Bold, tight tracking (Greek letters from Inter, since Space Grotesk has none) |
| Labels | Space Mono, capitals, wide tracking, like `RESPONSE WINDOW` |
| Wordmark | Major Mono Display, used for the POSNER name only |
| Shapes | Sharp corners, hairline borders, no shadows; the symbol tiles are framed with corner brackets like a camera reticle |

In the feed, green ✓ is right, red ✗ is wrong, and amber ⏱ is too slow.

## How it plays

Each round shows two symbols. Pick the **most specific** thing they share, before the time runs out. One press answers the round.

| Answer | Pick it when the two symbols... | Posner level it echoes | Examples |
|---|---|---|---|
| **MEANING** | are the same thing, written two ways | name identity | VIII and 8, He and Helium, β and Beta |
| **SYSTEM** | are written the same way, but are different things | new in POSNER | III and XII, He and Li, λ and π |
| **DOMAIN** | are the same kind of thing, but differ in both meaning and writing | rule identity | IV and 12, Rh and Helium, δ and Sigma |
| **UNRELATED** | have nothing in common: items from two different sets | no match | 7 and He, Iron and π |

The answers run from most to least specific: MEANING and SYSTEM, then DOMAIN, then UNRELATED. Every MEANING or SYSTEM pair is also two of the same kind, but DOMAIN is then the wrong answer, because it stops short of the real relationship. VIII and 8 is MEANING, not DOMAIN.

Identical pairs (A A, physical identity) are never shown, because they would match on every level at once.

**Content sets.** Tick any of **Numbers**, **Elements** and **Greek**:

- **Numbers:** Arabic and Roman numerals.
- **Elements:** the periodic table, by symbol or by name.
- **Greek:** the Greek alphabet, by lower-case letter or by name (β, Beta). Omicron is left out, because ο looks exactly like Latin o and zero.

Each set has exactly two ways of writing things (Arabic / Roman, symbol / name, letter / name), so MEANING, SYSTEM and DOMAIN work the same way in all three.

Ticking two or more sets mixes them in the same session, which adds the UNRELATED answer. With one box ticked, UNRELATED is hidden, because every pair then shares a domain.

**Look-alikes.** When sets are mixed, anything that could be read as an item from another set is left out, so every pair keeps exactly one right answer. Roman I and V are dropped next to elements (iodine, vanadium). Greek ι, ν and χ are dropped next to numbers (they read as I, V and X), as is the name Xi (Roman XI). Greek ι, κ, ν, ρ and υ are dropped next to elements (I, K, V, P and U). In a Greek-only session all 23 letters are used.

With no box ticked, START stays greyed out and the screen reads *Select content to begin*. During a session the last ticked box can't be cleared.

**Grading.**

| Result | Meaning | In the feed |
|---|---|---|
| Right | You picked the most specific answer | green ✓ |
| Wrong | You picked anything else, including a true but less specific answer | red ✗ |
| Too slow | You picked nothing in time | amber ⏱ |

The feed always shows the right answer for each pair.

**How to play.** The **i** button in the header opens a guide. It explains the four answers, with example pairs from each set, and the most common mistakes. It also lists the content sets and their two ways of writing, what each setting does, the keys, and what right, wrong and too slow mean.

---

## Response window and pool depth

Speed and breadth are set separately, so you can train one without the other getting in the way.

**Response window** is how long you have to answer: ten steps, half a second apart, from 5.0 s down to 0.5 s. ‹ shortens it and › lengthens it.

**Pool depth** is how many items are in play: ten steps. ‹ makes it shallower and › makes it deeper. Under it, all three ranges are always listed (Numbers, Elements, Greek); sets you haven't ticked are dimmed, so the box never changes size.

| Step | Response window | Pool depth: numbers | Pool depth: elements | Pool depth: Greek |
|---|---|---|---|---|
| 1 | 5.0 s | 1 to 12 | first 12 (up to Magnesium) | α to ζ (6) |
| 2 | 4.5 s | 1 to 16 | first 24 (up to Chromium) | α to θ (8) |
| 3 | 4.0 s | 1 to 20 | first 36 (up to Krypton) | α to κ (10) |
| 4 | 3.5 s | 1 to 25 | first 47 (up to Silver) | α to μ (12) |
| 5 | 3.0 s | 1 to 29 | first 59 (up to Praseodymium) | α to ξ (14) |
| 6 | 2.5 s | 1 to 33 | first 71 (up to Lutetium) | α to π (15) |
| 7 | 2.0 s | 1 to 37 | first 83 (up to Bismuth) | α to σ (17) |
| 8 | 1.5 s | 1 to 42 | first 94 (up to Plutonium) | α to υ (19) |
| 9 | 1.0 s | 1 to 46 | first 106 (up to Seaborgium) | α to χ (21) |
| 10 | 0.5 s | 1 to 50 | all 118 | α to ω (all 23) |

The two are independent: any window works with any pool. New players start at 2.0 s (step 7) and pool depth 1. Settings saved under the older six-step scales are moved over once: the window keeps its seconds and the pool moves to the nearest range.

### Why they are separate

New or unfamiliar items need time to recognise. If the time limit shrinks at the same moment new items arrive, players guess instead of learning, and a miss could mean either "too slow" or "didn't know it". Posner's own task used letters everyone already knew, so slower answers reflected deeper processing, not gaps in knowledge. Keeping the two controls apart keeps that distinction.

### Auto scale

With the **Auto scale** switch on, both controls adjust to how you are doing during a session:

- **A strong run** (16 answers since the last change, with at most 2 mistakes):
    - if your speed is ahead of your pool (the window step is higher than the pool depth), the pool gets one step deeper and the window one step longer, so new items arrive with more time;
    - otherwise, the window gets one step shorter.
- **Three misses in a row:** the window gets one step longer. If it is already at its longest (5.0 s), the pool gets one step shallower instead.

So speed leads and depth follows, in a sawtooth: faster, then deeper with a little more time, then faster again. Every change is noted in the feed (for example `FASTER → 1.5S` or `DEEPER → POOL 3 · 2.5S`). Wherever a session ends becomes the starting point for the next one.

With the switch off, the window and pool stay exactly where you set them. The ‹ › arrows work at any time.

## Sessions and results

- Set a session by **TIME** (minutes) or **QUESTIONS** (a count), then press **START**. **STOP** ends early.
- The Time / Questions box counts down during the session. Your accuracy appears on the results screen at the end.
- The feed beside the game shows your last 15 answers, newest first. It keeps every answer of the session: once the session ends or you press STOP, a scroll bar appears so you can scroll back through all of them. On a phone the feed sits under the game and the page itself scrolls. Starting a new session clears it.
- At the end you see accuracy, questions, mistakes, and the final response window and pool depth. **Copy results** puts a plain-text summary on your clipboard:

```
POSNER — 2026-11-22 19:52
Accuracy: 90% (36/40 correct)
Questions: 40 | Mistakes: 4
Response window: 3.0s → 2.0s
Pool depth: 1 → 3 (Numbers 1–20 + Elements 1–36, mixed pairs)
Auto scale: on
Session: 40 questions | Time played: 0:25
```

## Keyboard

| Answer | Keys |
|---|---|
| MEANING | `1`, `A` or `←` |
| SYSTEM | `2`, `S` or `↓` |
| DOMAIN | `3`, `D` or `→` |
| UNRELATED | `4`, `F` or `↑` |
| Close results or the How to play panel | `Esc` |

## How to play and progress

- **i How to play:** the four answers with examples, common mistakes, the content sets, settings, keys and results.
- **↗ Progress:** total time, days trained, sessions, longest session, average and best accuracy, total answers and day streak. **Reset Saved Progress** clears them.

Everything is saved in your own browser. Nothing is sent to a server, so progress does not follow you to another device. The only outside request is to Google Fonts, for the typefaces. If it cannot be reached, the page falls back to the system's own sans-serif and monospace fonts.

## Running it

The whole tool is one file, `index.html`.

- **Locally:** open `index.html` in a browser.
- **On GitHub Pages:** put `index.html` and this README in a public repository, then Settings → Pages → "Deploy from a branch", `main`, `/ (root)`, Save. The site appears at `https://<username>.github.io/<repository>/` within a minute or two.

## References

- Posner, M. I., and Mitchell, R. F. (1967). Chronometric analysis of classification. *Psychological Review*, 74(5), 392–409.
- Posner, M. I. (1978). *Chronometric Explorations of Mind*. Hillsdale, NJ: Lawrence Erlbaum Associates.
- Hayward, D. A., and Ristic, J. (2013). Measuring attention using the Posner cuing paradigm: the role of across and within trial target probabilities. *Frontiers in Human Neuroscience*, 7, 205. https://pmc.ncbi.nlm.nih.gov/articles/PMC3656349/

## Credits

- Based on the [aPOSNER trainer](https://eeemind.github.io/POSNER/) by eeemind.
- Typefaces: Space Grotesk, Space Mono, Major Mono Display and Inter (Greek letters only), all under the SIL Open Font License, served by Google Fonts.
