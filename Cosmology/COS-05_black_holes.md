# COS-05: The Last Sound
## Cosmology — Lesson 5

**Core concept:** Black hole physics, event horizon, spaghettification, Hawking radiation  
**Duration:** 90 minutes  
**Plugin tie-in:** SINGULARITY — wavetable synthesis on black hole physics  
**Reference object:** M87* — 6.5 billion solar masses, 55 million light-years away

---

### Opening Statement

> *"It took eight telescopes, the entire circumference of the Earth acting as one dish, and five petabytes of data. What they produced was a ring of light around absolute nothing."*
> — Event Horizon Telescope collaboration, April 10, 2019

On April 10, 2019, the Event Horizon Telescope released the first photograph ever taken of a black hole. The target was M87* — the supermassive black hole at the centre of the Messier 87 galaxy, 55 million light-years from Earth, with a mass of 6.5 billion Suns.

The image showed a ring of glowing orange plasma, asymmetric (brighter on the bottom, due to relativistic beaming), surrounding a dark centre. That dark centre is the **shadow** of the event horizon — the point beyond which nothing, not even light, returns.

The ring is not fire. It is gas and dust, heated to millions of degrees by gravitational compression as it spirals in, glowing in radio waves. The black hole itself makes no light. It is visible only by what surrounds its absence.

---

### 1. The Schwarzschild Radius

In 1916 — four weeks after Einstein published General Relativity and while Karl Schwarzschild was deployed on the Russian front in World War I — Schwarzschild derived the exact solution to Einstein's field equations for a spherical, non-rotating mass. He sent the solution to Einstein from the trenches. He died four months later.

The solution contains a singularity at a specific radius, now called the **Schwarzschild radius**:

$$r_s = \frac{2GM}{c^2}$$

Where:
- `G` = gravitational constant (6.674 × 10⁻¹¹ N·m²/kg²)
- `M` = mass of the object
- `c` = speed of light (3 × 10⁸ m/s)

For the Sun (M = 2 × 10³⁰ kg):
$$r_s = \frac{2 \times 6.674 \times 10^{-11} \times 2 \times 10^{30}}{(3 \times 10^8)^2} \approx 2.95 \text{ km}$$

If the entire mass of the Sun were compressed into a sphere 2.95 km in radius, it would become a black hole. The Sun's actual radius is 696,000 km — it is far too diffuse to form a black hole. Stars above approximately 20 solar masses can, if their core collapses past the Schwarzschild radius during a supernova.

For a human (M ≈ 70 kg):
$$r_s \approx 10^{-25} \text{ m}$$

Far smaller than a proton. You are not in danger.

---

### 2. The Event Horizon

The Schwarzschild radius defines the **event horizon** — the boundary of a black hole.

The event horizon is not a physical surface. There is no wall, no membrane you could detect as you crossed it. It is a causal boundary: events inside it cannot send information to events outside it.

At the event horizon, the escape velocity equals the speed of light:

$$v_{esc} = \sqrt{\frac{2GM}{r}} = c \text{ (at } r = r_s\text{)}$$

Beyond this point, the required escape velocity exceeds c. Nothing with mass can travel at c. Light itself, if directed radially outward from exactly the event horizon, makes no progress — it remains stationary in Schwarzschild coordinates, neither escaping nor falling in.

**An external observer** watching someone fall into a black hole would see that person appear to slow down asymptotically as they approach the event horizon — redshifting to longer and longer wavelengths, appearing to freeze at the boundary and fade as the photons are stretched to radio waves, then microwave frequencies, then silence.

**The falling observer** crosses the event horizon without noticing anything unusual at the moment of crossing. The horror is not at the boundary. It is at the centre.

---

### 3. Spaghettification

The gravitational field of a black hole is not uniform. The force on the near side of a body is greater than the force on the far side. This **tidal force** is the same phenomenon that causes ocean tides — the Moon's gravity pulls the near side of the Earth more strongly than the far side.

Near a stellar-mass black hole, tidal forces become extreme at large distances. The differential gravitational acceleration across the length of a human body (~2 metres) near a 10-solar-mass black hole at 1,000 km distance:

$$\Delta g = \frac{2GMl}{r^3}$$

Where `l` = body length, `r` = distance from the singularity.

$$\Delta g = \frac{2 \times 6.674 \times 10^{-11} \times 2 \times 10^{31} \times 2}{(10^6)^3} \approx 5,300 \text{ m/s}^2$$

Approximately 540 times the surface gravity of Earth, applied differentially across a 2-metre body. The result is **spaghettification** — the body is stretched radially and compressed laterally, elongating into a thread of matter as it approaches the singularity.

