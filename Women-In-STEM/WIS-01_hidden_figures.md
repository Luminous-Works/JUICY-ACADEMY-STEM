# WIS-01: The Numbers That Flew
## Women in STEM — Lesson 1

**Core concept:** Orbital mechanics, trajectory calculation, numerical computation  
**Duration:** 90 minutes  
**Subjects:** Katherine Johnson · Dorothy Vaughan · Mary Jackson · Christine Darden  
**Institution:** NACA / NASA, Langley Research Center, Hampton, Virginia  
**Date of record:** 1953–1970s

---

### Opening Statement

> *"I counted everything. I counted the steps to the road, the steps up to church, the number of dishes and silverware I washed... anything that could be counted, I did."*
> — Katherine Johnson

In 1962, astronaut John Glenn was preparing to become the first American to orbit the Earth. NASA had installed IBM electronic computers to calculate his trajectory. Glenn looked at the machine. Then he said:

**"Get the girl to check the numbers. If she says the numbers are good, I'm ready to go."**

The "girl" was Katherine Johnson. She was 44 years old. She had been computing orbital mechanics for NASA for nine years. She had calculated the trajectory for Alan Shepard's first spaceflight. She would later calculate the trajectory for Apollo 11 — the first Moon landing.

She worked in a building where the bathrooms were segregated. She had to fight to attend mission briefings. Her name did not appear on research reports for years because women's names were not included.

John Glenn would not fly until she personally verified the computer's answer.

Her numbers flew. Her name did not — until 2015, when President Obama awarded her the Presidential Medal of Freedom. She was 97 years old.

---

### 1. Who Were the Hidden Figures?

At the NACA (National Advisory Committee for Aeronautics, precursor to NASA) Langley Research Center in Virginia, a group of Black women worked as **human computers** — mathematicians who performed calculations by hand or with mechanical calculators.

They worked in a segregated wing. Their cafeteria was separate. Their bathrooms were labeled "Colored." They were addressed by first name by white colleagues who were addressed as "Mr." or "Mrs."

They were also the most mathematically precise calculators in the building.

**Katherine Johnson** (1918–2020)  
Degree in mathematics and French, West Virginia State College (summa cum laude, 1937). Specialised in orbital mechanics. Key contributions:
- Alan Shepard's Freedom 7 trajectory (1961) — first American in space
- John Glenn's Friendship 7 orbital trajectory (1962) — verified by hand
- Apollo 11 lunar trajectory (1969)
- Apollo 13 emergency return trajectory (1970) — calculated the path that brought the astronauts home after the explosion

**Dorothy Vaughan** (1910–2008)  
First Black supervisor at NACA/NASA. When electronic computers arrived in the early 1950s, Vaughan recognised they would replace human computers. She obtained a FORTRAN programming manual, taught herself to code, then taught every member of her team. She became one of NASA's first programmers — and ensured her entire group made the transition with her. Nobody was left behind.

**Mary Jackson** (1921–2005)  
NASA's first Black female engineer. To become an engineer required graduate-level coursework — which was taught only at a whites-only school in Virginia. Jackson petitioned the city of Hampton to attend. They granted an exception. She completed the courses, became an engineer, and spent her career advancing wind tunnel research. Later became NASA's Federal Women's Program Manager, working to improve hiring and promotion of women at the agency.

**Christine Darden** (born 1942)  
Aerospace engineer, expert in supersonic aerodynamics and sonic boom minimisation. Asked her supervisor directly why men with lesser qualifications were promoted ahead of her. He had no answer. She was promoted. She spent 25 years researching how to reduce the sonic boom from supersonic aircraft.

---

### 2. The Mathematics They Did

Katherine Johnson's work centred on **orbital mechanics** — the mathematics governing how an object moves through space under gravitational influence.

**The vis-viva equation** (orbital speed at any point in an orbit):

