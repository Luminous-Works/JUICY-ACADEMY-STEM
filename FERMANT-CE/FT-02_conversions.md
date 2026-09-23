# JUICY Academy — FT-02 · Conversions

> *Musicians count what physicists multiply.*

**Program:** JUICY Academy STEM Curriculum
**Track:** FERMANT-CE — the synth that proves its own theorems
**Division:** Luminous.Works LLC
**Audience:** Advanced high school / college
**Prerequisites:** FT-01 (the harmonic series). Exponents and logarithms — or a willingness to meet them properly, here.
**Lab:** FERMANT Community Edition — the keybed, REDSHIFT (the Doppler disk), and the arpeggiator strip
**Time:** ~90 minutes

---

## 1 · Two number systems

In Jamaica we build songs on **riddims** — one instrumental track, and then voice after voice
riding it, decade after decade. The riddim works because everybody agrees on the same grid
before anybody plays a note: the tempo, and the key.

But notice what the musicians are actually counting. Not hertz. Not seconds. A singer says
"take it up a semitone." A drummer says "count it in." The musician's units are **semitones,
cents, beats, and bars**. The physicist's units are **hertz and seconds**. And the two
number systems do not match — not even a little. The keyboard is not a ruler marked off in
equal hertz-steps; the tempo grid is not marked off in equal anything. Each of the
musician's units is a *logarithm or a reciprocal* of the physicist's.

This module is the dictionary. It teaches the algebra that translates between the two
systems — and every formula gets checked against your ears.

## 2 · The octave is a doubling

