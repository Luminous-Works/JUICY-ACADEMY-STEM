# COS-02: Everything Is Moving Away
## Cosmology — Lesson 2

**Core concept:** Doppler effect, cosmological redshift, gravitational redshift, Keplerian orbits  
**Duration:** 90 minutes  
**Plugin tie-in:** REDSHIFT surface — PARALLAX · SINGULARITY  
**Anchor:** z = Δλ/λ₀ = v/c (classical) · z = GM/rc² (gravitational)

---

### Opening Statement

> *"Every distant galaxy shows a redshift in its spectral lines. The further the galaxy, the greater the redshift. The universe is not static. It is expanding."*
> — Edwin Hubble, 1929

In 1929, Edwin Hubble published a paper that changed our understanding of reality. By measuring the spectra of distant galaxies, he found that their light was systematically shifted toward the red end of the spectrum — and that the more distant the galaxy, the larger the shift.

The interpretation was inescapable: everything in the universe is moving away from everything else. Not because there is some centre that galaxies are fleeing from, but because spacetime itself is expanding. The distance between any two points in the universe is growing.

We heard this before Hubble proved it. A police siren that drops in pitch as it passes you. A train whistle that falls as the locomotive recedes down the track. The Doppler effect. The universe, at every scale, is playing the same note — and it is moving away from us.

---

### 1. The Classical Doppler Effect

When a wave source moves relative to an observer, the observed frequency differs from the emitted frequency.

**For a receding source:**
$$f_{obs} = f_{source} \cdot \frac{v_{wave}}{v_{wave} + v_{source}}$$

**For an approaching source:**
$$f_{obs} = f_{source} \cdot \frac{v_{wave}}{v_{wave} - v_{source}}$$

Where:
- `f_obs` = frequency observed
- `f_source` = frequency emitted
- `v_wave` = speed of wave in the medium (343 m/s for sound in air at 20°C)
- `v_source` = speed of the source

A fire engine emitting a 440 Hz siren moving toward you at 30 m/s:

$$f_{obs} = 440 \cdot \frac{343}{343 - 30} = 440 \cdot 1.096 = 482 \text{ Hz}$$

As it passes and moves away:

$$f_{obs} = 440 \cdot \frac{343}{343 + 30} = 440 \cdot 0.919 = 404 \text{ Hz}$$

A drop of **78 Hz** — nearly a minor third — from approach to recession. The pitch change you hear at the moment of passing is that entire 78 Hz shift occurring continuously as the velocity vector rotates from toward to away.

---

### 2. Cosmological Redshift

For light (electromagnetic radiation), the classical Doppler formula does not fully apply at cosmological velocities. The relativistic version and the expansion of spacetime itself both contribute.

The **redshift parameter z** is defined as:

$$z = \frac{\lambda_{obs} - \lambda_{em}}{\lambda_{em}} = \frac{\Delta\lambda}{\lambda_0}$$

For small velocities (v << c), this simplifies to:

$$z \approx \frac{v}{c}$$

For a galaxy with a recession velocity of 10,000 km/s (3.3% of the speed of light), the redshift is:

$$z \approx \frac{10,000}{300,000} = 0.033$$

A hydrogen spectral line normally at 656 nm (red) would be observed at:

$$\lambda_{obs} = 656 \cdot (1 + 0.033) = 677.6 \text{ nm}$$

Shifted further into the red. Hence: **redshift**.

The most distant observed galaxies have z > 10 — their light has been stretched by a factor of more than 11 during its journey. The universe was 13.8 billion years ago. That light left when the universe was approximately 400 million years old.

---

### 3. Gravitational Redshift

Einstein's General Theory of Relativity predicts a second form of redshift unrelated to motion.

Light climbing out of a gravitational well loses energy. Since the energy of a photon is E = hf, losing energy means losing frequency. The light redshifts.

$$z_{grav} = \frac{GM}{rc^2}$$

Where:
- `G` = gravitational constant (6.674 × 10⁻¹¹ N·m²/kg²)
- `M` = mass of the gravitating body
- `r` = distance from the centre of mass
- `c` = speed of light (3 × 10⁸ m/s)

For a photon escaping from the surface of the Sun (M = 2 × 10³⁰ kg, r = 7 × 10⁸ m):

