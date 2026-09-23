# JUICY Academy — DSP-02 · The Mod Matrix

> *One hand on the siren's knob.*

**Program:** JUICY Academy STEM Curriculum
**Track:** FERMANT-CE — the synth that proves its own theorems
**Division:** Luminous.Works LLC
**Audience:** Advanced high school / college
**Prerequisites:** FT-02 (rate and period conversions) and DSP-01 (the envelope as a function). FT-01 recommended.
**Lab:** FERMANT Community Edition — MOD-04 (the three LFOs) and MOD-07 · LANGOLANDS–TUNNELL (the modulation matrix)
**Time:** ~90 minutes

---

## 1 · The siren's hand

At a sound-system session, when the operator reaches for the **dub siren**, everybody knows
what happens next: a wailing sine, and a hand on the rate knob, turning — the wobble slows,
swells, breathes, and the crowd answers it. Nobody calls that mathematics, but it is. The
siren is a **periodic function** — a wobble — and the operator's hand is performing
**rate modulation** on it, live.

The whole of this module lives inside that moment. Synthesists call the slow wobble an
**LFO** — a Low-Frequency Oscillator — and they call the hand's work **modulation**. The
instrument you will learn it on does what the siren operator does by hand, but with the
algebra made visible: a wall of **sources** (the wobble-makers) that can be wired to
**destinations** (the parameters they wobble), each wire carrying a number — the **depth** —
that is nothing more than a scalar in a multiplication.

By the end you will wire a periodic function into a parameter, scale it, reflect it, sum it
with another one, and modulate a function's *frequency* with a second function — which is
the day mathematics and the sound system shake hands.

## 2 · The periodic function, formally

A function *f* is **periodic** if it repeats: f(t + T) = f(t) for every *t*, and the
smallest such T is the **period**. The **rate** is its reciprocal — FT-02's law, back for
an encore:

```
rate = 1 / T        T = 1 / rate
```

