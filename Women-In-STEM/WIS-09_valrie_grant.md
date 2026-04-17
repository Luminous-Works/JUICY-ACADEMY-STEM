# WIS-09: The Woman Who Maps Jamaica
## Women in STEM — Lesson 9

**Core concept:** Geospatial science, LiDAR mapping, climate resilience, national spatial data infrastructure  
**Duration:** 90 minutes  
**Subject:** Dr. Valrie Grant, DBA, GISP  
**Origin:** Kingston, Jamaica  
**Foundation degree:** BSc Geology, University of the West Indies, Mona  
**Institution:** Fugro — Caribbean Market Specialist for Climate and Nature / Founder, GeoTechVision  
**Award of record:** 2020 WE Empower UN SDG Challenge Award (Vital Voices Global Partnership / Arizona State University)

---

### Opening Statement

> *"Geospatial intelligence is critical in addressing the problems of climate change, disaster management, resource management and economic development."*
> — Dr. Valrie Grant

Jamaica is an island of approximately 10,990 square kilometres. It sits in the centre of the Caribbean Sea, surrounded by ocean that is warming, rising, and intensifying the storms that cross it. Seventy percent of the Caribbean's population lives within the narrow coastal zone — within a few kilometres of sea level. The difference between one metre of elevation and two metres of elevation is the difference between a community that floods in a major hurricane and one that does not.

Someone must know exactly where one metre is.

In 2008, **Dr. Valrie Grant** founded **GeoTechVision** in Kingston, Jamaica — a company that builds the precise three-dimensional maps of land, coast, and ocean floor that governments, disaster managers, and climate scientists need to protect people. She holds a BSc in Geology from the University of the West Indies, a Master's in Geographic Information Systems, an MBA, and a doctorate. She is one of the most certified geospatial scientists in the Caribbean. She sits on United Nations committees. She is now the Caribbean Lead for Climate and Nature at **Fugro** — one of the world's largest geo-data companies — where her team recently produced a **3D digital twin of Jamaica's entire onshore and nearshore areas** using laser mapping from aircraft.

She is not mapping an abstraction. She is mapping the place where her students live.

---

### 1. Who She Is

Valrie Grant was born in Jamaica. She attended school in Kingston and earned her first degree — a **BSc in Geology** — at the **University of the West Indies, Mona**. Geology: the study of Earth materials, structures, and the physical processes that have shaped the surface her instruments would later map.

From UWI, she continued to:
- **MSc in Geographic Information Systems and the Environment** — Manchester Metropolitan University, UK
- **MBA** — Florida Institute of Technology, USA
- **DBA (Doctor of Business Administration)** — University of North Carolina at Charlotte, 2025

In parallel with her academic credentials, she earned the **GISP designation** — Geographic Information Systems Professional — the premier professional certification in geospatial science, awarded by the GIS Certification Institute. It marks the highest level of demonstrated competence in the field.

In 2008, she founded **GeoTechVision** in Kingston, with offices eventually extending to Guyana and project reach across St. Maarten, Turks and Caicos, and beyond. The company offers LiDAR mapping, UAV (drone) aerial surveys, 3D topographic modelling, GNSS field mapping, spatial database creation, and national spatial data infrastructure consultation.

She also founded **Jamaica Flying Labs** — a network of drone operators that provides rapid humanitarian mapping after disasters. When a hurricane struck, she coordinated **26 drone pilots and nearly 30 international organisations** to map an entire disaster zone in real time.

---

### 2. LiDAR — Measuring Earth with Light

The central technology of Dr. Grant's work is **LiDAR**: Light Detection and Ranging.

LiDAR is an **active remote sensing** system. Unlike photography, which records light reflected from surfaces passively, LiDAR fires its own laser pulses at the ground and measures the time it takes for each pulse to return. From that travel time, the precise distance to every point it strikes is calculated:

$$d = \frac{c \cdot t}{2}$$

where:
- $d$ = distance from sensor to ground point
- $c$ = speed of light ($3 \times 10^8$ m/s)
- $t$ = round-trip travel time of the laser pulse
- Divided by 2 because the light travels to the ground and back

A modern airborne LiDAR system fires **500,000 to over 1,000,000 laser pulses per second**, each one returning an x, y, z coordinate. The result is a **point cloud** — a three-dimensional map of the ground surface with centimetre-level precision.

For Jamaica, this means:

The coastline is not flat. It has micro-relief — small ridges, channels, slight rises — that determine exactly where water goes during storm surge. A map accurate to 5 metres cannot tell you this. A LiDAR point cloud accurate to 10 centimetres can. The difference between those two numbers is the difference between a useful coastal flood map and a useless one.

