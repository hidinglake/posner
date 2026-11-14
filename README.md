# POSNER

A speed-matching trainer that runs in your browser.

**Play it here: https://hidinglake.github.io/posner/**

Two symbols appear. You decide, against the clock, what they have in common. It is free, works on desktop and phone, and needs no install and no account.

## What Posner is

The Posner letter-matching task is a classic experiment from the 1960s by the psychologist Michael Posner. People saw two letters and had to say, as fast as they could, whether they matched.

- Pairs that looked identical (A A) were answered fastest.
- Pairs that only shared a name (A a) were slower.
- Pairs that only shared a category (two vowels, A e) were slower again.

Those gaps showed that the mind works out sameness in layers: first how something looks, then what it is, then what kind of thing it is. This tool turns those layers into a timed drill.

## How to play

1. Tick **Numbers**, **Elements**, or both.
2. Pick a level with the slider.
3. Choose a session length: **TIME** (minutes) or **QUESTIONS** (a count).
4. Press **START** and answer each pair before the time runs out.

### The answers

| Answer | The two symbols are... | Examples |
|---|---|---|
| **MEANING** | the same thing, written two different ways | VIII and 8, He and Helium |
| **SYSTEM** | written the same way, but two different things | III and XII, He and Li |
| **DOMAIN** | the same kind of thing and nothing more | IV and 12 (both numbers), Rh and Helium (both elements) |
| **NEITHER** | nothing in common: a number next to an element | 7 and He |

NEITHER is only possible when numbers and elements are mixed, so the button only appears when both boxes are ticked. With one box ticked you get three answers: MEANING, SYSTEM and DOMAIN.

### Content sets

- **Numbers:** Arabic and Roman numerals by default. The settings can add up to five more writing systems (Latin, Greek, Cyrillic and Hebrew letters, and Morse code).
- **Elements:** the periodic table, shown by symbol (He) or by name (Helium).

Tick both and the two sets are mixed in the same session.

## Levels

The level sets two things: how long you get to answer, and how much you need to know. Higher levels are faster and cover more numbers and more elements.

| Level | Time per answer | Numbers | Elements |
|---|---|---|---|
| 1 | 3.00 s | 1 to 12 | first 12 (up to Magnesium) |
| 2 | 2.69 s | 1 to 16 | first 24 (up to Chromium) |
| 3 | 2.38 s | 1 to 20 | first 36 (up to Krypton) |
| 4 | 2.07 s | 1 to 25 | first 47 (up to Silver) |
| 5 | 1.76 s | 1 to 29 | first 59 (up to Praseodymium) |
| 6 | 1.44 s | 1 to 33 | first 71 (up to Lutetium) |
| 7 | 1.13 s | 1 to 37 | first 83 (up to Bismuth) |
| 8 | 0.82 s | 1 to 42 | first 94 (up to Plutonium) |
| 9 | 0.51 s | 1 to 46 | first 106 (up to Seaborgium) |
| 10 | 0.20 s | 1 to 50 | all 118 |

The level also adjusts itself during a session:

- **Down one level** after three misses in a row.
- **Up one level** after 32 answers with fewer than four mistakes.

To stop this, turn on **Keep level fixed** in the settings. You can also move the slider at any time, even mid-session.

## During a session

- **Stats row:** level, accuracy, time trained today, and time or questions left.
- **Feed:** your last 10 answers, newest on top. Each line shows the pair, the correct answer, and whether you were right (✓), wrong (✗) or too slow (⏱). Level changes show up in the feed too.
- **STOP** ends the session early and takes you to the results.

## Results

When a session ends you see your accuracy, the number of questions, your mistakes and your final level. **Copy results** puts a plain-text summary on your clipboard, ready to paste into a progress log or a forum post:

```
POSNER — 2026-11-14 13:02
Accuracy: 93% (37/40 correct)
Questions: 40 | Mistakes: 3
Level: 4 → 5 (2.07s → 1.76s)
Mode: Numbers 1–29 (2 systems) + Elements 1–59, mixed pairs
Session: 40 questions | Time played: 0:28
```

## Keyboard

| Answer | Keys |
|---|---|
| MEANING | `1`, `A` or `←` |
| SYSTEM | `2`, `S` or `↓` |
| DOMAIN | `3`, `D` or `→` |
| NEITHER | `4`, `F` or `↑` |

`Esc` closes the results screen. You can also click or tap the answer buttons.

## Settings (⚙)

- **Theme:** Silver (default), Dark or Cyan.
- **Writing systems:** how many number systems are in play, from 2 (Arabic and Roman) to 7.
- **Keep level fixed:** stops the automatic level changes.
- **Show accuracy during the session:** turn off to hide your accuracy until the end.
- **Buzzer:** plays a short sound after a wrong answer or a timeout.

## Progress (↗)

The progress panel keeps running totals: total time, days trained, sessions, longest session, average and best accuracy, total answers, and your current day streak. **Reset Saved Progress** clears them.

## Fair pairs

Every pair has exactly one correct answer. Symbols that could be read two ways are left out. For example, when Numbers and Elements are both ticked, a bare **I** or **V** never appears, because it could be a Roman numeral or the symbol for Iodine or Vanadium.

## Your data

Everything is saved in your own browser (local storage): your level, your settings and your progress. Nothing is sent to a server, so your progress does not follow you to another device or browser. The only outside request the page makes is to Google Fonts, for the typeface.

## Run it yourself

The whole tool is one file, `index.html`.

- **Locally:** download `index.html` and open it in a browser.
- **On GitHub Pages:** put `index.html` in a public repository, then go to Settings → Pages, choose "Deploy from a branch", pick `main` and `/ (root)`, and save. The site appears at `https://<your-username>.github.io/<repository-name>/` after a minute or two.

## Credits

- Based on the [aPOSNER trainer](https://eeemind.github.io/POSNER/) by eeemind.
- Named after the letter-matching task from Posner & Mitchell (1967), "Chronometric analysis of classification", *Psychological Review*.
- Typeface: Libre Baskerville, used under the SIL Open Font License.
