# AIS-02: Now I Am Become Death
## Artificial Intelligence — Lesson 2

**Core concept:** Nuclear physics · The ethics of building what cannot be unbuilt · Von Neumann and the computer · The Oppenheimer problem  
**Duration:** 90 minutes  
**Subject:** The Manhattan Project — 1939–1945  
**Date of record:** 16 July 1945, 05:29:45 MWT — Trinity Test Site, New Mexico  
**Physics of record:** $E = mc^2$

---

### Opening Statement

> *"We knew the world would not be the same. A few people laughed. A few people cried. Most were silent. I remembered the line from the Hindu scripture, the Bhagavad Gita — 'Now I am become Death, the destroyer of worlds.' I suppose we all thought that, one way or another."*
> — J. Robert Oppenheimer, on witnessing the Trinity test, 1945

At 05:29:45 on the morning of 16 July 1945, the first nuclear device ever detonated exploded over the New Mexico desert.

The yield was equivalent to 21 kilotons of TNT. The fireball reached temperatures four times hotter than the surface of the Sun. The shockwave was felt 160 kilometres away. A blind woman in Albuquerque reported seeing the flash.

The scientists watching from a bunker 9 kilometres away had spent three years building it. Several of them wept. Several laughed. Robert Oppenheimer, the scientific director of the project, reached for a line from a 2,000-year-old Hindu text.

Three weeks later, the device was used on human beings.

This lesson is about the physics that made it possible, the people who built it, the resources from Africa that fuelled it, the machine it required that gave birth to the computer, and the ethical question it poses to every scientist who has ever built something powerful enough to change the world:

**Once you build it, can you take it back?**

That question is not historical. It is the central question of artificial intelligence. Oppenheimer asked it first.

---

### 1. The Letter That Started It

On 2 August 1939 — three weeks before Germany invaded Poland — a letter was delivered to President Franklin D. Roosevelt. It was signed by **Albert Einstein**.

Einstein had been persuaded to sign it by a Hungarian physicist named **Leó Szilárd**, who had fled Nazi Germany in 1933 and had been lying awake at night since 1934 thinking about what a nuclear chain reaction could do in a bomb.

The letter warned Roosevelt that recent research in nuclear physics — specifically the discovery of uranium fission by Otto Hahn and Fritz Strassmann in Berlin — made it likely that "extremely powerful bombs of a new type may thus be constructed." It warned that Germany was already pursuing this research.

Roosevelt read it. Within weeks, he established the Advisory Committee on Uranium. Within two years, that became the **Manhattan Project** — the largest scientific undertaking in human history to that point.

The irony contains the whole story of this lesson:

The scientists who built the weapon that would end the Second World War were **almost entirely European Jews** who had fled the Nazi regime that made the weapon necessary.

| Scientist | Origin | Fled |
|-----------|--------|------|
| Albert Einstein | Germany | 1933 |
| Leó Szilárd | Hungary | 1933 |
| Enrico Fermi | Italy | 1938 (wife Jewish) |
| Edward Teller | Hungary | 1933 |
| Hans Bethe | Germany | 1933 |
| **John von Neumann** | Hungary | 1933 |
| Niels Bohr | Denmark | 1943 (rescued by British intelligence) |

Hitler's race laws drove the greatest concentration of scientific talent in the 20th century to the United States. Then the United States aimed them at Hitler.

---

### 2. The Physics — $E = mc^2$

The theoretical foundation of the Manhattan Project is Einstein's 1905 equation:

$$E = mc^2$$

Where:
- $E$ = energy (joules)
- $m$ = mass (kilograms)
- $c$ = speed of light in a vacuum ($3 \times 10^8$ m/s)

The implication: mass and energy are equivalent. A small amount of mass contains an enormous amount of energy — because $c^2 = 9 \times 10^{16}$ m²/s² is an immense multiplier.

**Nuclear fission** releases this energy by splitting a heavy atomic nucleus. When a uranium-235 nucleus absorbs a neutron, it becomes unstable and splits:

$$^{235}_{92}\text{U} + ^1_0\text{n} \rightarrow ^{141}_{56}\text{Ba} + ^{92}_{36}\text{Kr} + 3\,^1_0\text{n} + \text{energy}$$

Each fission event releases approximately **200 MeV** (megaelectronvolts) of energy — and, critically, **3 free neutrons**, each capable of triggering another fission event.

This is the **chain reaction**. If each fission produces enough neutrons to trigger more than one subsequent fission, the reaction is **supercritical** — it multiplies exponentially. The number of fissions doubles every few nanoseconds. Within microseconds, an enormous fraction of the available atoms have split.

**Critical mass:** The minimum mass of fissile material required to sustain a chain reaction. Below this threshold, too many neutrons escape the material before hitting another nucleus. The critical mass of pure uranium-235 is approximately **52 kilograms** in a spherical configuration (reduced significantly with a neutron reflector surrounding it).

