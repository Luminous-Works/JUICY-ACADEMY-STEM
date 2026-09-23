# JUICY Academy — DSP-01 · Envelopes are Functions

> *Loudness, plotted against time.*

**Program:** JUICY Academy STEM Curriculum
**Track:** FERMANT-CE — the synth that proves its own theorems
**Division:** Luminous.Works LLC
**Audience:** Advanced high school / college
**Prerequisites:** FT-01 (the harmonic series). Functions and their notation; interval notation helps but can be learned here.
**Lab:** FERMANT Community Edition — MOD-06 · the amplitude envelope (the ADSR desk)
**Time:** ~90 minutes

---

## 1 · The funde and the repeater

Sit with the nyabinghi drums. The **funde** holds the heartbeat — the steady, patient
boom-boom that carries the ground of the music, on and on, level as a table. The
**akete** — the repeater — talks over it: quick strikes, rolls, cuts, accents that leap
up and are gone.

Two drums, and between them every question this module asks. When the funde plays, what
is happening to the *loudness*? It rises when the hand lands, then holds — for as long
as the drummer keeps the pulse. When the repeater lands a slap, the loudness leaps and
dies in a blink. Loudness is not a number; it is a **story with a beginning, a middle,
and an end** — and a story that unfolds against the clock is exactly what mathematics
calls a function:

```
level(t)   — the loudness of the sound at time t.
```

The drummer writes this function by hand and muscle. The synthesist writes it by drawing
it. This module teaches you to read it, write it in proper notation, and edit it live on
an instrument that plays back the mathematics the instant you touch it.

One distinction before we start, and it matters for the whole track: FT-01 studied the
**waveform** — the shape vibrating hundreds of times per *second*, the thing that makes
an abeng sound like an abeng. This module studies the **envelope** — the volume knob's
path over *seconds*, the thing that makes a funde sound like a funde and a slap sound
like a slap. Waveform is timbre's function. Envelope is loudness's function. Every real
sound is one riding on the other.

## 2 · The envelope is a piecewise function

Here is the whole idea of the ADSR envelope — the shape every keyboard and drum machine
in the world is named for — written as mathematics. Four parameters: attack time *a*,
decay time *d*, sustain level *s*, release time *r*. Then:

```
                    ⎧ rises from 0 to 1        for 0 ≤ t ≤ a          (attack)
                    ⎨ falls from 1 to s        for a < t ≤ a + d       (decay)
  level(t) =        ⎨ holds at s               while the key is held  (sustain)
                    ⎨
                    ⎩ falls from s to 0        after the key is lifted, over r seconds
                                                                (release)
```

Read what the notation is saying. This is **one function built from pieces**, each piece
owning its own stretch of the time axis — a *piecewise* function. The pieces meet at
joints, and the whole shape is pinned down by just four numbers. Change *a* and you
stretch the first piece's domain. Change *s* and you slide the third piece's range.
The four sliders on the instrument are the four parameters of the definition — the desk
is the function's control panel, literally.

And notice the strangest piece: **the release does not begin at a time.** It begins at
an *event* — your finger lifting off the key. Hold the note for one second, the release
starts at t = 1. Hold it for ten, it starts at t = 10. The envelope is a function that
listens. (We will meet event-driven mathematics again in this track — a scheduled
arpeggiator is nothing but a list of such events on a clock.)

## 3 · The lab — read it, write it, drag it

Find **MOD-06** — the envelope canvas with its curve and four anchor handles. The
letter-row keybed plays underneath it; one hand holds a note while the other edits the
mathematics. Everything you touch redraws the function and re-voices it, instantly.

**Exercise A — read the graph.** Double-click the canvas: the desk returns to its
defaults — attack 120 ms, decay 350 ms, sustain 68%, release 600 ms. Do what a
mathematician does first: read the pieces. Write the four intervals — [0, 0.120],
(0.120, 0.470], the held region, and the release — and label each with its piece's
behavior. You have just written the piecewise definition of the sound in front of you.

**Exercise B — the anchors are the parameters.** The canvas shows three circle anchors
and one triangle. Drag the **A anchor** right and left: you are editing the domain of
the attack piece, and the slider below reports it in milliseconds. Drag the
**D-S corner**: one point, two parameters — sideways edits the decay piece's domain,
vertically edits the sustain piece's *range*. (One handle carrying two coordinates — a
junction of the graph that moves in both axes. Find it on your sketch from Exercise A.)
Drag the **triangle** right: the release piece appears and stretches. Every drag is a
live edit of the function's definition.

**Exercise C — slopes.** With attack at its default, the piece rises 100 percentage
points in 120 ms — an average slope of about 0.83 points per millisecond. Compute the
average slope of the attack when you stretch it to 600 ms, and of the release piece
(68 points falling over 600 ms). Then listen to each version while you hold a note.
Slope is not decoration: it is the *speed of the swell* your ear reports.

**Exercise D — the one-shot.** Drag the D-S corner all the way down: sustain = 0, and
the desk badges the curve **ONE-SHOT**. The function no longer has a held piece — the
note strikes and terminates at the end of the decay, a function with a hard **domain
restriction**. This is the funde-versus-repeater distinction rendered in notation: the
funde's level function is defined for as long as the drummer plays; the slap is a
one-shot, full stop. Now design two one-shots on the desk and defend your parameters:
a conga slap (what attack? what decay?) and a bass-drum thud. Swap desks with a
partner and play each other's designs blind — can they tell which is which?