**Why elevation accuracy is life-critical:**

Current global datasets (SRTM, derived from 2000 shuttle radar measurements) have vertical accuracy of ±10 metres in flat terrain and worse in complex terrain. For a Caribbean island where the coastal zone averages 2–5 metres above sea level, ±10 metres of uncertainty means you don't know whether a given community floods.

Dr. Grant's LiDAR maps bring this uncertainty to ±10 centimetres. One hundredth the error. In a place where ten centimetres of elevation can be the difference between a home and a ruin.

---

### 3. Sea-Level Rise — The Stakes

The science behind why LiDAR matters for Jamaica begins with the physics of a warming ocean.

**Thermal expansion:** As water temperature rises, water molecules move faster and occupy more volume. The relationship between temperature and volume is described by the coefficient of thermal expansion:

$$\Delta V = V_0 \cdot \beta \cdot \Delta T$$

where $\beta$ is the volumetric thermal expansion coefficient of seawater (approximately $2.1 \times 10^{-4}$ per °C in the upper ocean) and $\Delta T$ is the temperature increase.

**Ice melt:** Melting of land ice (glaciers, ice sheets) adds mass to the ocean. The mass-to-sea-level relationship: adding 361 Gt (gigatonnes) of water to the ocean raises global mean sea level by approximately 1 mm.

**Combined effect:** The current measured rate of sea-level rise in the Caribbean is **3.40 ± 0.3 mm/year** (1993–2019), consistent with the global mean but now accelerating. Under high-emissions scenarios, the projected rise by 2100 is **0.6 to 1.0 metres** above 2000 levels.

One metre of sea-level rise, combined with storm surge from an intensifying hurricane, places communities currently considered safe — above the flood line on current maps — under water.

The only way to know **which communities** and **exactly when** is to have elevation data accurate enough to model that risk. That is what LiDAR provides. That is what Dr. Grant builds.

---

### 4. GNSS — How Coordinates Are Made Exact

LiDAR point clouds are only useful if their coordinates are accurate in absolute terms — not just relative to each other but referenced to the actual shape of the Earth. This requires **GNSS** (Global Navigation Satellite System) ground control.

GNSS receivers on the ground and in the aircraft establish their positions by receiving signals from multiple satellites simultaneously. The raw measurement is called a **pseudorange**:

$$\rho = r + c(\delta T_r - \delta T^s) + I + T + \varepsilon$$

where:
- $\rho$ = measured pseudorange (what the receiver calculates)
- $r$ = true geometric distance between satellite and receiver
- $c(\delta T_r - \delta T^s)$ = receiver and satellite clock errors (multiplied by speed of light)
- $I$ = ionospheric delay (signal slowed by ionised atmosphere)
- $T$ = tropospheric delay (signal slowed by lower atmosphere)
- $\varepsilon$ = noise

Consumer GPS (the kind in a phone) achieves ±5 metres accuracy because ionospheric and clock corrections are approximate. Survey-grade GNSS — using differential correction against a reference station with a precisely known position — achieves ±1 centimetre accuracy by eliminating the shared atmospheric and clock errors.

A LiDAR survey without GNSS ground control gives you a beautiful 3D model that could be offset from reality by metres. With survey-grade GNSS control, every laser point is globally accurate.

---

### 5. National Geospatial Information Management — The Governance Science

Dr. Grant's doctoral research (DBA, UNC Charlotte, 2025) examined a problem that no amount of better technology solves on its own.

Title: *"Factors Influencing the Adoption of National Geospatial Information Management (NGIM) in Small Island Developing States (SIDS)."*

**The problem:** A country can have access to LiDAR surveys, satellite imagery, and GIS software — and still fail to use any of it effectively for climate planning, disaster management, or development decisions. Why?

Her research identified the answer: it is not a technology problem. It is a governance problem. The critical factor determining whether a small island nation successfully builds and institutionalises its geospatial data infrastructure is **multi-level leadership** — government ministries, private sector, civil society, and international partners acting in coordination, not in silos.

Countries with strong NGIM frameworks can combine flood maps, population data, infrastructure records, and storm track models into a unified picture that answers: *which communities face which level of risk, and what interventions are possible?* Countries without this framework have all the same data in incompatible formats, held by different agencies that do not share, meaning no one can answer the question at all.

For Caribbean SIDS — where the stakes of climate adaptation are existential — she argued that geospatial governance is not optional infrastructure. It is survival infrastructure.

---

### 6. Jamaica Flying Labs — When the Science Goes to the Field