The three classic shapes on MOD-04 (the desk's three **torsion LFOs**, named for Barry
Mazur's torsion groups — periodic by construction, the panel says so itself):

- **SIN** — the sinusoid: the smooth wobble, f(t) = sin(2πt/T). The trumpet's vibrato, the
  siren's wail.
- **TRI** — the triangle: rising linearly, falling linearly. Slope is constant; corners are
  sharp. The default shape of the desk's third LFO.
- **SQR** — the square: an instant jump between two levels, dwelling at each. A **pulse
  train** — and the reggae skank, the offbeat chop that carries the riddim, is exactly this
  shape played twice per bar.

And one rule-breaker: **S&H** — *sample & hold*. It ticks periodically like the others, but
at each tick it leaps to a **fresh random value** and holds it until the next tick.
Periodic in time, random in value — a staircase built of dice. (The panel's tooltip
warns *use with caution*. Respect the warning; then, being a scientist, ignore it once and
listen.)

One more distinction, and it is the deepest fact in the module: an LFO is **not a sound**.
It is a *control signal* — a function whose output goes to knobs, not to your ears. At
wobble rates (say 0.5 to 8 Hz — the desk's three defaults) it moves parameters and you
hear motion. Push the same algebra to hundreds of hertz and the wobble crosses into the
audio range and becomes *timbre itself* — but that is the rabbit hole at the end, not the
lesson.

## 3 · The route is scalar multiplication

Here is the entire matrix, stated as one line of algebra:

```
destination += source(t) × depth
```

A **source** is a function of time. A **destination** is a parameter of the sound. A
**route** is the wiring, and its **depth** — the little wheel beside each landed route — is
a **scalar**, ranging from −1 to +1. That is all the wheel is: the multiplier in a
scalar multiplication.

Three consequences fall out of the algebra, and your ear can check every one:

1. **depth = 0 kills the function.** Zero times anything is the zero function — the
   parameter sits still. (The wheel's center is not "quiet"; it is *nothing*.)
2. **Negative depth is reflection.** Multiplying a function by −1 flips its graph through
   the horizontal axis: the part that used to bend the pitch *up* now bends it *down*,
   at exactly the same moments. Same shape, mirrored. When a route ducks instead of
   boosts — the sidechain direction — that is the sign doing its work.
3. **Two routes into one destination are a sum of functions.** The desk adds them,
   literally: two wobbles riding one knob interfere like the two close frequencies of
   FT-02 — sometimes reinforcing, sometimes cancelling.

And one number worth carrying: the **PITCH** destination spans ±12 semitones at full
depth — every 0.10 of depth is 120 cents. A depth of 0.50 is a ±600-cent wobble: a full
tritone each way. You will verify that by ear shortly.

## 4 · Lab I — build the wobble

The desk for this module is two panels: **MOD-04** (the three torsion LFOs, each with rate,
depth and shape) and **MOD-07** — the matrix itself: fourteen source chips above,
thirty-nine destination chips below, and the landed routes between them with their wheels.
(To arm: click a source, then click a destination. To sever: the route's ✕. The PATCH BAY —
the floating wire diagram — mirrors the same routes as colored wires, if you like your
algebra drawn.)

**Exercise A — the basic wobble.** In MOD-04, take LFO 1 (SIN, rate 2). In MOD-07, land
**LFO 1 → PITCH** at depth +0.03 — 1200 × 0.03 = ±36 cents, the width of a real singer's
vibrato. Hold a note: there it is. Now send the same route to **FILTER CUTOFF** instead:
the filter breathes. The source did not change; only the *parameter* it multiplies into.
One function, many knobs.

**Exercise B — rate and period, by the watch.** Set LFO 1's rate to 2 (hertz, as the
slider reports). Compute T = ½ s, then count the wobbles against a watch for ten seconds:
about twenty. Halve the rate; predict before you count. This is FT-02's tempo law wearing
a slower clock — the riddim's grid at 0.5 Hz is one pulse every two seconds, a patient
wobble indeed.

**Exercise C — the scalar sweep.** With LFO 1 → PITCH landed, sweep the wheel slowly from
+1 through 0 to −1, holding a note. Three events, in order: the deep wobble; the *dead
center* where motion ceases (the zero function); then the return of the wobble — same
rhythm, mirrored shape. Say which direction the pitch bends first on each side of zero,
and confirm your prediction from §3.

**Exercise D — the square-wave sketch.** Switch LFO 1 to **SQR**, route it to PITCH at
depth 0.50, slow the rate until the wobble is one per second, and *listen*: not a vibrato
anymore — a **trill**, hopping exactly a tritone apart, ±600 cents each way. Sketch
pitch(t): a square wave. Then compute what depth would make the trill a whole tone
(±200 cents — answer: ±200/1200 = 0.17). You have just *designed* an ornament by algebra —
this is what a synthesized trill has always been.

## 5 · The sum of functions, and chance itself

**Exercise E — interference.** Land **LFO 2 → PITCH** beside the LFO 1 route, LFO 2 at a
different rate (say 2 and 3 hertz). Two periodic functions summed into one destination:
the wobble you hear is neither — it is f + g. At rates 2 and 3, the pattern snaps back
into itself exactly every second: the sum is periodic with period 1 s, because 2 and 3
share a common multiple. Now set the second rate to 1.4 hertz and listen for the long
drift of alignment and misalignment — compute it and you will find the sum *does* come
round, but only every five seconds (2 and 1.4 share the fraction 10/7, and fractions
always come round eventually). Set a ratio that *cannot* be written as a fraction and no
finite answer exists — the sum is **quasiperiodic**, and the drift you hear is two
periods walking past each other forever. (The wave interference of FT-02, at hearing
pace.)

**Exercise F — chance as a function.** Switch LFO 1's shape to **S&H** and route it to
FILTER CUTOFF at a modest depth, then slow the rate until each step is distinct: the
cutoff leaps to a fresh random value and dwells. And beside it, land the **RANDOM** source
— the Ω dice, a fresh white value on *every* evaluation — into FILTER RESO at small depth.
Two kinds of randomness: one sampled-and-held at a period you choose, one continuous and
unrepeatable. Neither is a periodic function; both are functions. Determinism and chance
are now things you can *route*.

## 6 · Lab II — modulating the mathematics itself

**Exercise G — play DSP-01's function.** Land **MOD ENV → ENV RELEASE** at a negative
depth — the self-sidechain from DSP-01, and now you can *say* what it is: one function
(the Shimura envelope, the fast dip) driving a *parameter of another function* (the
amplitude envelope's release time). The matrix does not just add wobbles to knobs; it
plays the coefficients of the piecewise function you learned to write by hand. The
envelope family is fully patchable — ATTACK, DECAY, SUSTAIN, RELEASE — so every number in
your ADSR definition is now a live input.

**Exercise H — the frequency of a frequency.** Land **LFO 1 → LFO 2 RATE** and slow LFO 1
to a wobble. LFO 2's *period* is now itself wobbling — the function's argument is being
driven by another function. This is the siren operator's hand, captured as a route: rate
modulation. Played gently it is the seasick drift; played hard it is the classic siren
sweep. In the literature this family is called *frequency modulation*, and the same
algebra at audio rates builds FM synthesis from three oscillators and a spare afternoon.

**The gate — the trumpet's secret.** The desk knows one more trick worth naming: a
LFO→PITCH route can carry an **onset** — the wobble re-arms on every note and *fades in*
over a few hundred milliseconds of a held note. A short stab stays dead-clean; a held
note blooms into a wobble — the way a real trumpet only starts to sing once the breath
settles. Mathematically it is a product of two functions: the wobble multiplied by a
slow-rising gate. Factory patches carry it (meet a trumpet-flavored preset and listen for
the bloom); you will wire it by hand when you are ready for it.

## 7 · Checkpoint problems

1. An LFO at 0.4 hertz, triangle shape, routed to PITCH at depth 0.30. Give the period in
   seconds, and the wobble's pitch extent in cents.
2. Why does depth exactly 0.00 sound like *no route at all*? Answer with the algebra, not
   the knob.
3. LFO A at 3 hertz and LFO B at 4 hertz both ride FILTER CUTOFF. Is the sum periodic?
   Give its period. What happens to the sum's period if B is retuned to √10 hertz, and
   why is there no correct finite answer?
4. A SQR LFO at 1 hertz rides PITCH. Sketch pitch(t) over two seconds at depth 0.25, and
   label the vertical jump in cents.
5. **Design brief.** A dub siren for 2026: specify LFO shape, rate, destination and depth
   for (a) the idle wail, (b) the operator's hand — name the destination your second
   route lands on, and (c) the one-drop kill: which single route, at what sign, ducks the
   whole desk on every pulse?
6. **Calculus preview.** MOD ENV → ENV RELEASE changes a number that DSP-01 treated as a
   constant. In one sentence: what does it mean, in the language of functions, for a
   *coefficient of a piecewise function* to itself be a function of time?
7. **The 546.** Fourteen sources, thirty-nine destinations: how many possible single
   routes? If you land three routes at once, how many unordered triples? (The desk's own
   manual says an operator will use between two and ten — justify the manual's taste in
   one sentence.)

## 8 · For the teacher

**What to grade:** the period and cents computations (1, 4); the zero-scalar and
reflection explanations in algebra language (2, and Exercise C's writeup); the
sum/periodicity argument (3); the design brief (5) — demand the destination names be
real chips, depths signed.

**Common misconceptions, all correctable on the desk:**
- *"The LFO is a sound."* Route LFO 1 → PITCH at depth 0 with everything else silent:
  there is nothing to hear. The LFO is a control signal — you hear the parameter it moves.
  (This is the module's most important single fact.)
- *"Depth is a volume."* No — a scalar on a normalized function. Depth 0.50 on PITCH is
  a ±600-cent trill, not "half loudness." Exercise D exists to make the scalar concrete.
- *"More routes, richer sound."* Routes into one destination *sum*, and sums interfere —
  Exercise E's misalignment is two routes fighting, not one failing. Mixing is algebra,
  and algebra can cancel.

**Lab logistics:** everything here runs on the free Community Edition — the matrix, the
three torsion LFOs, the PATCH BAY wire view. No presets are required, but after the lab,
the *Wire a mod route* and *808 pump* lessons in the desk's own ACADEMY make good
consolidation, and the Ω RANDOMIZER button is now comprehensible machinery rather than a
mystery: it rolls fresh routes because rolling routes is something this desk does.

**Going further.** Raise an LFO's rate into the audio range while it rides PITCH and hold
a note: the wobble hardens into a new *timbre* — the periodic function has crossed into
the carrier's own frequency range, and you have just built FM synthesis with one route
and one knob. The rabbit hole is officially open.

---

## Cross-references

- **FT-01 · Hearing the Harmonic Series** — the carrier being wobbled.
- **FT-02 · Conversions** — the rate/period law this module leans on.
- **DSP-01 · Envelopes are Functions** — the function whose coefficients this module plays.
- **The desk's ACADEMY** — *Wire a mod route* and *The 808 pump — self-sidechain* (live
  guided lessons on this same surface).

---

*JUICY Academy — Luminous.Works LLC · Wisconsin · Built in Jamaica*
