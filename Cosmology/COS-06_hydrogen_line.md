# COS-06: The Channel No One Changed
## Cosmology — Lesson 6

**Core concept:** The HI 21cm line, neutral hydrogen in the interstellar medium, and the physics of SETI  
**Duration:** 90 minutes  
**Instrument tie-in:** Hydrogen — HI Signal Intelligence · BlackBox Element H·1  
**Lab:** Load Hydrogen. Load the WOW! Signal. Do not speak for 30 seconds.  
**Anchor frequency:** 1420.405751768 MHz · λ = 21.106 cm

---

### Opening Statement

> *"We do not know that an intelligent signal has been received. We do know that an unexplained one has."*  
> — John Kraus, Big Ear Observatory Director, on the WOW! Signal, 1977

On August 15, 1977, astronomer Jerry Ehman was reviewing a printout from the Big Ear radio telescope in Delaware, Ohio, when he circled six characters in red ink and wrote one word in the margin: **Wow!**

The signal lasted 72 seconds — exactly as long as the telescope's observing window allowed. It came from the direction of the constellation Sagittarius. It was centred on 1420 MHz. It has never repeated.

It remains the strongest candidate for extraterrestrial intelligent contact in the history of radio astronomy.

It was detected on the hydrogen frequency. This lesson explains why that matters.

---

### 1. The Hyperfine Transition

Neutral hydrogen — the simplest atom in the universe — consists of one proton and one electron.

Both particles possess a quantum property called **spin** — an intrinsic angular momentum that causes each particle to behave like a tiny magnet. The electron's spin can be either **parallel** (aligned with the proton's spin) or **anti-parallel** (opposed to it).

The parallel state has slightly higher energy than the anti-parallel state. When an electron spontaneously flips from parallel to anti-parallel, it releases the energy difference as a photon.

The frequency of that photon is:

$$\nu_{HI} = 1420.405751768 \text{ MHz}$$

The wavelength:

$$\lambda = \frac{c}{\nu} = \frac{2.998 \times 10^8 \text{ m/s}}{1.420 \times 10^9 \text{ Hz}} = 0.211 \text{ m} = 21.1 \text{ cm}$$

This transition is called the **hyperfine transition** because the energy splitting is extremely small — approximately 5.9 × 10⁻⁶ eV, compared to the ~13.6 eV needed to ionise hydrogen entirely.

| Quantity | Value |
|---------|-------|
| Rest frequency | 1420.405751768 MHz |
| Wavelength | 21.106 cm |
| Photon energy | 5.9 × 10⁻⁶ eV |
| Spontaneous transition probability | 2.87 × 10⁻¹⁵ s⁻¹ |
| Mean transition time (single atom) | ~11 million years |

The mean transition time is 11 million years. A single hydrogen atom, left undisturbed, will wait 11 million years before emitting this signal.

But there are approximately **10⁶⁷ hydrogen atoms in the Milky Way**. Even with a transition probability of once per 11 million years per atom, the combined flux from the galactic plane is bright enough to detect with a horn antenna built from PVC pipe and plumbing fittings.

---

### 2. Why This Frequency Is Universal

In 1959, physicists Giuseppe Cocconi and Philip Morrison published a paper in *Nature* titled "Searching for Interstellar Communications." Their argument was simple:

Any technologically advanced civilisation capable of interstellar radio communication would necessarily understand atomic physics. They would know about neutral hydrogen — the most abundant element in the universe. They would know its hyperfine transition frequency. And they would recognise that any other civilisation capable of receiving would also know this frequency.

1420 MHz is the one channel that requires no prior agreement. No exchange of codes. No shared language. Only the laws of physics — which are the same everywhere.

It is the universal dial tone.

> *"The hydrogen frequency is the watering hole of the cosmos — the place where all creatures come to drink."*  
> — Bernard Oliver, NASA SETI Institute

This reasoning was so compelling that it guided the design of the Arecibo radio telescope and every major SETI programme that followed. The WOW! Signal was detected at 1420 MHz in 1977. The Breakthrough Listen programme continues to monitor this frequency today.

---

### 3. What Hydrogen Reveals About the Galaxy

Because neutral hydrogen is ubiquitous in the interstellar medium, and because its emission frequency is known to extreme precision, it functions as a velocity probe across the entire galaxy.

When a hydrogen cloud is moving toward or away from Earth, the detected frequency is Doppler-shifted:

$$\nu_{obs} = \nu_{rest} \left(1 \pm \frac{v_r}{c}\right)$$

