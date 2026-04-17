# WIS-04: The Code Beneath Your Feet
## Women in STEM — Lesson 4

**Core concept:** Geodesy, mathematical modelling, GPS satellite navigation  
**Duration:** 90 minutes  
**Subject:** Dr. Gladys Mae West  
**Institution:** US Naval Weapons Laboratory, Dahlgren, Virginia  
**Date of record:** 1956–1998 · GPS mathematical model published 1986

---

### Opening Statement

> *"I just did the work. I didn't think about whether it was important. You do the work in front of you as well as you can do it. That's all."*
> — Dr. Gladys West

Every time you open a map on your phone, a network of satellites 20,200 kilometres above Earth triangulates your position to within a few metres.

The mathematics that makes this possible — the precise model of Earth's shape that GPS satellites use to calculate ground position — was built by a Black woman named Gladys West, working at the US Naval Weapons Laboratory in Dahlgren, Virginia, from the 1950s through the 1980s.

Her name did not appear in the GPS origin story for decades.

In 2018, she was inducted into the Air Force Space and Missile Pioneers Hall of Fame. She was 87 years old. She had not been aware, until fairly recently, that the model she built was what GPS runs on.

She found out at her sorority reunion when someone mentioned it. She had not connected what she built to what GPS became.

She just did the work.

---

### 1. The Problem of Earth's Shape

GPS navigation requires solving a deceptively difficult problem: **where are you, exactly, on the surface of Earth?**

This seems simple until you ask: what shape is Earth?

Earth is not a sphere. It is not a perfect ellipsoid. It is an irregular, lumpy **geoid** — a shape defined by the surface where Earth's gravitational potential is equal everywhere (the equipotential surface that matches mean sea level globally). Mountains, ocean trenches, variations in the density of the mantle below the crust — all of these distort the geoid from a smooth mathematical shape.

A GPS satellite broadcasting your position needs to know the exact relationship between:
1. Its own position in orbit (known from orbital mechanics)
2. The signal travel time to your receiver (known from timing)
3. The exact shape of Earth's surface at your location

If the model of Earth's shape is wrong, your position is wrong. For military applications — the original purpose of GPS — errors of even tens of metres could mean the difference between hitting a target and missing it.

---

### 2. The Mathematics of the Geoid

Gladys West's job was to build a mathematical model of Earth's shape accurate enough to support satellite navigation.

The starting point is the **reference ellipsoid** — a best-fit smooth ellipse rotated around Earth's polar axis:

$$\frac{x^2 + y^2}{a^2} + \frac{z^2}{b^2} = 1$$

Where:
- `a` = semi-major axis (equatorial radius) = 6,378,137.0 m
- `b` = semi-minor axis (polar radius) = 6,356,752.3 m
- **Flattening:** f = (a−b)/a = 1/298.257

But the real geoid deviates from this ellipsoid by up to ±100 metres in different locations. The deviations (called **geoid undulations** or **geoid heights**, N) must be mapped and modelled.

Gladys West used satellite altimetry data — radar signals bounced from satellite to ocean surface and back — combined with data from surface gravity measurements and the orbital perturbations of early satellites (whose paths were affected by the uneven mass distribution of Earth below them) to compute the geoid model.

The mathematical technique was **least squares adjustment** — minimising the sum of squared residuals between observations and model:

$$\text{minimise } S = \sum_{i=1}^{n} w_i \left(l_i - f(x)\right)^2$$

Where `l_i` are observations, `f(x)` is the model prediction, and `w_i` are weights (how much to trust each observation). This is solved iteratively — billions of calculations, done on early mainframe computers programmed in FORTRAN.

West programmed these calculations herself. The accuracy of the final model — the WGS 84 ellipsoid and geoid model, which GPS satellites use to this day — depended on her mathematics.

---

### 3. WGS 84 — The Standard That GPS Runs On

The **World Geodetic System 1984 (WGS 84)** is the coordinate reference system used by GPS globally. Every coordinate on your phone's map — every latitude and longitude — is expressed relative to WGS 84.

WGS 84 was the product of decades of geodetic research at Dahlgren, the institution where Gladys West worked. Her 1986 technical report — *"Data Processing System Specifications for the GEOSAT Satellite Radar Altimeter Mission"* — is one of the foundational documents in the GPS mathematical ancestry.

The WGS 84 ellipsoid parameters she helped refine:
- Semi-major axis: a = 6,378,137.0 m (accurate to ±0.1 m)
- Flattening: f = 1/298.257223563
- Angular velocity: ω = 7.292115 × 10⁻⁵ rad/s
- Earth's gravitational constant: GM = 3.986004418 × 10¹⁴ m³/s²

The GPS system requires the geoid model to be accurate to approximately **±1 metre globally** to provide the claimed civilian accuracy of ±5 metres. Military GPS requires higher accuracy still.

West's contributions were foundational to achieving this.

---

### 4. The Life Behind the Work

Gladys West was born in 1930 in Sutherland, Virginia — a rural farming community. Her parents farmed tobacco. She saw farming as a life of relentless labour with no path out.

She was determined to find another path.

She graduated as valedictorian of her high school class. She won a scholarship to Virginia State College — one of the historically Black colleges (HBCUs) — where she studied mathematics. She graduated in 1952 and began teaching.

In 1956, she was hired by the US Naval Weapons Laboratory as a mathematician — one of only a handful of Black employees, and one of even fewer women. She spent 42 years there.

She married Ira West, who also worked at the Naval Weapons Laboratory. While raising a family and working full-time, she completed a Master's degree in Public Administration. Later, after her retirement, she returned to school for a doctorate.

She received her PhD from Virginia Tech at age 88.

---

### 5. The Invisibility Problem

The GPS origin story, as typically told, centres on engineers, physicists, and military project managers — almost exclusively white men. The mathematical infrastructure that GPS depends on — the geoid model, the reference ellipsoid, the satellite altimetry algorithms — was built by teams of computers, many of them Black women like Gladys West, whose contributions were documented in technical reports, not press releases.

Technical reports are not the same as press releases. They do not generate recognition. They generate GPS.

West was inducted into the Air Force Space and Missile Pioneers Hall of Fame in 2018 because a retired Air Force officer read her biography and recognised what she had built. Before that, she had no public recognition connected to GPS.

Her response, when asked how she felt about finally being recognised: *"I'm glad the story is getting out. But I didn't do it for recognition. I did it because it needed to be done right."*

---

### Discussion Questions

1. The WGS 84 geoid model has been updated several times since 1984, incorporating more precise satellite data. The current version is WGS 84 (G2139), updated in 2021. Why is it necessary to update a model of Earth's shape? What changes about Earth over time that would require updates to the geoid model?

2. GPS requires signals from at least **four satellites** to determine a three-dimensional position plus accurate time. Why four, and not three? (Hint: consider the number of unknowns — x, y, z, and time — and the number of equations needed to solve for them.)

3. Gladys West used least-squares adjustment to fit a mathematical model to noisy observational data. This is the same mathematical technique used in machine learning, climate modelling, and medical statistics. Why is minimising the sum of squared errors, rather than just the sum of errors, a better strategy? What would happen if you minimised the sum of absolute errors instead?

4. West continued her education throughout her career, completing a PhD at 88. What does this tell us about the relationship between formal credentials and actual expertise? At what point in her life did she possess the knowledge that contributed to GPS — before or after her doctorate?

---

*Standards: NSF Mathematics & Physics Grade 11–12, UWI MATH3301 (numerical methods), AP Calculus BC, AP Statistics. Luminous Works LLC / JUICY Academy WIS-04.*
