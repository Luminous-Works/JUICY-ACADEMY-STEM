# JUICY Academy — FERMANT-CE Track

> *The synth that proves its own theorems.*

**Program:** JUICY Academy STEM Curriculum
**Division:** Luminous.Works LLC
**Lab instrument:** FERMANT Community Edition — the free build of the Lumina.Aerospace FFT formant engine
**Audience:** Advanced high school / college
**Philosophy:** Every FERMANT timbre is a theorem in a dependency tree. This track teaches mathematics the way musicians learn intervals: by ear, then by proof.

---

## Overview

Most math curricula ask students to trust the theorem and move on. This track hands them an
instrument where the theorem is the thing they are listening to. FERMANT is a pure additive
synthesizer: every sound it makes is built, one sine wave at a time, from the first 32 terms
of a Fourier series. When a student paints a partial weaker, the mathematics changes and the
sound changes with it — algebra rendered audible, in real time, on a desk that fits in a
browser tab and costs nothing.

The Community Edition is the free build, cut for classrooms. It carries everything this
track needs: the 32-partial array editor, the four factory wave shapes whose tooltips state
their own coefficient laws (aₙ ∝ 1/n — the instrument states its mathematics on its
faceplates), and the COEFFICIENTS preset bank — factory patches named for the series they
paint, ζ(1) through ζ(3) among them.

No music background is required. A keyboard is not required — the keybed plays from the
computer's letter row.

## Module Index

| Module | FERMANT surface | The mathematics |
|---|---|---|
| **FT-01 · Hearing the Harmonic Series** (live) | MOD-01 · Frey Curve | Fourier series · Σ1/nˢ · convergence you can hear |
| **FT-02 · Conversions** (live) | Keybed · REDSHIFT · ARP strip | frequency ↔ ratio ↔ cents · logarithms · tempo arithmetic |
| **DSP-01 · Envelopes are Functions** (live) | MOD-06 · ADSR canvas | piecewise functions · slopes · event-driven pieces · the loop as periodic extension |
| DSP-02 · The Mod Matrix (planned) | MOD-07 · Langlands–Tunnell | periodic functions · scalar multiplication |

## The Preset Bank as Problem Set

The COEFFICIENTS bank is a playable problem set. Each patch paints the first 32 partials
with amplitudes given by a named series:

| Factory patch | Amplitude law | The theorem it plays |
|---|---|---|
| Harmonic Series · Σ1/n | aₙ = 1/n | the divergent series — brightness without end |
| Basel Problem · Σ1/n² | aₙ = 1/n² | Euler's sum = π²/6 ≈ 1.645 — a flutey, convergent tone |
| Apéry's Triple · Σ1/n³ | aₙ = 1/n³ | ζ(3) ≈ 1.202, Apéry's constant — darker still |
| Riemann Rolloff · Σ1/n^1.5 | aₙ = 1/n^1.5 | ζ(1.5) ≈ 2.612 — the boundary case |

Students can rank convergence by ear before they can compute it. That inversion — ears
first, proof second — is the whole method of this track.

## Related Repos

- [`JUICY-ACADEMY-STEM`](https://github.com/Luminous-Works/JUICY-ACADEMY-STEM) — master curriculum
- [`blackbox-suite`](https://github.com/Luminous-Works/blackbox-suite) — scientific instruments
- [`JUICY-Composites-Analysis`](https://github.com/Luminous-Works/JUICY-Composites-Analysis) — composites track

---

*JUICY Academy — Luminous.Works LLC · Wisconsin · Built in Jamaica*
