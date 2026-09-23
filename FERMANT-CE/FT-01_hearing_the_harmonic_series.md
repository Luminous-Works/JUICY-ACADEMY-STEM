# JUICY Academy — FT-01 · Hearing the Harmonic Series

> *Every sound is a sum. Learn to hear the terms.*

**Program:** JUICY Academy STEM Curriculum
**Track:** FERMANT-CE — the synth that proves its own theorems
**Division:** Luminous.Works LLC
**Audience:** Advanced high school / college
**Prerequisites:** Fractions and exponents. No music theory required — the instrument teaches what it needs.
**Lab:** FERMANT Community Edition — MOD-01 · FREY CURVE (the global partial array)
**Time:** ~90 minutes

---

## 1 · The abeng's question

Stand anywhere in the Cockpit Country and you may hear it: the abeng, the Maroon horn cut
from conch or cow horn, one note blown so it carries across a whole valley. The British
could not silence it in three hundred years; it still calls the Asafu and the council to
order in Accompong and Moore Town today.

Now ask the physicist's question: *what is that sound?* A "single note," we say. But no
instrument on earth plays a single frequency. Hold any sustained tone — an abeng, a guitar
string, your own voice — and inside that one note hides a whole family of frequencies,
stacked in a precise order. That order is called **the harmonic series**, and it is the
deepest law in all of music and acoustics. Every instrument obeys it; every timbre is a
particular way of weighting it.

This module teaches you to hear the family, one member at a time — and then to prove, by
hand, the theorem that builds a violin's buzz out of nothing but sine waves.

## 2 · One string, many shapes

Why should one note contain many frequencies? Because a vibrating string (or air column,
or conch cavity) cannot move in just any shape. Pin a string at both ends and pluck it:
the ends cannot move, so only waves that *fit* the string can exist on it.

A wave must have a whole number of humps between the two fixed ends. The longest that fits
has half a wavelength along the string — one hump:

```
λ₁ = 2L        f₁ = v/2L
λ₂ = 2L/2      f₂ = 2·f₁
λ₃ = 2L/3      f₃ = 3·f₁
λₙ = 2L/n      fₙ = n·f₁
```

where *v* is the wave speed and *L* the length. The allowed frequencies are the whole
multiples of one fundamental: **f₁, 2f₁, 3f₁, 4f₁, …** No fractions, no exceptions. The
same arithmetic that fits standing waves on a string fits them in the air column of an
abeng — and in the bore of every trumpet and the body of every steelpan note.

**The algebra, once:** if the third shape fits three half-wavelengths into length *L*,
then λ₃ = 2L/3, and since frequency is speed over wavelength, f₃ = v/(2L/3) = 3v/2L = 3f₁.
Do the same for n = 4, 5, 6 and write the general law fₙ = n·f₁. That is the entire
skeleton of Western music, derived in three lines.

But frequencies alone are not sound. Each member of the family also carries a **weight** —
an amplitude. The shape of the whole family — who is loud, who is faint — is what makes an
abeng sound like an abeng and a flute sound like a flute. The weights are the *timbre*.
And in 1807, Joseph Fourier stood in front of the Paris Academy and made the claim that
scandalized Lagrange: **any** repeating shape can be written as a sum of these sine family
members, with the right weights. Timbre, he said, is a series of numbers.

## 3 · The theorem you can hear

Take the brightest, buzziest wave in the synthesist's kit: the sawtooth. Fourier's series
for it is

```
y(t) = (2/π) · Σ  sin(n·ω·t) / n      (n = 1, 2, 3, …)
```

Read the weights off the formula: harmonic *n* gets amplitude **1/n**. The fundamental at
full strength, the second harmonic at half, the third at a third, the fourth at a quarter.
A sawtooth is nothing but the reciprocals 1, ½, ⅓, ¼, ⅕ … dressed in sine waves.

And notice what the weights sum toward. Σ 1/n — *the harmonic series itself* — does not
converge. Its tail never dies: that unending tail of ever-fainter partials is exactly the
aggressive brightness that makes a sawtooth cut through a mix. The mathematics and the
sensation are the same fact.

## 4 · The lab — paint the theorem

