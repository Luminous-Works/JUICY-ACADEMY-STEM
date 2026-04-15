# Addendum SP-A: Curriculum Extension Products
## Signal Physics Module — Product Development Ideas

*Generated from the context of the SP-02 Digital Limiter module. These are proposed products that extend or apply the curriculum concepts in adjacent markets.*

---

### 1. Applied Physics / Engineering Simulation Software

A desktop or web application focused on visualising real-world threshold interventions. Expands the "break step" analogy from SP-01 by allowing students to design and test feed-forward logic systems for non-audio domains:

- **Bridge stability** — set the resonant frequency of a virtual bridge, vary soldier cadence, observe amplitude growth and the point of structural failure
- **Earthquake dampening** — model base isolation systems as threshold interventions
- **Industrial safety cut-off switches** — design a VCA-equivalent for mechanical systems

**Curriculum fit:** Bridges SP-01 (physical resonance) and SP-02 (threshold logic) into engineering design thinking. Students who can reason about a digital limiter can reason about any feed-forward safety system.

**Diagram requirement:** The simulation UI itself acts as the diagram. Priority deliverable.

---

### 2. "Audio Fundamentals Lab" Kit (Hardware / Software Bundle)

A teaching kit combining a low-cost microcontroller (Arduino or Raspberry Pi) with custom JUICY Academy software. Students physically build a simple digital limiter or compressor circuit and program the five mathematical steps:

1. Square the input (power domain)
2. Compute the running RMS average
3. Convert to decibels (logarithm)
4. Apply threshold conditional logic
5. Convert back to linear gain (inverse log)

Students hear the gain reduction applied in real time to a live audio input signal.

**Why this works:** The mathematics stops being abstract the moment the student hears their own voice being limited by code they wrote. The "aha" moment is physical.

**Potential partner:** FAMU Engineering Department (existing JUICY relationship). This is a natural lab assignment for a Grade 10 physics or CS class.

---

### 3. Advanced JUICY Academy Module: "Digital Filter Design" (SP-03)

A follow-up module to SP-02, covering essential DSP concepts:

- **FIR Filters** (Finite Impulse Response) — the output depends only on current and past inputs; mathematically predictable; used in EKG-EQ's linear phase mode
- **IIR Filters** (Infinite Impulse Response) — feedback in the filter design; more efficient; used in most analog-modelled EQs including the Keeley/4320 architecture
- **Complex numbers in audio** — why the z-transform requires imaginary numbers; the unit circle as a frequency map
- **The bilinear transform** — how analog filter designs (like the 4320) are converted to digital implementations

**Teaching notes for instructors:**
- Most student errors in DSP involve data type confusion (float vs. double, fixed-point vs. floating-point). Address early.
- Complex arithmetic in audio is often students' first meaningful encounter with imaginary numbers as a tool rather than an abstraction. Frame it as: *"Complex numbers are how we describe rotation. Frequency is rotation. Therefore complex numbers are the language of audio."*

**Plugin tie-in:** EKG-EQ (bandpass and notch filter mathematics), Imperial Six (convolution as FIR filtering at room scale).

---

### 4. Interactive dB and Logarithm Trainer

A dedicated, gamified educational tool for mastering decibel conversions and logarithms — the foundational mathematics of SP-02 and every subsequent Signal Physics module.

**Core drills:**
- Convert linear amplitude to dB and back (the half-amplitude rule: −6 dB = 0.5× amplitude)
- Distinguish power-based conversion (×10 rule) from amplitude-based (×20 rule)
- Identify common student errors: confusing squaring with doubling, misreading decimal places, calculator input syntax

**Game mechanic:** Students are audio engineers watching a signal approach a threshold in real time. They must calculate the required gain reduction before the clip indicator fires. Speed and accuracy both score.

**Integration:** Could live inside the ALIEN Meter as an educational mode — the meter becomes the game board. The five ALIEN bands light in sequence as the student completes each level of the logarithm curriculum.

**Why the ALIEN Meter:** The letters A-L-I-E-N map to the five frequency bands a student needs to understand (Sub, Low-mid, Mid, Hi-mid, Air). Making the meter interactive turns a passive monitoring tool into an active learning device. This is the JUICY Academy philosophy applied to hardware UI.

---

*Luminous Works LLC / JUICY Academy — Addendum SP-A. For internal product development use.*