Theory becomes real on the day after a hurricane.

Dr. Grant founded **Jamaica Flying Labs** as part of the global WeRobotics network — a humanitarian UAV operator organisation that deploys drone-based mapping for disaster response and community resilience.

After a major hurricane, the urgent questions are: which roads are cut off? Which communities are isolated? Where is flooding most severe? Where is structural damage concentrated?

Satellite imagery takes days to acquire and process. Ground teams cannot reach cut-off areas. But drone pilots can fly in minutes.

Dr. Grant coordinated 26 drone pilots and nearly 30 international organisations to map a disaster zone in Jamaica — producing **orthomosaics** (stitched aerial photographs precisely georeferenced to the ground) and **digital elevation models** from drone-collected imagery processed through **Structure-from-Motion (SfM) photogrammetry**: an algorithm that identifies matching feature points across overlapping photographs and triangulates their three-dimensional positions geometrically, the same principle by which human eyes perceive depth — scaled up to map entire disaster zones.

That map went directly to relief logistics coordinators.

---

### 7. Recognition

| Award | Body | Year |
|-------|------|------|
| NCB Women in Business Award | NCB Jamaica | 2013 |
| JCC Young Entrepreneur of the Year | Jamaica Chamber of Commerce | 2014 |
| Commonwealth Woman Entrepreneur of the Year | Commonwealth Business Council | 2015 |
| UTech Trailblazer Award | University of Technology, Jamaica | 2015 |
| Georgetown Chamber Young Business Executive Award | Georgetown Chamber of Commerce, Guyana | 2016 |
| ROSA Distinguished Alumni Award | — | 2017 |
| Listed: 51 Most Impactful Smart Cities Leaders Globally | Smart Cities Council | 2019 |
| **WE Empower UN SDG Challenge Award** | Vital Voices / Arizona State University | 2020 |

The **WE Empower award** — a global competition — recognised her work bridging geospatial science, entrepreneurship, and climate resilience for Caribbean communities. Six global finalists were selected. She was one of them.

She represents Fugro at the **UN Committee of Experts on Global Geospatial Information Management (UN-GGIM)**. She is a co-chair of the **UN-GGIM Americas Private Sector Network**. She is a member of the **World Geospatial Industry Council**. She hosts the *Mapping the Conversations* podcast and has written a column for *GIM International*.

She also wrote two books: *Every Day is Day One: Maintaining the Startup Culture and Mindset* (2021) and *Hills and Valleys: Poems of Resilience* (2023).

---

### 8. The Jamaican Foundation

Her first degree is from UWI. Her company was founded in Kingston. Her work is explicitly about the islands where Jamaican students live — the coastlines, the communities, the flood zones, the elevation maps that determine whose home is safe.

She built GeoTechVision from a technology incubator at the University of Technology Jamaica. She spoke at a UWI conference in Trinidad. She sits on UN committees while remaining rooted in the Caribbean.

Her doctoral research asks: why do some small island governments fail to use the geospatial science available to them? Her answer — multi-level leadership, governance structures, institutional coordination — is a question that Jamaican students are positioned to understand directly. They live in the context she is trying to fix.

---

### Discussion Questions

1. LiDAR achieves centimetre-level elevation accuracy by measuring the round-trip travel time of laser pulses. Calculate the travel time of a single pulse to a target 1,000 metres below an aircraft and back. (Use c = 3 × 10⁸ m/s.) What engineering challenges does this imply for the timing system, given that the aircraft fires over a million pulses per second?

2. Dr. Grant's doctoral research found that geospatial governance — not technology access — is the primary barrier to effective climate adaptation in small island states. What does this suggest about the relationship between scientific tools and political institutions? Can a scientist who only understands the technology part fully serve communities that need both?

3. Jamaica Flying Labs deployed 26 drone pilots within hours of a disaster, coordinating nearly 30 organisations, to map a zone that ground teams could not reach. Design the coordination protocol for such a deployment — who communicates with whom, in what order, and how is the resulting data delivered to the people who need it? What could go wrong?

4. The difference between ±10 metres of elevation accuracy and ±10 centimetres is a factor of 100. For Jamaica's coastal zone, describe a specific scenario where that difference determines whether a community is correctly identified as at-risk or incorrectly identified as safe. What are the ethical consequences of the lower-accuracy figure being used for policy decisions?

---

*Standards: NSF Earth Sciences & Environmental Science Grade 10–12, UWI Geomatics / GEOG3402, AP Environmental Science. Luminous Works LLC / JUICY Academy WIS-09.*