The **implosion design** — used in the Fat Man bomb dropped on Nagasaki — used conventional explosives arranged precisely around a subcritical sphere of plutonium. When detonated simultaneously from all directions, the shockwave compressed the plutonium to supercriticality in microseconds. The timing required precision to within one microsecond across 32 detonation points.

Those timing calculations were done by hand, and then by **ENIAC**.

---

### 3. The Congo — What the Curriculum Never Tells You

The uranium that fuelled the Manhattan Project came primarily from a single mine: **Shinkolobwe**, in the Katanga province of the Belgian Congo — the country now called the Democratic Republic of Congo.

Congolese uranium ore was extraordinary: **65% pure uranium oxide**. The next best deposits, in Canada and Colorado, were less than 1% pure. Without Congolese ore, the Manhattan Project could not have proceeded on the timeline that ended the war.

The mine was operated under Belgian colonial authority. Congolese workers extracted the ore. They were not told what it was. They were not told where it went. They were not told what it would be used for.

The United States purchased 1,200 tonnes of Congolese uranium ore in 1940 — the year before the Manhattan Project was officially launched. The purchase was arranged by Edgar Sengier, the Belgian director of Union Minière du Haut Katanga, who had the foresight to ship the ore to a warehouse in Staten Island, New York, anticipating American interest.

The Congolese miners who extracted the ore received no compensation, no recognition, and no warning about the radioactive nature of what they handled.

The bomb that changed history was built on African labour and African resources, by European refugees, for an American government.

This is not a footnote. This is the structure.

---

### 4. John von Neumann — The Man in Both Rooms

**John von Neumann** is the figure who connects the Manhattan Project to the history of artificial intelligence.

Born in Budapest in 1903 into a wealthy Jewish banking family, von Neumann demonstrated mathematical ability so extreme that his university professors consulted him as a peer before he had finished his undergraduate degree. He held a simultaneous PhD in mathematics from Budapest and a degree in chemical engineering from ETH Zürich. He joined the Institute for Advanced Study in Princeton in 1933, the same year Hitler came to power, and never returned to Europe.

At Los Alamos, von Neumann was responsible for the mathematical design of the **implosion lens** — the precisely shaped conventional explosive charges that had to compress the plutonium core symmetrically in nanoseconds. The calculations were staggering. The tolerances were beyond what hand computation could reliably achieve.

Von Neumann went to Aberdeen Proving Ground and saw ENIAC. He understood immediately what it was.

In 1945, he wrote the **"First Draft of a Report on the EDVAC"** — a document that described the architecture of a stored-program digital computer. The report specified:
- A processing unit performing arithmetic and logic
- A **separate memory unit** storing both data *and* the program instructions
- An input/output mechanism
- A control unit sequencing operations

This is the **von Neumann architecture**. Every computer built since 1945 — including the one running this text — uses it.

The critical innovation: **the program is stored in memory alongside the data**. It can be modified by the computer itself. A computer that can rewrite its own instructions is a Universal Turing Machine made physical.

Von Neumann got the theoretical framework from Turing's 1936 paper. Turing got the hardware implementation from von Neumann's 1945 draft. Between those two documents, the modern computer was born — as a tool designed, in part, to calculate how to build a more efficient nuclear weapon.

Von Neumann also founded **game theory** with Oskar Morgenstern — the mathematical study of strategic decision-making under conditions of conflict and cooperation. The **Minimax theorem**, which he proved in 1928, is the direct mathematical ancestor of the algorithms used in chess engines, Go-playing AI, and reinforcement learning systems.

One man. The bomb. The computer architecture. Game theory. He was everywhere.

He died of bone cancer in 1957 — almost certainly caused by radiation exposure during nuclear testing. He was 53.

---

### 5. Trinity — 16 July 1945

The Trinity test was conducted at 05:29:45 on 16 July 1945 at the Jornada del Muerto desert in New Mexico.

Yield: **21 kilotons TNT equivalent**.  
Fireball temperature: approximately **100 million °C** at detonation — roughly four times the surface temperature of the Sun.  
Shockwave: felt at distances up to 160 km.  
The tower on which the device was mounted was **vaporised**.  
The sand beneath it was **fused into glass** — a new mineral, later named **trinitite**, pale green, mildly radioactive.

Oppenheimer's words, recalled decades later, were from the Bhagavad Gita. Elsewhere, he quoted a different line: *"I am become Death."* Physicist Kenneth Bainbridge, who directed the test, turned to Oppenheimer and said: *"Now we are all sons of bitches."*

The scientists had been told the device would end the war. They were not told the decision about how it would be used had already been made.

---

### 6. Hiroshima and Nagasaki

**6 August 1945, 08:15 local time, Hiroshima.**

Little Boy — a gun-type uranium bomb, yield approximately 15 kilotons — was detonated 600 metres above Shima Hospital in the centre of Hiroshima.

Approximately **70,000–80,000 people** died instantly. By the end of 1945, the death toll reached **90,000–166,000** from blast, burns, and acute radiation syndrome.