Where:
- `ν_obs` = observed frequency
- `ν_rest` = 1420.405751768 MHz (rest frequency)
- `v_r` = radial velocity (positive = receding)
- `c` = speed of light

A cloud moving away from Earth at 10 km/s shifts the signal to:

$$\Delta\nu = \frac{10,000 \text{ m/s}}{2.998 \times 10^8 \text{ m/s}} \times 1.420 \times 10^9 \text{ Hz} \approx 47.4 \text{ kHz}$$

By mapping these Doppler shifts across the sky, astronomers have produced detailed maps of the spiral arm structure of the Milky Way — structure that cannot be seen optically due to dust absorption. The hydrogen line sees through the dust. It sees everything.

In Hydrogen, the crosshair annotation displays this Doppler velocity in real time: `1420.406 MHz · ΔV 0.0 km/s` means the observed cloud is at rest relative to the Local Standard of Rest (LSR). A nonzero ΔV value tells you the gas is moving — and from the direction, you can infer which spiral arm you are observing.

---

### 4. The WOW! Signal

At 22:16 EST on August 15, 1977, the Big Ear telescope swept over a region of sky in Sagittarius. It detected a narrowband signal at 1420 MHz. The signal lasted 72 seconds — the full duration of the telescope's beam — and rose and fell in exactly the gaussian profile expected from a fixed point source in the sky.

The signal string printed on the original observation log was:

```
6EQUJ5
```

Each character represents the signal-to-noise ratio at that moment. In Big Ear notation, digits 0–9 represent SNR 0–9; letters A–Z represent SNR 10–35. The character `U` = SNR 30. The peak SNR of the WOW! Signal was **30 times background noise**.

| Property | Value |
|---------|-------|
| Date | August 15, 1977 · 22:16 EST |
| Frequency | ~1420 MHz (exact value uncertain — single-channel receiver) |
| Duration | 72 seconds |
| Peak SNR | ~30 (character 'U' in Big Ear notation) |
| Bandwidth | ≤ 10 kHz (appears narrowband) |
| Source direction | Sagittarius · χ Sagittarii field |
| Polarisation | Unknown (single feed) |
| Repetitions | None confirmed in 47+ years of follow-up |

What makes it anomalous:

1. **Narrowband emission.** Natural astrophysical sources are broadband. A narrowband signal at exactly the hydrogen rest frequency is not expected from any known natural process.
2. **Correct frequency.** 1420 MHz is what Cocconi and Morrison predicted an intelligent signal would use.
3. **Correct profile.** The signal's rise and fall matches the antenna beam pattern — consistent with a fixed point source, not satellite interference (which would drift).
4. **No repetition.** Despite repeated observations of the same sky region by multiple telescopes, it has never been detected again.

No explanation — natural or artificial — has been definitively confirmed.

---

### 5. The Instrument

**Hydrogen** (Element H·1, BlackBox Industries) is a scientific RF signal intelligence instrument built around the HI 21cm line. It runs in two modes:

**Archive Mode** — Nine canonical radio astronomy recordings are loaded by default. Each represents a distinct class of signal:

| Recording | Frequency | What You Are Hearing |
|-----------|-----------|---------------------|
| Galactic Plane · HI 21cm | 1420.406 MHz | Neutral hydrogen emission from the galactic midplane |
| Cygnus A | 1400.000 MHz | Radio galaxy 600 million light-years away, 1570 Jy |
| PSR B0329+54 | 408.000 MHz | Dead star spinning 1.4 times per second |
| Proxima Centauri · BLC-1 | 982.002 MHz | Narrowband signal from the nearest star. Origin unresolved. |
| WOW! Signal | 1420.456 MHz | 72 seconds. Never repeated. |
| Solar Burst · Type III | 1415.000 MHz | Electrons accelerated by solar magnetic reconnection |
| Jupiter S-burst | 20.100 MHz | Jovian lightning driven by the volcano moon Io |
| Voyager I | 8419.000 MHz | Telemetry from 23+ billion km |
| FRB 121102 | 1350.000 MHz | Extragalactic explosion from a source at z=0.19 |

**Observatory Mode** — with an RTL-SDR dongle (~$30), a horn antenna, and a low-noise amplifier, Hydrogen connects to live sky data. The oscilloscope, waterfall spectrogram, and spectrometer update in real time.

The oscilloscope in Hydrogen shows the raw I/Q signal — the in-phase and quadrature components of the baseband. When you load the Jupiter S-burst, you are watching the actual waveform of a plasma discharge from the Io-Jupiter magnetospheric interaction — 600 million kilometres from Earth, showing up as a voltage fluctuation on a $30 USB dongle.

