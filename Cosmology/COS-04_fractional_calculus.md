# COS-04: The Calculus of Fractured Time
## Cosmology — Lesson 4

**Core concept:** Fractional derivatives, Mittag-Leffler functions, anomalous diffusion  
**Duration:** 90 minutes  
**Plugin tie-in:** PLASMA PL-01 synthesis engine — φ,ψ-fractional operator · Mittag-Leffler envelope  
**Source:** Elzaki & Latrach (2025), *Fractal Fract* 9(12):812

---

### Opening Statement

> *"What would it mean to differentiate a function half a time? I don't know. But perhaps it would lead somewhere useful."*
> — Gottfried Wilhelm Leibniz, letter to Guillaume de l'Hôpital, September 30, 1695

In 1695, Leibniz invented calculus alongside Newton (independently). In the same year, he wrote a letter to his colleague posing a question that seemed like a mathematical joke: what is the ½th derivative of a function?

L'Hôpital replied: "This will be a paradox." Leibniz answered: "From this apparent paradox, one day useful consequences will be drawn."

He was right. Three hundred years later, fractional calculus — calculus where the order of differentiation can be any real number, not just an integer — is used to model:

- Anomalous diffusion in biological tissue
- Viscoelastic materials (matter that behaves as both fluid and solid)
- Memory effects in electrical systems
- The evolution of plasma in oscillating electromagnetic fields
- Envelopes in a synthesizer that cannot be produced by classical ADSR

The PLASMA PL-01 synthesis engine is built on fractional calculus. Every envelope is a Mittag-Leffler function. Every preset is a solution to a specific fractional differential equation. This lesson explains why.

---

### 1. What a Derivative Measures

The standard first derivative measures the instantaneous rate of change of a function:

$$f'(x) = \lim_{h \to 0} \frac{f(x+h) - f(x)}{h}$$

The second derivative measures how the rate of change is itself changing (acceleration):

$$f''(x) = \frac{d^2f}{dx^2}$$

In classical physics:
- Position: x(t)
- Velocity: x'(t) = dx/dt
- Acceleration: x''(t) = d²x/dt²

These are integer-order derivatives: 1st, 2nd, 3rd. Each tells you something physically distinct.

---

### 2. What a Fractional Derivative Means

A fractional derivative of order α (where α is any positive real number) lies between the integer orders.

The **½-order derivative** of a function lies "between" the function itself (0th derivative = the function) and the first derivative (rate of change). It encodes a kind of memory — the fractional derivative at a point depends not just on the local behaviour of the function, but on its entire history.

**Riemann-Liouville fractional integral (order α > 0):**

$$I^\alpha f(t) = \frac{1}{\Gamma(\alpha)} \int_0^t (t - \tau)^{\alpha - 1} f(\tau) \, d\tau$$

Where `Γ(α)` is the Gamma function — the extension of the factorial to non-integer values: Γ(n) = (n-1)! for positive integers.

The convolution kernel `(t − τ)^(α−1)` is what gives fractional calculus its memory. The value at time `t` depends on all past values `f(τ)` for 0 ≤ τ ≤ t, weighted by how recent they are.

When α = 1, this reduces to the ordinary integral. When α = 2, it integrates twice. When α = 0.5, it integrates "half a time" — a weighted history where recent events matter more, but the past is never entirely forgotten.

---

### 3. The Mittag-Leffler Function

In classical calculus, the exponential function e^t is the natural response of first-order systems:

$$\frac{d}{dt}f(t) = -f(t) \implies f(t) = e^{-t}$$

This is the mathematics of standard exponential decay — the basis of classical ADSR envelopes.

In fractional calculus, the analogous function is the **Mittag-Leffler function**:

$$E_{\alpha,\beta}(z) = \sum_{k=0}^{\infty} \frac{z^k}{\Gamma(\alpha k + \beta)}$$

Where:
- `α > 0` controls the "spread" of the function — how stretched the decay is
- `β > 0` controls the shape at t = 0 — the initial behaviour
- When α = 1, β = 1: E₁,₁(z) = eᶻ — the ordinary exponential

The Mittag-Leffler function generalises the exponential. When α < 1, it decays more slowly than a pure exponential — a **power-law tail** that never fully reaches zero in any finite time. This is called **anomalous decay**.

Anomalous decay describes:
- Relaxation in viscoelastic materials
- Memory effects in disordered systems
- Amplitude envelopes that have a "stretched" character — lingering harmonics that decay at different rates for different partials

This last property is what makes the Mittag-Leffler envelope musically interesting.

---

### 4. The PLASMA Synthesis Equation