Boot the FERMANT Community Edition, switch the engine on, and find **MOD-01 · FREY CURVE**
— the instrument's global partial array. You are looking at 32 bars, labelled H1 through
H32: harmonic 1 through harmonic 32 of whatever note you play. Each bar's height is that
harmonic's amplitude; drag a bar to change it, and the readout gives you its exact value
to three decimals. The desk plays from the computer's letter keys — **Z S X D C V** and
their row are the white keys. One hand holds a note; the other hand paints.

> FERMANT states its own laws on its faceplates. Hover the shape chips under the curve and
> read the tooltips: *Sawtooth — aₙ ∝ 1/n. Square — odd partials only, 1/n. Triangle — odd
> partials, 1/n².* The instrument is telling you its own coefficient table before you
> prove it. Good. Now prove it.

**Exercise A — read the law.** Click **SAW**. Read off H1, H2, H3, H4, H5. Compute the
ratios H2/H1, H3/H1, H4/H1, H5/H1. State the law you observe as a formula.

**Exercise B — hand-build the saw.** Reset the curve (double-click), then paint the
reciprocals by hand: H1 = 1.00, H2 = 0.50, H3 = 0.33, H4 = 0.25, H5 = 0.20, H6 = 0.17 …
as far down the row as your patience allows, the rest near zero. Hold a note and listen.
You did not imitate a sawtooth — you *derived* it, and your ears just confirmed the
derivation. Play your hand-built saw next to the factory SAW: the factory has 32 terms,
you have six. The difference you hear **is** the tail of the series.

**Exercise C — hear convergence.** Keep your hand-painted saw. Now erase from the top:
drag H8–H32 to zero and listen. Then H5 upward. Then everything above H3. The tone gets
rounder, darker, purer — each erasure removes another piece of the infinite tail. You are
hearing partial sums of a divergent series approach their limit shape. Nobody who has done
this needs to be told what "the tail matters" means.

**Exercise D — the square's secret.** Load **SQR** and read the bars: H2 = 0, H4 = 0, H6 =
0. The square wave keeps only the *odd* harmonics — still weighted 1/n. Why? Sketch: a
square wave repeats upside-down after half a period (flip the sign, shift by T/2, and it
looks the same). Any even-harmonic sine term would come back with the *wrong* sign and
cancel itself. Symmetry killed the evens. This is a real proof, and it is three lines
long — write it out.

## 5 · The ζ corner — convergence you can rank by ear

Now the beautiful part. Open the preset browser (the caret by the preset name, or **[** and
**]** with the cursor over the name), find the **COEFFICIENTS** bank, and load these four
factory patches in order. Each one paints its partials with a named series:

| Patch | Amplitude law | The series |
|---|---|---|
| Harmonic Series · Σ1/n | aₙ = 1/n | ζ(1) — **diverges** |
| Riemann Rolloff · Σ1/n^1.5 | aₙ = 1/n^1.5 | ζ(1.5) ≈ 2.612 — barely converges |
| Basel Problem · Σ1/n² | aₙ = 1/n² | ζ(2) = **π²/6** ≈ 1.645 |
| Apéry's Triple · Σ1/n³ | aₙ = 1/n³ | ζ(3) ≈ 1.202 — Apéry's constant |

Listen across the four, in order, on the same held note. ζ(1) is aggressive, edgy, bright.
ζ(1.5) is still noticeably buzzy. ζ(2) turns suddenly hollow and flute-like. ζ(3) is dark,
soft, nearly a pure tone. **You just ranked four infinite series by their rate of
convergence — using only your ears.** The faster the tail dies, the fewer overtones carry
energy, the darker the timbre. Analysis, the study of infinite sums, has become a
listening exercise.

**Exercise E — Euler as a timbre.** The Basel problem — named for the city of the Bernoullis,
unsolved for eighty years until Euler announced in 1735 that

```
Σ 1/n² = 1 + 1/4 + 1/9 + 1/16 + … = π²/6
```

Load *Basel Problem · Σ1/n²* and look at the bars: partial *n* sits at exactly 1/n². The
terms of Euler's series are standing there in the window, one per bar, playing. Hold a
note. You are listening to π²/6.

**Exercise F — paint Basel yourself.** Reset, then hand-paint H1 = 1.00, H2 = 0.25, H3 =
0.11, H4 = 0.0625, H5 = 0.04 … (1, ¼, ⅑, 1/16, 1/25 …). Compare with the factory patch.
Then, from your painted Basel, zero the even bars (H2, H4, H6 …) and boost nothing else.
Odd-only 1/n² is the **triangle wave** — the smoothest, roundest tone in the family. One
erasure, and Euler's series became the coefficient table of the triangle.

