# SP-02: How Does a Digital Limiter Work?
## Signal Physics — Lesson 2 — TEACHER ANSWER KEY

*Do not distribute to students. For teacher use only.*

---

### Exercise 1.1 — Square the Input

**Question:** If input = 0.5, what is input²?

**Answer:** `0.5 × 0.5 = 0.25`

**Common error to watch for:** Students writing `0.5 × 2 = 1.0` — confusing squaring with doubling. Address directly. Squaring means multiplying a number by itself; doubling means multiplying by 2.

**Partial credit:** No partial credit on this question — it is a single arithmetic step.

---

### Exercise 2.1 — RMS Leaky Integrator

**Question:** alpha = 0.9992, rmsLevel = 0.04, input² = 0.01

**Full working:**
```
(0.9992 × 0.04) + (0.0008 × 0.01)
= 0.039968 + 0.000008
= 0.039976
```

**Answer:** `0.039976`

**Common error:** Decimal slip — using `0.004` instead of `0.04` for rmsLevel. This gives:
```
(0.9992 × 0.004) + (0.0008 × 0.01) = 0.0039968 + 0.000008 = 0.0040048
```

**Marking note:** Award full method marks if the student sets up the formula correctly and executes it, even if they misread the input value. The arithmetic procedure is correct; the decimal error is a reading mistake, not a conceptual failure. Note the slip and move on.

---

### Exercise 3.1 — Logarithm

**Question:** `10 × log₁₀(0.001)`

**Full working:**
```
0.001 = 10⁻³
log₁₀(10⁻³) = -3
10 × (-3) = -30 dB
```

**Answer:** `-30 dB`

**Teaching note:** Students should recognise the pattern — every factor of 10 in power = 10 dB change. This is the table in the lesson made algebraic. If students struggle, ask them to locate 0.001 in the table first, then work backwards to the formula.

**Common error:** Students computing `log₁₀(0.001)` as `-0.003` (multiplying rather than taking the log). This indicates a calculator input error — they typed `10 × 0.001` rather than `log(0.001)`. Reteach calculator syntax.

---

### Exercise 4.1 — Threshold Logic

**Question:** inputDB = 2.0, thresholdDB = -1.0, ratio = 100

**Part a:** How many dB over threshold?

`2.0 − (−1.0) = 3.0 dB over threshold`

**Part b:** Gain reduction applied?

`3.0 × (1 − 1/100) = 3.0 × 0.99 = 2.97 dB reduction`

**Teaching note:** With ratio = 100:1, only 0.03 dB of the 3.0 dB excess passes through. This is what "near brick-wall" means in audio engineering. True brick-wall (infinite ratio) would reduce the full 3.0 dB — nothing above the threshold passes at any level. Students interested in the distinction can explore this as extension work.

**Extension question (optional):** *At what ratio value would the limiter become a true brick wall?* Answer: mathematically, ratio → ∞, making `(1 - 1/ratio) → 1`, so `reductionDB = inputDB - thresholdDB` exactly.

---

### Exercise 5.1 — Inverse Logarithm

**Question:** reductionDB = 6.0

**Full working:**
```
gainFactor = 10^(-6/20)
           = 10^(-0.3)
           ≈ 0.5012
```

**Answer:** `≈ 0.5012`

**Teaching note:** The signal is reduced to approximately half its linear amplitude. This is the **"−6 dB = half amplitude"** rule — a foundational audio fact students should memorise. The relationship works because:
- `20 × log₁₀(0.5) = 20 × (−0.301) ≈ −6 dB`

Ask students why the formula here uses `/20` while the earlier conversion used `×10`. Answer: we moved from power domain (where ×10 applies) to amplitude domain (where ×20 applies). Same signal, different measurement perspective.

---

### Discussion Question — Model Answer

**Full marks:**
The "break step" order is a **feed-forward threshold intervention**. When soldiers march in unison, their combined footfall energy approaches the bridge's resonant frequency. Breaking step randomises the timing — scattering the input energy across a range of frequencies, none of which is sufficient to drive the bridge into resonance. The `if (inputDB > thresholdDB)` check performs the same function: it detects when energy has crossed a dangerous level and intervenes before damage occurs. Both systems act on a prediction, not in response to damage after it happens.

**Partial marks:**
Student identifies that both systems prevent damage by intervention, but does not connect the feed-forward timing logic (detecting before the VCA, ordering before the bridge breaks). Give 60% credit.

**Minimum marks:**
Student states "the soldiers stopped marching in step" and "the limiter turns down the volume." Accurate but missing the physics connection. Prompt with: *"In both cases, what is the signal that triggers the intervention, and when does the intervention happen relative to the damaging event?"*

**No marks:**
"Both are about being quiet." No connection to threshold, energy, or intervention timing.

---

### Rubric Summary

| Question | Full Marks | Partial Marks | No Marks |
|---|---|---|---|
| 1.1 | Correct arithmetic (0.25) | — | Wrong operation |
| 2.1 | Correct formula + answer (0.039976) | Correct formula, decimal slip | No formula attempt |
| 3.1 | Correct (-30 dB) | Correct method, calculator error | No log understanding |
| 4.1a | Correct (3.0 dB) | — | — |
| 4.1b | Correct (2.97 dB) | Method correct, arithmetic slip | No threshold logic |
| 5.1 | Correct (≈ 0.5012) | Correct setup, rounding error | No inverse log |
| Discussion | Feed-forward + threshold + energy scattering | Damage prevention only | No physics connection |

---

*Luminous Works LLC / JUICY Academy SP-02. Teacher edition — confidential.*