The PLASMA PL-01 engine implements a solution to the **φ,ψ-fractional differential equation** from Elzaki & Latrach (2025):

$${}^{\phi,\psi}D^{\alpha,\beta} u(t) + \lambda u(t) = f(t)$$

Where:
- `D^{α,β}` is the φ,ψ-fractional derivative operator — a generalisation of the Riemann-Liouville derivative
- `α, β` are the fractional orders (the two envelope parameters in PLASMA)
- `λ` is a damping parameter (the decay knob)
- `u(t)` is the oscillator amplitude over time
- `f(t)` is the input function (the wave shape)

The general solution is a Mittag-Leffler function of the form:

$$u(t) = \sum_{k=0}^{N} c_k \cdot E_{\alpha,\beta}(-\lambda t^\alpha)$$

Each preset in PLASMA corresponds to a specific set of {α, β, λ, N} parameters — a specific fractional differential equation with a specific solution. The 8 base types (SOLAR, AURORA, BALL, NEON, TORCH, ARC, COLD, FUSION) correspond to the 8 solution cases enumerated in the Elzaki-Latrach paper.

---

### 5. Why Classical ADSR Cannot Reproduce This

A standard ADSR envelope consists of four linear or exponential segments:
- Attack: linear ramp 0 → peak
- Decay: exponential fall peak → sustain
- Sustain: constant level
- Release: exponential fall sustain → 0

Each segment is a first-order process (α = 1). The decay is always `e^(-t/τ)` for some time constant τ.

The Mittag-Leffler envelope with α ≠ 1 produces decay curves that **cannot be produced by any combination of ADSR stages**. In particular:
- For α < 1: the initial decay is faster than exponential, but the tail is slower — a "stretched" decay that pulls partials out in time
- For α > 1: the decay is oscillatory before settling — not a ring, but a true sub-oscillation in the amplitude itself

This is why PLASMA sounds different from any synthesizer that uses classical envelopes. The physics of the envelope itself is different.

---

### 6. Anomalous Diffusion in Cosmology

The fractional calculus is not just a mathematical trick for synthesizers. It appears throughout cosmological physics.

**Standard diffusion** (heat spreading through a material) follows Fick's law:
$$\frac{\partial n}{\partial t} = D \frac{\partial^2 n}{\partial x^2}$$

This produces Gaussian spreading — the variance grows linearly with time: σ² ∝ t.

**Anomalous diffusion** — observed in turbulent plasma, cosmic ray propagation, and interstellar magnetic field fluctuations — follows:
$$\frac{\partial^\alpha n}{\partial t^\alpha} = D_\alpha \frac{\partial^2 n}{\partial x^2}$$

With a fractional time derivative. The variance grows as σ² ∝ t^α.

For α < 1: **subdiffusion** — spreading slower than classical (e.g., trapped in disordered media)
For α > 1: **superdiffusion** — spreading faster than classical (e.g., Lévy flights in turbulent plasma)

Cosmic ray propagation through the interstellar medium is subdiffusive. The fractional exponent α ≈ 0.6 has been measured. PLASMA's SOLAR preset, with α ≈ 0.72, is in the same mathematical neighbourhood as the diffusion of high-energy particles through the galactic magnetic field.

---

### Discussion Questions

1. The Gamma function Γ(n) = (n-1)! for positive integers. Calculate Γ(1), Γ(2), Γ(3), Γ(4). Now, Γ(1/2) = √π. Using these values, compute the first four terms of the Mittag-Leffler series E₁/₂,₁(-1). What does the series converge to?

2. In a standard synthesizer, the ADSR release time controls how long a note takes to fade after a key is released. If PLASMA uses a Mittag-Leffler release with α = 0.7, describe qualitatively what this would sound like compared to a standard exponential release. Would it be better or worse for sustained string sounds? For percussive hits?

3. Fractional derivatives have "memory" — the derivative at time t depends on the entire history of the function. Name a physical system outside of mathematics where memory effects are important (hint: viscoelastic materials, biological tissue, financial markets). How does the presence of memory change the behaviour of that system?

4. Open PLASMA PL-01. Select the SOLAR type, preset "SOLAR FLARE." Change the α (phi) parameter from 0.72 to 0.99. Listen to how the decay changes. Now change it to 0.30. What do you hear? How does this correspond to the mathematical difference between a Mittag-Leffler function with α near 1 (approaching exponential) and α far from 1 (highly fractional)?

---

*Standards: NSF Physics Grade 12 (calculus applications), UWI MATH2401 (differential equations), AP Calculus BC. Luminous Works LLC / JUICY Academy COS-04.*