**Exercise E — the curve families.** The same pieces, different *shapes*: the CURVE
chips switch the interpolating family of every piece at once.

- **LIN** — straight segments: constant slope. The pure textbook piece.
- **EXPONENTIAL** — nature's curve: the dive that starts fast and settles long. This is
  the cooling-coffee curve, the ringing-drum curve, radioactive decay.
- **LOGARITHMIC** — the opposite character: fast start, long settle.
- **HOLD** — the extreme case: each piece stays at its starting level and *jumps* at
  the end. This is the **step function**, the special piecewise function with a
  discontinuity at every joint.

Switch through all four on a held note and watch the curve while it sounds. Same four
parameters, four different functions — the *family* is a fifth parameter, and your ear
hears it as physical character: mechanical, natural, or simply electronic.

**Exercise F — the loop, or how to build a periodic function early.** Engage the
**LOOP IN** chip (first click arms it; further clicks nudge the marker) and LOOP OUT
likewise. The desk shades the marked stretch of the attack–decay span — and while you
hold the note, that stretch **repeats**. You have taken a piecewise function and
performed a *periodic extension* of one of its pieces: the marked segment becomes the
one period of a new, repeating function. On current builds the little beads at the
region's edges are directly draggable — pull them closer and hear the period shorten.
The mathematics of repeating functions is the whole subject of the next module,
**DSP-02 · The Mod Matrix**. You have just built its first specimen by hand.

## 4 · The release — the shape of letting go

Return the release to zero (drag the triangle home, all the way to the sustain corner).
The triangle turns to a ghost — a hollow dashed shape with a **+** inside — and the
dashed path where the release *would* go appears past it. The desk is showing you an
undefined piece: the release exists in potential, not yet in the function. Drag it
right and the triangle **lights up** and glows: the piece is defined, the function
grows its fourth limb.

Now do this with your ears. Hold a note for two seconds and let go. Count how long the
sound keeps dying: that audible tail is the release piece executing, the falling part
of the function running exactly as drawn. Put the release at 600 ms, then 3 s: your
muscles are learning the parameter now. Musicians call this *letting a note go*.
Mathematicians call it *evaluating the final piece*. The drummer has always known both.

## 5 · Checkpoint problems

1. Write the default envelope (a = 120 ms, d = 350 ms, s = 68%, r = 600 ms) as a full
   piecewise definition, with each piece's interval and its start/end values.
2. Compute the average slope of each piece of the default envelope: attack, decay,
   release. Rank the pieces by steepness. Which piece is the gentlest, and does the
   default patch sound gentle there?
3. **The gate.** A note is held indefinitely. Which pieces of the function ever run?
   What is level(t) for large t? (This is why the sustain is a *level*, never a
   duration — the piece is a constant function, defined until the event.)
4. **The HOLD attack.** With the HOLD curve selected, describe level(t) on the attack
   interval [0, a] in words, then sketch it. Where does the discontinuity sit?
5. **Design brief.** A reggae organ stab and a pad wash use the same oscillator. Give
   plausible ADSR parameters for each (four numbers and a curve family), and write one
   sentence justifying each number.
6. **Loop period.** With a = 120 ms and d = 350 ms, the loop markers sit at 15% and 45%
   of the attack–decay span. How long is one loop period in milliseconds? Approximately
   how many repeats per second does the held note produce?
7. **The two functions.** In one sentence each: what did FT-01 study, and what does this
   module study — and which one does the abeng's *tone* belong to, versus its *swell*?

## 6 · For the teacher

**What to grade:** the piecewise writeup from Exercise A / Checkpoint 1 (exact intervals
in correct notation); the slope computations; the one-shot design brief with
justifications; Checkpoint 3 in written form — the event-driven release is the concept
most worth a paragraph.

**Common misconceptions, all correctable on the instrument:**
- *"The envelope is the sound."* No — it is the volume-control function riding the
  waveform. Zero the attack and the sound is still there, just switched on
  instantaneously. The waveform (FT-01) is the clay; the envelope is the hand.
- *"Sustain is how long the note lasts."* No — it is the level held while the key is
  down. The *duration* belongs to the player. Have the student hold one sustained
  patch for 2 s and for 10 s and watch which parts of the curve re-run.
- *"Release happens at the end of the sound."* It happens at note-off, whenever that
  is. The release piece's domain *begins at an event*, not a clock time — worth
  belaboring, because event-driven definitions return in every scheduler and sequencer
  they will ever meet.

**Lab logistics:** everything in this module runs on the free Community Edition. Newer
builds add two conveniences used above: the loop beads are directly draggable, and
**SHIFT + mouse-wheel** zooms the envelope's time axis (plain wheel still scrolls the
page — the zoom waits for the shift key on purpose). Double-clicking the canvas always
returns the desk to the default four numbers.

**Going further.** Every instrument the students know is an envelope catalogue: have
them classify the school's percussion by attack steepness and decay time, then prove
their classification by rebuilding each sound's envelope on the desk. And the one-shot
badge is a doorway: a function that *terminates* leads naturally to the question of
what a sampler does when it refuses to terminate — the loop — which is periodicity,
which is DSP-02.

---

## Cross-references

- **FT-01 · Hearing the Harmonic Series** — the waveform underneath the volume.
- **FT-02 · Conversions** — the time units (ms, BPM) this module's axis lives in.
- **DSP-02 · The Mod Matrix** (planned) — periodic functions arrive in force: LFOs,
  the loop's big sibling.

---

*JUICY Academy — Luminous.Works LLC · Wisconsin · Built in Jamaica*