For a supermassive black hole like M87* (6.5 billion solar masses), the event horizon is so large — approximately 20 billion kilometres in radius — that tidal forces at the event horizon are actually relatively gentle. An astronaut falling into M87* would cross the event horizon without being immediately torn apart. There would be no sensation at the boundary. Only 3–4 hours later (in their own proper time) would the tidal forces become fatal as they approached the singularity.

---

### 4. Hawking Radiation

In 1974, Stephen Hawking derived a result that shocked the physics community: **black holes are not perfectly black.**

Using quantum field theory in curved spacetime, Hawking showed that particle-antiparticle pairs spontaneously created near the event horizon can result in one particle falling in while the other escapes. The escaping particle carries energy away from the black hole. Over cosmological timescales, the black hole loses mass.

The **Hawking temperature** of a black hole:

$$T_H = \frac{\hbar c^3}{8\pi G M k_B}$$

Where `ℏ` = reduced Planck constant, `k_B` = Boltzmann constant.

For a solar-mass black hole: T_H ≈ 6 × 10⁻⁸ K — essentially zero, 40 million times colder than the cosmic microwave background. Undetectable. But for a micro-black hole of 10¹² kg:

$$T_H \approx 10^{11} \text{ K}$$

Hot enough to emit gamma rays. Such a black hole would evaporate completely in approximately 2.6 billion years, ending in a burst of high-energy radiation.

Black holes are not silent. They whisper — and at the end, they scream.

---

### 5. SINGULARITY — The Synthesizer

The SINGULARITY synthesizer is built on the physics of this lesson:

**Wavetable engine:** The wavetable position corresponds to the observer's position relative to the event horizon. Position 0 = distant safe observation. Position 1 = at the singularity. As position increases, the waveform morphs from a recognisable complex wave toward pure, compressed energy — the mathematical equivalent of a signal that has been gravitationally redshifted to extreme wavelengths.

**Spaghettification modulator:** Tidal force = Δg = 2GMl/r³ is the basis of the stretching/compression LFO. As the modulator deepens, harmonic content is stretched radially (pitch drops, fundamental strengthens) and compressed laterally (stereo width narrows toward mono). This is the audio parallel of spaghettification.

**Hawking radiation channel:** A noise floor that is precisely shaped to the Planck blackbody curve at temperature T_H. At low settings, it is inaudible — sub-noise-floor breath. At maximum, it is the final burst as the black hole evaporates. This is not reverb. It is a temperature.

**Event horizon threshold:** A hard compression threshold set at the Schwarzschild radius ratio. Signal that crosses this threshold does not return to its original amplitude — it can approach asymptotically, fade, but cannot cross back. The compressor models the one-way membrane of the event horizon.

---

### 6. The Physics of Sound in a Gravitational Field

Sound cannot travel through a vacuum. A black hole, in the hard vacuum of space, would produce no sound detectable by a human ear.

But:
- In 2003, NASA's Chandra X-ray Observatory detected **pressure waves** in the hot gas surrounding the Perseus galaxy cluster — sound waves propagating through plasma at 57 octaves below middle C. The frequency: approximately 10⁻¹⁵ Hz. One cycle every 10 million years.
- The **gravitational waves** detected by LIGO from merging black holes (September 14, 2015 — the first detection) were directly converted to audio at human hearing range. The "chirp" heard lasted approximately 0.2 seconds. The two black holes had been approaching for over a billion years.

The universe makes sound. We needed 4 km laser interferometers sensitive to 1/1000th the diameter of a proton to hear it.

---

### Discussion Questions

1. The Schwarzschild radius of Earth is approximately 9 mm (the size of a marble). If Earth were compressed to this size, it would become a black hole. Describe the tidal forces you would experience at the event horizon of an Earth-mass black hole. Would you survive crossing the horizon?

2. The 2015 LIGO detection of gravitational waves from merging black holes produced a signal equivalent to three solar masses converted entirely to gravitational wave energy in 0.2 seconds. The peak power output exceeded the combined luminosity of every star in the observable universe for that fraction of a second. Express this power output in watts. (Solar luminosity = 3.828 × 10²⁶ W. Observable universe: ~2 × 10²³ stars.)

3. Hawking radiation has never been directly observed — even the most microscopic natural black holes known have temperatures far too low. Design an experiment or observation scenario that could provide indirect evidence for Hawking radiation. What would you measure?

4. Open SINGULARITY. Set the wavetable position to the minimum (distant observation). Now slowly increase it toward maximum (singularity approach). At what position does the sound feel like it "crosses a threshold"? Is this where you expected the event horizon to be in the parameter range? What changes in the sound at that point?

---

*Standards: NSF Physics Grade 12 (general relativity, gravitational physics), UWI PHYS3401 (astrophysics and cosmology), AP Physics C. Luminous Works LLC / JUICY Academy COS-05.*