---

### 6. The Audio Parallel — The Universal Tuning Fork

Every musician knows the A440 standard. Concert pitch: A = 440 Hz. It is not a law of physics. It is a human convention, agreed upon in 1939 at an international conference. A different conference could have chosen a different frequency.

1420.405751768 MHz is not a convention. It is a law of physics. You cannot choose a different value. Every hydrogen atom in the observable universe emits at this frequency. It was true before the Earth existed. It will be true after the Sun dies.

If you were to design the ultimate tuning fork — one that any civilisation anywhere in the universe could use as a universal pitch reference — it would resonate at 1420 MHz.

This is why Cocconi and Morrison were right. This is why the Big Ear was pointed at 1420 MHz. This is why the WOW! Signal was significant.

And this is why **Hydrogen's Nixie display shows 1420.406 MHz by default**. Not because it is a radio app. Because it is tuned to the one frequency the universe has agreed upon.

---

### Lab — Hydrogen Observatory

**Required:** Hydrogen app (browser, no installation) · `hydrogen.luminousworksllc.com`

**Exercise 1 — The Baseline**
1. Open Hydrogen. Allow the boot sequence to complete.
2. The default recording is the Galactic Plane at 1420.406 MHz.
3. Observe the oscilloscope. Note the waveform character — broad, irregular, noise-like. This is what thermal radio emission looks like.
4. Observe the waterfall spectrogram. The bright band at centre frequency is the HI line.
5. Note the crosshair annotation: `1420.406 MHz · ΔV 0.0 km/s`. The gas you are observing is at rest relative to the Local Standard of Rest.
6. **Question:** What would a Doppler shift of +100 km/s look like on the waterfall? Sketch it.

**Exercise 2 — The WOW! Signal**
1. In the left library panel, find and click **WOW! Signal · 1977**.
2. Observe the oscilloscope. The signal is narrow — compare it to the galactic plane.
3. The annotation panel shows: SNR 30. Natural radio sources rarely exceed SNR 2–3 from this sky region.
4. The recording is 72 seconds. Watch the full duration.
5. **Question:** Why does the recording end at 72 seconds? What does this tell you about the observation geometry of the Big Ear telescope?

**Exercise 3 — The Planetary Signal**
1. Load **Jupiter S-burst · Io**.
2. Watch the oscilloscope. This signal does not look like noise. It has structure — bursts, edges, sharp transients.
3. **Question:** What physical process creates these sharp transients? How does it differ from thermal emission?

**Exercise 4 — The Comparison (A/B Mode)**
1. Load the Galactic Plane into Slot A (default).
2. Click the **B** button on the WOW! Signal card to load it into Slot B.
3. Both waterfall displays now show simultaneously.
4. **Question:** Describe two visible differences between the galactic plane baseline and the WOW! Signal in the waterfall display. What would these differences mean if the WOW! Signal were of natural origin?

---

### Discussion Questions

1. The WOW! Signal has not repeated in 47 years of follow-up observations. Does this make it *more* or *less* likely to be of intelligent origin? Consider both possibilities and argue the case for each.

2. The hyperfine transition of hydrogen has a mean transition time of 11 million years per atom. Explain, using the concept of large numbers, why the galactic HI emission is nevertheless detectable with amateur equipment. Show the calculation.

3. If a civilisation 100 light-years away transmitted a signal today at 1420 MHz, when would it arrive? What would Earth's political situation have been when they sent it?

4. The Voyager I signal has a flux density of approximately 10⁻²⁰ Watts per square metre at Earth. The WOW! Signal had a peak flux of approximately 212 Jy (1 Jy = 10⁻²⁶ W/m²/Hz). Which was stronger? By what factor? What does this tell you about the required transmitter power if the WOW! Signal was artificial?

5. The SETI Institute's Allen Telescope Array monitors 1420 MHz continuously. If you were designing a monitoring programme with limited telescope time, would you focus on 1420 MHz, or would you argue for a different frequency? Justify your answer using the Cocconi-Morrison reasoning.

---

*Standards: NSF Physics Grade 11 (electromagnetic spectrum, wave properties), UWI PHYS2401 (radio astronomy), AP Physics C. SETI context: Cocconi & Morrison (1959), Nature 184:844. WOW! Signal: Ehman (1977), Big Ear Observatory Report. Luminous Works LLC / JUICY Academy COS-06.*