> *Footnote for the precise:* the true triangle wave alternates the *signs* of its odd
> terms (+, −, +, − …), which this desk paints as magnitudes. The signs are a phase detail
> — the amplitude law, odd and 1/n², is what your ear tracks. FERMANT keeps the display
> honest by painting magnitudes; your ears are not lying to you.

## 6 · Where the music comes from

Play a low note and look at the frequencies, not just the amplitudes. The harmonic series
is also a *musical* structure: 2f₁ is an octave above the fundamental, 3f₁ lands a perfect
fifth above *that*, 4f₁ another octave, 5f₁ a major third. Every chord Western music is
built on is a snapshot of this one arithmetic sequence. When a nyabinghi drummer tunes two
drums a fifth apart, they are placing the 2nd and 3rd members of one series in the air.

The algebra of turning frequencies into intervals — ratios, cents, logarithms — is the
whole subject of the next module, **FT-02 · Conversions**.

## 7 · Checkpoint problems

1. Compute 1/n for n = 1 … 8 as decimals, then as percentages. Which factory shape matches
   your table, and which bars would sit at zero in that shape?
2. **Oresme's proof, in your own words.** Group the harmonic series as
   1 + ½ + (⅓ + ¼) + (⅕ + … + ⅛) + (⅑ + … + 1/16) + … — each bracket holding twice as many
   terms as the one before. Show that every bracketed group sums to at least ½, and explain
   why this proves Σ1/n has no finite sum. Then explain
   what that fact *sounds like* on MOD-01.
3. Without computing anything: which is brighter, ζ(1.5) or ζ(3)? Defend your answer in
   one sentence using the word *tail*.
4. A triangle wave has odd partials weighted 1/n². If H1 = 1.00, compute H3 and H5. Then
   load *Apéry's Triple · Σ1/n³* and say in one sentence why it sounds *darker* than the
   triangle even though the triangle's law drops faster per term. (Hint: evens.)
5. The square wave keeps odd 1/n; the saw keeps all 1/n. Compute the total weight of the
   first four partials in each (add your fractions). Which wave put more energy in its
   first four terms — and is that what you heard in Exercise D?

## 8 · For the teacher

**What to grade:** the ratio table from Exercise A (they should find ~1/n unprompted); the
hand-painted saw from Exercise B (ear-check in a walk-around); the symmetry argument from
Exercise D in written form; the Oresme grouping argument from Problem 2; the one-sentence
convergence ranking from Problem 3.

**Common misconceptions, all audible and thus correctable on the spot:**
- *Amplitude and frequency confused.* Harmonic *n* has frequency n·f₁ but amplitude ~1/n.
  Have the student zero H1 on a saw and notice the pitch did not change — the "location" of
  the sound moved, not its note. (This is worth a full discussion; it previews formants.)
- *"The fundamental is the note, the rest is decoration."* Load *Basel Problem* and mute
  H1: a tone remains, an octave up and ghostly. The note is the whole series.
- *"Convergence is about the first terms."* It is about the tail — which is precisely what
  the ear hears as brightness. Exercise C exists to make this permanent.

**Lab logistics:** FERMANT CE runs on any classroom machine with a browser; the keybed
plays from the letter row, so no MIDI controllers are required, though they enrich the
later modules. The COEFFICIENTS bank ships in the Community Edition, so every patch this
module references is available in the free build.

**Going further — the steelpan breaks the rule.** Trinidad and Tobago's national
instrument is the Caribbean's great acoustic invention: a note hammered into a steel drum
carries partials that are deliberately pulled *away* from the pure harmonic series to make
one drum surface carry whole chords. Fourier's law is the rule; the steelpan is the region's
most famous, most beautiful violation of it. A student who can explain *why* the steelpan
sounds like no other instrument — using the words *partial* and *inharmonic* correctly —
has finished this module.

---

## Cross-references

- **ECO-02 · Cockpit Country** — the abeng's home, and the landscape that carried it.
- **Metallurgy Academy** — the BlackBox pairing method this track mirrors.
- **FT-02 · Conversions** (planned) — frequency to ratio to cents, the algebra of the
  equal-tempered keyboard.

---

*JUICY Academy — Luminous.Works LLC · Wisconsin · Built in Jamaica*