$$z_{grav} = \frac{(6.674 \times 10^{-11})(2 \times 10^{30})}{(7 \times 10^8)(9 \times 10^{16})} \approx 2.1 \times 10^{-6}$$

Tiny. But measurable. GPS satellites must correct for this effect — clocks on satellites run slightly faster than clocks on the surface because they are higher in Earth's gravitational potential. Without the correction, GPS would accumulate errors of ~38 microseconds per day, translating to ~10 km of position error per day.

---

### 4. Keplerian Orbits and the Return to Centre

Johannes Kepler (1571–1630) derived three laws governing planetary motion from Tycho Brahe's observational data:

**First Law:** Planets orbit the Sun in ellipses, with the Sun at one focus.

**Second Law:** A line connecting a planet to the Sun sweeps equal areas in equal times. (Planets move faster when closer, slower when farther — conservation of angular momentum.)

**Third Law:**
$$T^2 \propto a^3$$

The square of the orbital period is proportional to the cube of the semi-major axis. A planet twice as far from the Sun takes 2^(3/2) = 2.83 times longer to complete one orbit.

The Keplerian return is the central fact of orbital mechanics: **gravity always returns a body to its closest approach point.** An object thrown outward will always come back, unless it exceeds escape velocity. The pull of the centre mass is the dominant organising force of every solar system, every galaxy, and every orbit ever measured.

---

### 5. The REDSHIFT Surface

The REDSHIFT surface on PARALLAX, SINGULARITY, and PLASMA implements three physical phenomena in a single control:

**Y-axis away from you (push):** Recession → redshift → frequency drops
$$f_{out} = f_{in} \cdot (1 - z)$$

**Y-axis toward you (pull):** Approach → blueshift → frequency rises
$$f_{out} = f_{in} \cdot (1 + z)$$

**Keplerian return:** When released, the joystick returns to centre — not because of a spring, but because it models gravitational attraction. The velocity of return follows the same curve as a body falling from orbit back to periapsis. The mathematical return curve is:

$$r(t) = a(1 - e \cos E)$$

Where `e` is orbital eccentricity and `E` is the eccentric anomaly, solved iteratively from **Kepler's Equation:** M = E − e sin E.

This is not approximate. The hardware uses the actual Keplerian solution.

The REDSHIFT surface is calibrated to **PSR J0108-1431 at 1.238 Hz** — the closest known pulsar. The centre position represents that frequency. Every departure from centre is a departure from that anchor. Every release is a gravitational return.

---

### 6. Why This Matters for Sound Design

The standard pitch-bend wheel applies linear interpolation between a minimum and maximum semitone value. It has no physics. Its return is a spring with a fixed constant.

REDSHIFT applies:
- Doppler frequency shift (non-linear at high velocities)
- Gravitational curve on approach/recession
- Keplerian trajectory on return (elliptical, not linear)

The result is a pitch deviation with the same mathematics as a satellite's elliptical orbit. Sounds made with REDSHIFT move the way real objects in space move — accelerating on approach, decelerating on recession, with a curved, physically-correct return.

You cannot tune this by ear and arrive at these numbers. You need the equations.

---

### Discussion Questions

1. The Andromeda Galaxy (M31) shows a **blueshift** in its spectral lines, not a redshift. Given what you've learned, what does this mean? Is the universe's expansion uniform?

2. A musician is standing on a moving train, playing a concert A (440 Hz) on a trumpet. The train is moving at 60 m/s toward a stationary listener. What pitch does the listener hear? (Use speed of sound = 343 m/s.) Express the answer in Hz and identify the nearest musical note.

3. The GPS system requires two relativistic corrections: special relativistic time dilation (clocks on fast-moving satellites run slow) and gravitational redshift (clocks higher in the gravity well run fast). These effects partially cancel. Which is larger, and by how much? If neither correction were applied, how far would your GPS position drift in one hour?

4. Using PARALLAX or PLASMA's REDSHIFT surface: set a sustained note, then push the joystick away slowly and release. Listen to the return trajectory. Does the return feel "physical"? What would a linear spring-return sound like by comparison?

---

*Standards: NSF Physics Grade 11 (waves, electromagnetism, special relativity), UWI PHYS2401, AP Physics C: Electricity & Magnetism. Luminous Works LLC / JUICY Academy COS-02.*