Sit at the FERMANT keybed. The computer's letter row plays it chromatically: **Z** is C,
then S, X, D, C, V, G, B, **N** (that's A), and so on up the row. Press **N** and hold it.
Now press **P** — the octave-up key — and press N again.

Same key. Same letter. But the sound jumped up an octave, and here is the entire secret of
pitch: **an octave is not a distance, it is a ratio.** The note you hear now vibrates
exactly *twice as fast* as the one before. Press **P** again: four times as fast. Press
**O**: half.

If A4 — the A above middle C — is fixed by international convention at 440 Hz, then the
keyboard's A-column is the doubling chain:

```
A1 =  55 Hz        A3 = 220 Hz        A5 = 880 Hz
A2 = 110 Hz        A4 = 440 Hz        A6 = 1760 Hz
```

The keyboard does not count hertz. It counts **doublings** — and it slices each doubling
into twelve equal *ratios*, the semitones. Which brings us to the strangest number in
music.

## 3 · The twelfth root of two

One octave = twelve semitones = a doubling. So one semitone must be the number that,
multiplied by itself twelve times, equals 2:

```
s¹² = 2        s = 2^(1/12) ≈ 1.0594630…
```

Up a semitone: **multiply by 1.05946**. Up an octave: multiply by it twelve times. The
keyboard, for all its black and white regularity, is built on an irrational number — and it
cannot be any other number, because the constraint is exact: twelve identical ratios must
make a factor of two. (That irrationality is a two-line proof by contradiction with even
and odd; it is Checkpoint 6.)

So the general law, for a note *k* semitones above A4:

```
f = 440 · 2^(k/12)
```

And run it backwards — the note you assign to a frequency *f*:

```
k = 12 · log₂(f / 440)
```

This is the whole trade. **Frequency is exponential in note-number; note-number is
logarithmic in frequency.** The logarithm is not a decoration here — it is the unit
conversion. It is what turns the physicist's multiplication into the musician's addition.

## 4 · Lab I — conversions you can hear

**Exercise A — the doubling ladder.** Press **N**, and step up with **P** four times. Each
press you hear the identical letter reborn. Compute the frequencies of A3 through A6 and
write them next to the four pushes. That *sameness* your ear reports at every octave — the
sensation that A2 and A4 are "the same note" — is your auditory system detecting a
**ratio of 2**. (FT-01 explained why: the whole harmonic series of A2 sits inside the
series of A4. The octave is the one interval where every partial of the lower note has a
partner in the higher. The ear noticed the arithmetic before you did.)

**Exercise B — compute, then play.** Before touching the keyboard, compute C5. It is three
semitones above A4: 440 · 2^(3/12) ≈ 523.25 Hz. Then compute C4: nine semitones *below*
A4: 440 · 2^(−9/12) ≈ 261.63 Hz — middle C. Now find each on the keyboard and check the
letter. The keyboard has no frequencies printed on it, and it does not need them: the
formula *is* the map.

**Exercise C — hear the difference frequency.** Press **O O** to drop two octaves, then
hold **Z and S together** — C2 and C♯2, one semitone apart. You will hear a single rough
tone *pulsing* — that pulsing is **beating**: two frequencies close together alternate
between reinforcing and cancelling, and the beat rate is exactly their difference.

Compute it. C2 = 440 · 2^(−21/12) ≈ 65.41 Hz. C♯2 = 65.41 × 1.05946 ≈ 69.30 Hz. Difference
≈ **3.9 beats per second**. Count the pulses for ten seconds against a watch — you should
count close to 39. You just measured the irrational number 2^(1/12) with your ear.

## 5 · Just vs. tempered — the great compromise

Now the painful part. The ratios that sound *purest* are the small fractions from FT-01's
harmonic series: the octave 2:1, the perfect fifth 3:2, the fourth 4:3, the major third
5:4. When two notes share a small whole-number ratio, their partials interlock and the
interval sounds clean.

But the piano-style keyboard cannot use those pure ratios and still close the octave into a
circle. Stack twelve *pure* fifths (×(3/2) each) and you land on (3/2)¹² ≈ 129.75 — which
overshoots seven octaves (128) by a factor of 1.0136. That gap is the **Pythagorean
comma**, about 23.5 cents wide. (The *cent* is the musician's fine unit: 100 cents =
1 semitone, so 1200 cents = 1 octave. To convert any ratio *r* to cents:

```
cents = 1200 · log₂(r)
```

— the same logarithm wearing concert clothes. Check it: the pure fifth 3:2 is
1200·log₂(1.5) = **702 cents**; the keyboard's fifth is exactly **700**. The keyboard's
fifth is flat by two cents. Its major third is worse: pure 5:4 is **386**, the keyboard
plays **400** — fourteen cents sharp. Every "in tune" chord on an equal-tempered keyboard
is a negotiated settlement.)

Equal temperament is the compromise: twelve identical semitones, every key equally
slightly wrong, every key usable. That is the arithmetic price of being able to play in
all twelve keys without retuning — the price the whole world agreed to pay so that one
instrument could follow any song into any key.

**Exercise D — hear the settlement.** Two octaves down again, hold **Z and C together** —
C2 and E2, the equal-tempered major third. C2 ≈ 65.41 Hz; E2 = 65.41 · 2^(4/12) ≈ 82.41 Hz.
The *pure* third of C2 would be 65.41 × (5/4) = 81.76 Hz. The tempered third sits 0.65 Hz
above it — close enough that the two sets of partials pull against each other. Listen for
a slow wobble in the sustained chord: that is the settlement, audible. The keyboard did
not give you the pure third; it gave you the third that works in every key at once.

## 6 · REDSHIFT — pitch without the ladder

The keyboard is a staircase: twelve fixed ratios to the octave. But pitch is continuous —
a singer does not climb semitone-steps, and neither does the Doppler effect. Open
**REDSHIFT**, FERMANT's Doppler disk (it replaces the old pitch and mod wheels), and drag
it **vertically**: the note bends smoothly, with no steps, through every ratio between the
keys. Horizontal motion shifts the formants — the vowel, not the note.

Two things to notice, both mathematical:

1. The disk's full vertical throw spans about ±9.4 semitones — nearly an octave each way —
   and the bend is smooth the whole way. Between any two adjacent keys live infinitely
   many pitches, every one a ratio; the keyboard is a *raster* of a continuum.
2. As you drag, your hand moves in equal *distances* but the frequency multiplies by equal
   *ratios*. The disk is calibrated in semitones and cents — the logarithmic units — not in
   hertz. A control surface for pitch could not be built any other way: a linear-in-hertz
   wheel would spend its whole travel in the bottom octave and be dead by the third.

This is what a Doppler shift is: a moving source trading pitch for velocity, f′ = f(1 ± v/c).
The disk is named for the physics on purpose.

## 7 · Lab II — the time conversions

Back to the riddim. Set the metronome thinking: open the **arpeggiator strip** above the
keybed (turn **ARP** on and pick any pattern), and find the **BPM** box. The fundamental
law of tempo is a reciprocal:

```
seconds per beat = 60 / BPM
```

At 120 BPM, one beat = 0.5 s. Set the rate to a quarter-note division and listen: two
clicks a second. Now the arithmetic of the **rate divisions**, which is fractions with a
referee:

- **1/4, 1/8, 1/16, 1/32** — each step halves the period: 0.5 s → 0.25 → 0.125 → 0.0625.
  You hear binary division; the fraction's denominator *is* the sound.
- **Dotted** — multiply the duration by 3/2. Dotted 1/8 at 120 = 0.375 s.
- **Triplet** — three notes in the span of two: multiply by 2/3. Triplet 1/8 at 120
  ≈ 0.167 s.

**Exercise E — verify the grid.** At 120 BPM set the rate to 1/8 and count the clicks
against a watch for ten seconds. You should count about 80 — eight per beat × four beats ×
ten seconds × 0.5 s each. Change only the BPM to 60 and predict the count before you
measure. (Answer: 40. The count halves because the period doubled.)

**Exercise F — reverse-engineer the tempo.** Find the BPM that makes a 1/16 note last
exactly one-tenth of a second. Write the equation before you touch the box:
60/(BPM·4) = 0.1 → **BPM = 150**. Set it, listen, and count. When your algebra and your
ears agree, you have done what producers do daily — solved for the grid.

The tempo-synced **delay** obeys the same law in echo: set a division and the repeats
arrive on the same grid you just computed. One equation, two audible consequences — the
riddim's clock, and its ghost.

> **The riddim corner.** Tempo ranges are a genre's signature, and ours are exact:
> dancehall lives around **100–105 BPM**; reggae around **70–80**. Set the BPM box to 102
> and start any arpeggio — that is the dancehall pocket. Drop to 75 and feel the space
> open up: same arithmetic, different gravity. When a producer says a riddim runs at 102,
> they are naming the one number every voice that ever rides it must agree on. The whole
> tradition is a tempo grid with a generation of songs on it.

## 8 · The conversion sheet

| From | To | Formula |
|---|---|---|
| note *k* semitones above A4 | frequency | f = 440 · 2^(k/12) |
| frequency | note (from A4) | k = 12 · log₂(f/440) |
| ratio *r* | cents | c = 1200 · log₂(r) |
| cents | ratio | r = 2^(c/1200) |
| BPM | seconds per beat | t = 60/BPM |
| beat division *n* (with dotted ×3/2, triplet ×2/3) | seconds | t = (60/BPM) × 4/n |
| close frequencies f₁, f₂ | beats per second | b = \|f₂ − f₁\| |

Every row was verified by ear in this module. That is the standard.

## 9 · Checkpoint problems

1. Compute A5 and C4. Then compute E5 (seven semitones above A4) and G4 (two below).
2. In cents, by the formula: the pure fifth 3:2, the pure major third 5:4, and the pure
   minor third 6:5. Compare each to its keyboard value (700, 400, 300) and give the error
   in cents for each.
3. **The comma.** Compute (3/2)¹² / 2⁷ and convert to cents. This is the gap equal
   temperament exists to hide.
4. Two strings sound at 220.00 Hz and 221.50 Hz. Give the beat rate, then the interval in
   cents, then — the hard part — one sentence on why the beat rate and the cent-size are
   different numbers describing the same pair.
5. At 96 BPM, how many seconds is a **dotted 1/16**? Write the chain of multipliers.
6. **The fretboard is a logarithmic ruler.** A guitar string's scale length is *L*. The
   n-th fret must shorten the string to L·2^(−n/12). Show that the fret's distance from
   the nut is L·(1−2^(−n/12)), and compute the first three frets' positions for L = 650 mm.
   Explain why the frets crowd together.
7. **Irrationality.** Show 2^(1/12) cannot be a fraction p/q: if it were, then p¹² = 2q¹²,
   making a number both even and odd. What does this say about the keyboard's geometry —
   can any fret ever land exactly on another's position, one octave out?

## 10 · For the teacher

**What to grade:** the frequency chain in Exercise B (computed *before* playing); the
beat-count in Exercise C (data table: predicted vs. counted); the equation-first work in
Exercise F; Checkpoints 3 and 6 in written form.

**Common misconceptions, all correctable on the instrument:**
- *"Higher note = bigger hertz-step."* No: equal steps in note are equal *ratios* in
  frequency. Have the student compute C4→C♯4 (15.6 Hz) and C7→C♯7 (~124.7 Hz) and reconcile
  the two on the keyboard's identical-looking keys.
- *"Cents are a small unit of hertz."* No: cents divide the *ratio*. 25 cents at 110 Hz is
  1.6 Hz; at 1760 Hz it is 25.6 Hz. REDSHIFT makes this felt — the same drag sounds like a
  different amount of bend depending on where the fundamental sits.
- *"BPM is how fast the sound is."* BPM is a counting grid, not a speed of anything.
  Exercise E exists to pin this: change BPM, nothing about the timbre changes — only the
  arithmetic the whole riddim agrees to.

**Lab logistics:** everything in this module runs on the free Community Edition — keybed,
REDSHIFT, arpeggiator, and delay. A watch or phone timer is the only extra equipment.

**Going further.** The guitar is this module's wooden exam: hand a student a fretboard
and Checkpoint 6, and the crowding of the frets becomes the logarithm made visible. And
the steelpan returns from FT-01 with new vocabulary: a tuner stretching a note's partials
is trading in ratios too — every hammer stroke is a renegotiation of the compromise this
module computed.

---

## Cross-references

- **FT-01 · Hearing the Harmonic Series** — why the octave's partials interlock; where the
  pure ratios 3:2 and 5:4 come from.
- **DSP-01 · Envelopes are Functions** (planned) — time stops being a grid and becomes a
  function's domain.
- **Metallurgy Academy** — the BlackBox pairing method this track mirrors.

---

*JUICY Academy — Luminous.Works LLC · Wisconsin · Built in Jamaica*
