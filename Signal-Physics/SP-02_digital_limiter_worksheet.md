# SP-02: How Does a Digital Limiter Work?
## Signal Physics — Lesson 2 — Student Worksheet

**Core concepts:** RMS detection, logarithms, threshold logic, VCA limiting
**Subject bridge:** Mathematics × Electronics × Computer Science × Acoustics
**Duration:** 90 minutes
**Prerequisite:** SP-01 (Resonance) or equivalent wave mechanics foundation
**Plugin tie-in:** MAL_IGN FX Block / Sovereign Sentry / ALIEN Meter

---

### The Problem

In SP-01, we saw that resonance without intervention destroys physical structures.

In audio, the same principle applies: an unchecked resonance spike or sudden loud signal can destroy speakers, damage amplifiers, and corrupt a recording. A **limiter** is the failsafe. It watches the signal in real time and reduces the gain before damage occurs.

Here is real C++ code that does exactly this. By the end of this worksheet you will be able to read every line of it.

```cpp
float process(float input) {
    rmsLevel = (alpha * rmsLevel) + ((1.0f - alpha) * (input * input));
    float inputDB = 10.0f * std::log10(rmsLevel + logFloor);
    float reductionDB = 0.0f;
    if (inputDB > thresholdDB) {
        reductionDB = (inputDB - thresholdDB) * (1.0f - (1.0f / ratio));
    }
    float gainFactor = std::pow(10.0f, -reductionDB / 20.0f);
    return input * gainFactor;
}
```

---

### Step 1 — Square the Input (Power Domain)

```cpp
rmsLevel = (alpha * rmsLevel) + ((1.0f - alpha) * (input * input));
```

We square the input sample because we want **power**, not amplitude.

> **Why?** The human ear responds to the *energy* of a sound, not its raw voltage. Energy is proportional to the square of amplitude — the same relationship as kinetic energy: KE = ½mv²

**Exercise 1.1:** If an input sample has a value of `0.5`, what is its squared value?

`input² = ___`

---

### Step 2 — Average It (RMS)

The formula for Root Mean Square:

$$X_{rms} = \sqrt{\frac{1}{n}\sum_{i=1}^{n} x_i^2}$$

In code we approximate this with a **leaky integrator** — a running average that gradually forgets old values:

```cpp
rmsLevel = (alpha * rmsLevel) + ((1.0f - alpha) * (input * input));
```

`alpha = 0.9992` means we keep 99.92% of the old value and add only 0.08% of the new measurement each sample.

> **Why RMS and not peak?** A peak detector reacts to every individual spike. RMS measures *average power* — which is how your ear actually perceives loudness. This is what makes a limiter sound *musical* rather than like a gate slamming shut.

**Exercise 2.1:** Given:
- `alpha = 0.9992`
- `rmsLevel = 0.04`
- `input = 0.1` (so `input² = 0.01`)

Calculate the new `rmsLevel`:

`new rmsLevel = (0.9992 × ___) + (0.0008 × ___) = ___`

---

### Step 3 — Convert to Decibels (Logarithm)

```cpp
float inputDB = 10.0f * std::log10(rmsLevel + logFloor);
```

We use **base-10 logarithm** because the decibel scale is logarithmic — matching how the ear compresses a trillion-to-one range of intensities into something manageable.

| Linear Power | Decibels |
|---|---|
| 1.0 | 0 dB |
| 0.1 | −10 dB |
| 0.01 | −20 dB |
| 0.001 | −30 dB |

> **Notice the pattern:** every time you divide power by 10, you subtract 10 dB. Logarithms turn multiplication into addition — that is their practical superpower.

**Exercise 3.1:** Using a calculator, compute:

`10 × log₁₀(0.001) = ___`

---

### Step 4 — Apply the Threshold (Conditional Logic)

```cpp
float reductionDB = 0.0f;
if (inputDB > thresholdDB) {
    reductionDB = (inputDB - thresholdDB) * (1.0f - (1.0f / ratio));
}
```

- `thresholdDB = -1.0f` — nothing louder than −1 dB passes through unchanged
- `ratio = 100.0f` — for every 100 dB the signal exceeds the threshold, only 1 dB gets through

This `if` statement is the same logic as a fuse in an electrical circuit, or the "break step" order from SP-01.

**Exercise 4.1:** If `inputDB = 2.0` and `thresholdDB = -1.0`:

a) How many dB over threshold is the signal? `___`

b) With `ratio = 100`, how much reduction is applied?
`reductionDB = ___ × (1 - 1/100) = ___`

---

### Step 5 — Convert Back to Linear (Inverse Logarithm)

```cpp
float gainFactor = std::pow(10.0f, -reductionDB / 20.0f);
return input * gainFactor;
```

We calculated gain reduction in decibels. Now we convert back to a linear multiplier to apply to the actual audio sample.

`10^(dB/20)` is the inverse of `20×log₁₀(linear)`. We opened with a logarithm; we close with its inverse. The mathematics forms a complete loop.

**Exercise 5.1:** If `reductionDB = 6.0`:

`gainFactor = 10^(−6/20) = 10^(−0.3) = ___`

*(Use a calculator. Round to 4 decimal places.)*

---

### The Five-Step Signal Flow

```
AUDIO IN → [²] SQUARE → [Σ/n] AVERAGE → [log₁₀] DECIBELS
                                                      ↓
AUDIO OUT ← [×] MULTIPLY ← [10^x] LINEAR ← [>?] THRESHOLD
```

Every professional limiter — hardware or software — follows this exact path.
The THAT Corp 4320 chip does it in analog electronics.
This C++ code does it in software.
The mathematics is identical.

---

### Discussion Question

The Broughton Bridge collapsed in 1831 because nobody limited the resonance. The British Army now orders soldiers to **break step** when crossing a bridge.

*How is that order — "break step" — performing the same function as the threshold check in Step 4?*

Write 3–5 sentences connecting the two systems.

---

*Standards: NSF Mathematics Grade 9 (logarithms, algebra), Physics Grade 10 (wave mechanics, resonance), Computer Science Grade 9 (conditional logic, data types). Luminous Works LLC / JUICY Academy SP-02.*