**9 August 1945, 11:02 local time, Nagasaki.**

Fat Man — the implosion-type plutonium bomb, yield approximately 21 kilotons — was detonated over Nagasaki. The original target that day was Kokura. Cloud cover redirected the aircraft to the secondary target.

Approximately **40,000 people** died instantly. Total deaths by end of 1945: **60,000–80,000**.

The majority of the dead were civilians.

**The Franck Report**, written in June 1945 by a committee of Manhattan Project scientists led by James Franck, had explicitly warned against using the bomb on a populated civilian target without prior warning. It argued that a demonstration on an uninhabited area, witnessed by Japanese military and political leadership, was more likely to produce surrender with fewer casualties and less long-term damage to America's international standing.

The report was submitted to the Secretary of War. It was not acted upon.

Japan surrendered on 15 August 1945.

---

### 7. The Doomsday Clock — When Scientists Try to Take It Back

In 1945, a group of Manhattan Project scientists founded the **Bulletin of the Atomic Scientists**. They had built the weapon. They could not unbuild it. What they could do was measure the distance between humanity and catastrophe — and report it publicly.

In 1947, they introduced the **Doomsday Clock**: a symbolic clock whose proximity to midnight represents the probability of human-caused global catastrophe. It was initially set at **7 minutes to midnight**.

It has been adjusted 25 times since. As of 2024, it stands at **90 seconds to midnight** — the closest it has ever been.

The scientists who built the first weapon of mass destruction spent the rest of their lives trying to prevent its use. Oppenheimer lost his security clearance in 1954 — the year Turing died — after being accused of Communist sympathies. The man who directed the project that ended World War II was deemed a security risk during the Red Scare.

The apparatus of security, secrecy, and state power that the Manhattan Project had helped create — turned on its creators.

---

### 8. The Oppenheimer Problem — And What It Has to Do with AI

*"The physicists have known sin, and this is a knowledge which they cannot lose."*  
— J. Robert Oppenheimer, 1947

The question that haunted Oppenheimer for the rest of his life is the same question that serious AI researchers are asking today:

**What happens when you build something more powerful than you can control, faster than governance can adapt, with consequences you cannot fully predict — and you know it?**

The Manhattan Project scientists knew the bomb was coming whether they built it or not. They believed the Germans were building it. They calculated that their participation gave them some control over the outcome. They were wrong about the level of control they would retain.

Today's AI researchers are in a structurally similar position:
- Powerful AI systems are being built whether any individual researcher participates or not
- The researchers who participate believe they have more influence over safety and deployment than those who abstain
- The governments and corporations deploying these systems are operating under timelines that governance frameworks cannot match

The **AI alignment problem** — ensuring that a sufficiently powerful AI system pursues goals that are actually beneficial to humanity — is Oppenheimer's problem restated in software.

The **Doomsday Clock** was the first systematic attempt to make the risk of catastrophic technology visible to the public and policymakers. The AI Safety community is attempting the same thing with the same urgency and the same uncertainty about whether anyone in power is listening.

The mathematics is different. The problem is the same.

---

### Discussion Questions

1. The Franck Report argued against using the bomb on a civilian population, proposing a demonstration instead. The decision-makers disagreed. The bomb was used twice on cities. In retrospect, was the Franck Report right? What criteria would you use to evaluate a decision made under conditions of total war, incomplete information, and enormous pressure to end the conflict quickly?

2. The Congo provided the uranium that made the Manhattan Project possible. Congolese workers extracted it without knowledge of its purpose or its hazards. Their labour is never part of the standard telling of this story. What is the effect — scientific, historical, and ethical — of omitting this from the record? Who is responsible for maintaining a complete record?

3. John von Neumann contributed to the Manhattan Project, to the stored-program computer, and to game theory — three of the most consequential developments of the 20th century. He was a refugee. His refuge was the Institute for Advanced Study at Princeton. What does this tell us about the relationship between persecution, migration, and scientific output? What talent is the Caribbean and Global South losing today through economic migration — and what would it take to change that?

4. Oppenheimer said the physicists had known sin. The AI researchers at DeepMind, OpenAI, and Anthropic who work on safety are, in many cases, people who believe they are preventing a catastrophe by staying inside organisations that are also accelerating it. Is this position coherent? Is it moral? Compare it explicitly to the position of the Manhattan Project scientists.

5. The Doomsday Clock has been maintained for 77 years. It currently stands at 90 seconds to midnight. Design a similar public-facing metric for AI risk — what would you measure, how would you represent it visually, who would govern it, and what would constitute progress toward safety versus acceleration toward catastrophe?

---

*Standards: NSF Physics & History of Science Grade 11–12, UWI PHYS2101 (nuclear physics) / HIST2201, AP Physics C, AP US History, AP World History, AP Computer Science Principles. Luminous Works LLC / JUICY Academy AIS-02.*