$$v = \sqrt{GM\left(\frac{2}{r} - \frac{1}{a}\right)}$$

Where:
- `v` = orbital speed at radius r
- `G` = gravitational constant
- `M` = mass of central body (Earth)
- `r` = current distance from centre of mass
- `a` = semi-major axis of the orbit

This equation calculates, at every instant, exactly how fast a spacecraft must travel to stay on its intended path. Too slow: it falls. Too fast: it escapes. The margin for error on a crewed orbital mission is measured in metres per second.

Katherine Johnson calculated these values — for multiple orbital passes, accounting for Earth's rotation and atmospheric drag — with pencil, paper, and a mechanical calculator, to an accuracy that the IBM computer matched when it was finally trusted enough to be used.

---

### 3. Dorothy Vaughan and FORTRAN

When the IBM 7090 mainframe arrived at NASA Langley in the late 1950s, the human computers faced obsolescence. Most were given no training and no path forward.

Dorothy Vaughan went to the library. She found a FORTRAN manual. She studied it. She returned to her team and taught them all.

FORTRAN (Formula Translation) was the first high-level programming language, designed for scientific computation. A sample FORTRAN program to compute orbital velocity:

```fortran
      PROGRAM ORBITAL
      REAL G, M, R, A, V
      G = 6.674E-11
      M = 5.972E24
      R = 6.771E6
      A = 6.771E6
      V = SQRT(G * M * (2.0/R - 1.0/A))
      WRITE(*,*) 'Orbital velocity (m/s):', V
      END
```

Vaughan did not just save her own career. She guaranteed that 30 Black women entered the computing age alongside the machine that was supposed to replace them.

---

### 4. The Segregated Bathroom

A scene from the historical record, not the film:

Katherine Johnson needed to use a bathroom. The nearest bathroom for "Colored" employees was 800 metres away — a different building on the other side of the campus. On days when she was deep in calculations, she ran. She did not complain formally. She had work to do.

In 1958, she asked to attend briefings that women were not invited to. She was told there was no rule against it. She attended. She sat at the table. She did the work.

In 2016, the building at NASA Langley that houses the computational sciences directorate was renamed the **Katherine G. Johnson Computational Research Facility**. The segregated bathroom is gone.

---

### 5. Why This Matters for STEM Students Today

The Hidden Figures were not exceptional because they overcame adversity. They were exceptional mathematicians — full stop — who were also required to overcome adversity that their white male colleagues never faced.

The question this lesson asks is not inspirational. It is structural:

**How many Katherine Johnsons did we lose?**

How many Black women with her mathematical gift never got the job? Never got the degree? Worked in fields that had nothing to do with their capabilities because no one offered them anything better?

The Hidden Figures were the ones who made it through. They are not the whole story. They are the part of the story that survived.

---

### Discussion Questions

1. Dorothy Vaughan made a decision: when the electronic computer arrived, she learned to program it. She did not wait to be trained. She did not wait to be invited. What does this decision tell us about the relationship between professional survival and proactive learning? How does this apply to students in the current era of AI?

2. John Glenn refused to fly until Katherine Johnson personally verified the computer's numbers. What does this reveal about the nature of trust in high-stakes technical systems? What is the difference between trusting a credential (a degree, a job title) and trusting a track record?

3. Mary Jackson had to petition the city government for permission to attend a class. She was not asking for special treatment — she was asking to be allowed to sit in a classroom. Calculate the cost to society of a policy that prevents qualified people from accessing education based on race. What kinds of innovations did we not get because of who was excluded?

4. Research one woman in STEM from the Caribbean or the African diaspora who is not mentioned in this lesson. Write three sentences: what she discovered or built, what barriers she faced, and what was named after her (if anything). If nothing was named after her, note that.

---

*Standards: NSF Physics & Mathematics Grade 10–12, Caribbean history integration, AP Physics C: Mechanics. Luminous Works LLC / JUICY Academy WIS-01.*
