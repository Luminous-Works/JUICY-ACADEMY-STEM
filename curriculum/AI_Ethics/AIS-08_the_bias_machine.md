# AIS-08: Error Rate 34.7%

**Subtitle:** Artificial Intelligence — Lesson 8
**Module:** AI Ethics
**Duration:** 90 minutes
**Level:** Grade 10–University

---

## Opening: The White Mask

Joy Buolamwini was a graduate student at the MIT Media Lab. She was working with facial analysis software — the kind of computer vision system that detects faces, measures features, infers attributes. The software would not detect her face.

She tried different lighting. She tried different angles. She adjusted the distance from the camera. The software continued to fail. It was not broken. It worked fine for her white colleagues. The machine looked at Joy Buolamwini's dark-skinned face and found nothing.

She obtained a white theatrical mask. She held it in front of her face. The software detected a face immediately.

The machine could see the mask. It could not see her.

This is not a metaphor. This happened. The system that was supposed to detect human faces required Joy Buolamwini to erase her own face and replace it with a white one before it would acknowledge her presence.

Everything that follows in this lesson flows from that image. The white mask is not an anecdote about one malfunctioning system. It is a precise illustration of what happens when the people who build technology do not consider — or do not care — whether their systems will work for everyone. And it is the origin of research that changed the facial recognition industry.

---

## Part I: Who Is Joy Buolamwini?

Joy Buolamwini was born in Canada to Ghanaian parents. She grew up partly in Mississippi and partly in Ghana, holding the lived experience of both continents and neither country fully claiming her. She studied computer science and became one of the most technically accomplished students in her field.

She attended MIT as a graduate researcher at the Media Lab, where she was surrounded by cutting-edge technology and the culture of innovation that MIT embodies. She earned a Rhodes Scholarship to Oxford University — one of the most competitive academic honors in the world. She is not a critic of technology from the outside. She is a technologist. She built systems. She understands them from the inside.

But she also had a face that the machines could not see.

The dissonance between those two facts — high technical achievement, systematic technological exclusion — became the foundation of her work. She did not simply complain that the software was broken. She designed a rigorous scientific study to document exactly how broken it was, and for whom, and why.

She founded the **Algorithmic Justice League** in 2016, an organization at the intersection of art, technology, and research whose mission is to develop tools and methods to illuminate and challenge algorithmic bias. Its tagline: *Increasing the accountability of AI.*

Her 2019 TED Talk, "How I'm Fighting Bias in Algorithms," has been viewed more than five million times. She has testified before the United States Congress. She has testified before European Parliament. She has met with government and corporate leaders across multiple continents. She was named one of *TIME* magazine's 100 Most Influential People in the world.

She is, by any objective measure, among the most consequential figures in the contemporary debate about artificial intelligence. She is also a Black woman from the African diaspora who had to wear a white mask to exist in the systems her peers built.

---

## Part II: The Gender Shades Study

### The Research Question

In 2018, Joy Buolamwini and Timnit Gebru — then a researcher at Microsoft Research, later a founding member of Google's Ethical AI team before being controversially fired in 2020 — published a research paper called **"Gender Shades: Intersectional Accuracy Disparities in Commercial Gender Classification."**

The study asked a deceptively simple question: how accurately do commercial facial recognition and gender classification systems perform, and does their accuracy vary across different demographic groups?

To answer this question, they needed a dataset. They constructed one: a benchmark dataset called the **Pilot Parliaments Benchmark (PPB)**, consisting of 1,270 faces drawn from the parliaments of three African countries (Rwanda, Senegal, and South Africa) and three Nordic countries (Finland, Iceland, and Sweden). They chose these countries deliberately — the African parliaments provided a significant proportion of dark-skinned faces (particularly dark-skinned women, a group almost entirely absent from the existing AI research benchmarks), while the Nordic parliaments provided lighter-skinned faces.

Each face in the dataset was labeled by at least two human raters for gender (male or female — this is a limitation of the study's binary framing, which the authors acknowledged) and skin tone using the **Fitzpatrick scale**, a dermatological classification system that rates skin tone from 1 (very light) to 6 (very dark). For the study, this was simplified into two categories: lighter-skinned (Fitzpatrick 1–3) and darker-skinned (Fitzpatrick 4–6).

They then tested three commercial gender classification APIs from major technology companies: IBM Watson Visual Recognition, Microsoft Azure Cognitive Services, and a system from Face++, a Chinese AI company.

### The Results

The results were not marginal differences. They were dramatic. Here is what they found:

| Demographic Group | Error Rate |
|---|---|
| Lighter-skinned men | 0.8% |
| Lighter-skinned women | 6.6% |
| Darker-skinned men | 12.0% |
| **Darker-skinned women** | **34.7%** |

To understand what these numbers mean: a system that misclassifies lighter-skinned men 0.8% of the time gets it wrong for darker-skinned women 43 times more often.

Imagine a standardized test in which white male students got 1 question wrong out of 100, while Black female students got 35 questions wrong out of 100. That is not a test that measures ability. That is a test that measures something else entirely.

The 34.7% error rate for darker-skinned women was the headline finding — and it became the most-cited figure from the study because it is the number that makes the abstract problem concrete. The machine was wrong about a third of the time when looking at a dark-skinned woman's face. You would do better guessing randomly.

---

## Part III: Why This Happens — The Mathematics of Biased Training

### What Machine Learning Actually Does

To understand why these disparities exist, you need to understand, at a foundational level, what machine learning systems do.

A machine learning model does not have rules programmed into it in the traditional sense. A traditional face detection program might say: "if the contrast between pixel group A and pixel group B exceeds threshold X, and the ratio of distances Y and Z falls within range W, then a face is present." Someone had to write those rules.

A machine learning model is different. You show it thousands — or millions — of labeled examples. Each example is a data point with an input (an image) and an output (the correct label: "face present" or "face absent," "male" or "female"). The model adjusts its internal parameters iteratively until it can accurately reproduce the correct output from the input for the examples in the training set. The "rules" emerge from the data. No human explicitly wrote them.

This is powerful. It is also the source of the bias problem.

### The Training Distribution Problem

Let *P(x)* represent the probability distribution of images in the training dataset — the mathematical description of what kinds of images appear, and how often.

If the training dataset contains images drawn primarily from one demographic group, then *P(x)* heavily weights that group. The model becomes very good at accurately classifying members of that group, because it has seen many examples of them. It becomes less good — potentially much less good — at classifying members of groups that are underrepresented in the training data.

This is not a mysterious phenomenon. It is a direct mathematical consequence of how these systems learn. A model cannot generalize well to data points it has rarely seen during training.

Here is a simplified numerical illustration:

Suppose you are training a face detection system. Your training dataset contains:
- 90,000 images of lighter-skinned faces
- 10,000 images of darker-skinned faces

The model achieves very high overall accuracy — say, 97%. But that overall accuracy figure is a weighted average. If the model achieves 98% accuracy on lighter-skinned faces (which make up 90% of the training data) and only 70% accuracy on darker-skinned faces (which make up 10%), the overall weighted accuracy is:

*(0.90 × 0.98) + (0.10 × 0.70) = 0.882 + 0.070 = 0.952*

A reported overall accuracy of 95.2% sounds excellent. But the disaggregated accuracy tells a completely different story: the system fails 30% of the time on darker-skinned faces.

This is why overall accuracy metrics are inadequate and potentially misleading. They can hide catastrophic performance on subgroups. The Gender Shades study was important not just for what it found, but for the methodological argument it made: **you must evaluate AI systems on disaggregated subgroups, not just population-level averages.**

### Where Do Biased Training Datasets Come From?

This is the question that connects the technical problem to the social and historical problem.

Facial recognition and computer vision datasets are built from images. Images come from somewhere. Many of the foundational facial recognition datasets were built from:

- Photo archives of corporate employees (overwhelmingly white and male)
- Publicly available mugshot databases (disproportionately dark-skinned, due to the well-documented racial disparities in U.S. arrest rates)
- Scraped internet photos (where the representation of who is photographed, celebrated, and publicly visible reflects the demographics of who holds power and wealth in the societies that built the internet)
- Curated research datasets compiled by academic researchers working at institutions with low demographic diversity

The skew in training data is not arbitrary. It reflects the historical patterns of who was systematically included and excluded from positions where photographs are taken and archived. The technology does not create the bias. It inherits and encodes it.

And once encoded in a deployed system, the bias is invisible. No one wrote a rule that said "be less accurate for dark-skinned women." No one chose this outcome. It emerged from the training data, which reflected the world as it was built — not as it should be.

---

## Part IV: The Consequences Are Not Abstract

### Robert Williams, Detroit, January 2020

Robert Williams is a Black man who lives in suburban Detroit with his wife and two daughters. On January 9, 2020, Detroit police officers came to his home and arrested him in front of his family.

The arrest was based on a facial recognition match. Detroit police had used an AI facial recognition system to compare images from a surveillance camera outside a watch store with a Michigan database of driver's license photos. The system returned a match: Robert Williams.

Williams was taken to a Detroit detention facility. He was held for approximately 30 hours. During that time, a detective showed him the surveillance footage and the driver's license photo the system had matched. Williams looked at the image from the surveillance camera and said: *"That's not me."* He reportedly held his driver's license photograph next to the surveillance image to demonstrate the obvious visual differences.

The charges against Williams were eventually dropped. But not before he had spent more than a day in jail, separated from his family, for a crime he did not commit, based on a machine's incorrect identification of his face.

The Williams case was the first documented case of a wrongful arrest based on facial recognition in the United States. It was not the last.

### Michael Oliver, Detroit, 2020

In the same city, in the same year, a similar case occurred. Michael Oliver, a Black man, was wrongfully arrested based on a facial recognition match for a crime he did not commit. Oliver maintained his innocence throughout. The charges were eventually dropped.

Two cases in the same city. The same year. Both Black men. Both involving facial recognition misidentification. Detroit's police department was using a facial recognition system with documented accuracy disparities along racial lines.

### Nijeer Parks, New Jersey, 2019

Nijeer Parks was wrongfully arrested in New Jersey based on a facial recognition match linking him to a shoplifting incident and car crash. He spent 10 days in jail before charges were dropped. Parks, also a Black man, had to prove his innocence against the presumptive authority of an AI system's output.

Parks later filed a lawsuit. In 2024, a New Jersey federal jury awarded him $1.75 million in damages — one of the first substantial legal verdicts against law enforcement's use of facial recognition technology.

### The Pattern

In all three cases: the wrongfully arrested person was Black. In all three cases, the match was wrong. In all three cases, the person was arrested anyway — because law enforcement treated the output of the facial recognition system as sufficient probable cause for arrest.

This is not a coincidence. This is the real-world consequence of deploying a technology with a 34.7% error rate on dark-skinned faces into a law enforcement context where the output of the system is treated as reliable evidence.

The people who built these systems did not intend to arrest innocent Black men. But intention is not the relevant variable when measuring consequences. The system was inaccurate. The inaccuracy was concentrated in a specific demographic group. That group was targeted by law enforcement. Innocent people were jailed.

---

## Part V: The COMPAS Algorithm and Criminal Justice

### What COMPAS Does

COMPAS — an acronym for Correctional Offender Management Profiling for Alternative Sanctions — is a risk assessment algorithm developed by a company called Northpointe (later renamed Equivant). It is used by courts in multiple U.S. states to assess the likelihood that a criminal defendant will reoffend — a measure called **recidivism risk**.

The score produced by COMPAS is used by judges when making decisions about bail, sentencing, and parole. A defendant assessed as "high risk" may be held without bail, sentenced more harshly, or denied parole. A defendant assessed as "low risk" may receive more lenient treatment.

The input to COMPAS is a questionnaire administered to defendants that includes information about their criminal history, age, employment status, residential stability, and crucially — questions about the criminal history of family members and friends and neighborhood characteristics.

The output is a score from 1 to 10.

### The ProPublica Investigation

In 2016, investigative journalism organization ProPublica published an analysis of COMPAS scores for more than 7,000 defendants in Broward County, Florida, comparing COMPAS scores with actual recidivism data over a two-year follow-up period.

Their findings:

- **Black defendants were nearly twice as likely as white defendants to be falsely flagged as high risk** — that is, labeled "high risk" but not actually reoffending within two years.
- **White defendants were nearly twice as likely as Black defendants to be falsely labeled low risk** — that is, labeled "low risk" but actually going on to reoffend.

In concrete numbers from their dataset: of defendants who did not reoffend (meaning the high-risk label was false), 44.9% of Black defendants had been labeled high risk, compared to 23.5% of white defendants. The false positive rate — the rate at which the algorithm incorrectly labeled someone as likely to reoffend — was nearly double for Black defendants.

Northpointe disputed ProPublica's analysis. They argued that COMPAS is "equally accurate" for Black and white defendants in the sense that it has similar overall predictive accuracy. This dispute has generated an enormous academic literature, because it turns out that you cannot simultaneously satisfy all of the mathematical definitions of "fairness" that can be applied to a classification system. This is known as the **impossibility of fairness**: multiple reasonable definitions of algorithmic fairness are mathematically incompatible with each other.

But the key finding from ProPublica does not require choosing between competing definitions of fairness. It requires only this: a tool that produces a false high-risk label at nearly double the rate for Black defendants compared to white defendants is producing systematically different outcomes for people based on race. Whatever you call that technically, its effect in a courtroom is that Black defendants face a higher risk of being incorrectly deemed dangerous.

### Why COMPAS Produces Racially Disparate Outputs

COMPAS does not include race as an explicit input variable. But several of the variables it does use are proxies for race in the United States:

- **Neighborhood characteristics** correlate with race because of residential segregation that was legally enforced for decades and continues to shape where people live.
- **Family and friend criminal history** correlates with race because of the well-documented racial disparities in arrest, prosecution, and incarceration — disparities that predate COMPAS and are embedded in the historical data the system was trained on.
- **Unemployment and residential instability** correlate with race because of structural inequalities in employment, housing, and economic opportunity.

When you train a model on historical data from a society with racial inequality embedded in every one of these dimensions, the model learns to treat race-correlated variables as predictors — and the outputs will reflect the racial structure of the input data.

This is not a mystery. It is what machine learning does. The question the COMPAS case forces us to answer is: should systems with these properties be used to inform decisions that affect people's freedom?

---

## Part VI: Ain't I A Woman

In 1851, Sojourner Truth — an abolitionist and former enslaved woman — delivered a speech at the Women's Rights Convention in Akron, Ohio. In it, she challenged those who argued that women were too delicate and intellectually limited for full social and political participation by pointing to her own physical labor, her own suffering, her own humanity:

*"Ain't I a woman? Look at me! Look at my arm! I have ploughed and planted, and gathered into barns, and no man could head me! And ain't I a woman? I could work as much and eat as much as a man — when I could get it — and bear the lash as well! And ain't I a woman?"*

The speech was addressed to people who claimed to believe in women's rights but whose concept of "woman" excluded Black women. Their feminism had a color bar. The systems they built to include women included only some women.

In 2018, Joy Buolamwini performed a spoken word piece called **"AI, Ain't I A Woman?"** She presented it as part of her congressional testimony and as a public artistic work. Over footage of facial recognition systems failing to correctly identify images of prominent Black women — Serena Williams, Michelle Obama, Oprah Winfrey, Sojourner Truth herself — she recited:

*"I am Joy Buolamwini, a poet of code who uses art to illuminate the unseen and to help us imagine a more just world."*

*"Ain't I a woman? Ain't I a woman? Ain't I a woman?"*

The continuity between 1851 and 2018 is not incidental. Sojourner Truth was challenging a system that claimed to represent all women but had been built by and for white women only. Buolamwini was challenging systems that claimed to detect all faces but had been built on data in which dark-skinned faces — and particularly dark-skinned women's faces — were absent or underrepresented.

The underlying structure is the same: systems built with partial data, encoding partial humanity, deployed as if universal. The harm is not random. It falls on the same people it has always fallen on.

---

## Part VII: The Response — What Happened After Gender Shades

### IBM

After the publication of the Gender Shades study, IBM published a blog post announcing improvements to its facial recognition system, claiming reduced error rates across demographic groups. Buolamwini retested the system and found the improvements were real — the error rate for darker-skinned women had been reduced substantially.

This is significant: the publication of rigorous research documenting bias prompted a company to improve its system. Evidence-based advocacy changed corporate behavior. The study worked.

In June 2020, IBM went further. In the wake of nationwide protests following the murder of George Floyd and escalating scrutiny of law enforcement technology, IBM CEO Arvind Krishna announced in a letter to Congress that IBM would:

- Exit the facial recognition business entirely
- No longer offer "general purpose IBM facial recognition or analysis software"
- Call on Congress to pass national legislation governing the use of facial recognition by law enforcement

This was a meaningful corporate decision. IBM did not announce technical improvements. It announced that it was leaving the market because it could not ensure the technology would be used without causing harm.

**What this tells us about the market:** If IBM exited because of public pressure and ethical scrutiny, it means that public pressure and ethical scrutiny can change what technology companies build and sell. The market created the bias; the market can be changed. The mechanism for change is not primarily technical — it is political and social.

### Microsoft

Microsoft followed with its own announcements of algorithmic improvements and, in 2020, announced it would not sell facial recognition technology to police departments until national legislation governing its use had been passed.

### Congressional Testimony

Buolamwini testified before the Senate Subcommittee on Science and Technology in 2019 and before the House Committee on Oversight and Reform in 2020. Her testimony established the Gender Shades findings as part of the formal legislative record of the U.S. Congress. Lawmakers citing her work introduced legislation — including the Algorithmic Accountability Act and specific prohibitions on federal law enforcement use of facial recognition — though as of 2026, comprehensive federal legislation has not been passed.

The gap between the research findings and the legislative response is itself instructive. The evidence of harm was documented in 2018. Wrongful arrests using the technology continued through at least 2020. Congress has heard testimony. Congress has not acted comprehensively.

Why not? The companies developing and selling these systems spend heavily on lobbying. Law enforcement agencies assert operational needs for the technology. The communities most harmed — Black communities, communities with high law enforcement contact — have the least political power to compel action.

---

## Part VIII: The Caribbean Dimension

### What These Error Rates Mean Here

Facial recognition technology is not a problem contained within the borders of the United States. It is a global commercial product being deployed by law enforcement and government agencies worldwide, including in the Caribbean.

Consider what the error rate data means in this context:

The Gender Shades study found error rates of 34.7% on darker-skinned women from commercial systems tested in 2018. Since then, accuracy has improved somewhat — but the principle that accuracy is lower on darker-skinned faces has not been eliminated. Studies published after Gender Shades continue to find disparities, though the magnitudes have shifted.

Caribbean nations have overwhelmingly Black and Afro-Caribbean populations. When facial recognition technology with accuracy disparities across skin tone is deployed by Caribbean law enforcement agencies, the population most likely to be misidentified is the dominant population of those countries — the very people the system is supposed to serve.

This is not a speculative concern.

Jamaica has been investing in surveillance camera networks and law enforcement technology in response to persistent violent crime. The technology being procured comes from commercial vendors — many of the same companies whose systems were tested in the Gender Shades study. The accuracy disparities documented in that study do not evaporate when the technology crosses the Atlantic.

Trinidad and Tobago, Barbados, the Cayman Islands, and other Caribbean territories have similarly been expanding their CCTV and digital surveillance infrastructure. The vendors are often Chinese or American companies whose training data was not constructed with Caribbean populations in mind.

**The specific risk:** A facial recognition system that produces a 34.7% error rate on dark-skinned women will, when deployed to identify suspects in a majority-Black Caribbean population, generate false matches at dramatically higher rates than it generates false matches in the demographic for which it was most extensively trained. The wrongful arrest risk documented in Detroit does not require bad actors to reproduce itself in Kingston or Port-of-Spain. It requires only deployment of the same technology.

**The accountability gap:** In the United States, at least three documented wrongful arrest cases have generated media coverage, advocacy campaigns, lawsuits, and congressional testimony. The infrastructure for accountability — investigative journalism, civil rights litigation, legislative oversight — while imperfect, exists. In smaller Caribbean jurisdictions, this infrastructure is thinner. The probability that a wrongful arrest based on facial recognition misidentification would generate the same accountability response is lower. The harm can occur with less visibility.

**The procurement question:** Caribbean governments procuring this technology should be asking vendors for disaggregated accuracy data across Fitzpatrick skin tone categories. This is not a technically difficult question. It is a question of whether the procurer thinks to ask, and whether the vendor is required to answer. Currently, there is no regulatory framework in most Caribbean nations compelling this disclosure.

---

## Part IX: The Larger Architecture of Algorithmic Bias

The facial recognition case is not unique. It is representative. The same dynamics — biased training data producing biased outputs, deployed in contexts with real-world consequences, with accuracy metrics that obscure disparate impacts on specific subgroups — appear across multiple domains.

**Hiring algorithms:** Resume screening tools trained on historical hiring data will reproduce the historical bias of those hiring decisions. If a company historically hired predominantly white men for technical roles, a model trained on "successful employee" data will learn to rank candidates similar to those historical hires more highly — regardless of actual qualifications.

**Credit scoring and lending:** Algorithmic credit scoring models may use proxy variables — zip code, purchase history, phone brand — that correlate with race due to historical patterns of residential segregation and economic inequality. The model does not know it is using race. It is using variables that carry racial information.

**Medical diagnosis:** AI diagnostic tools trained predominantly on data from white populations have been shown to be less accurate for patients with darker skin tones. A widely used algorithm for measuring blood oxygen saturation using pulse oximetry was found to systematically overestimate oxygen levels in patients with darker skin, a finding published in the *New England Journal of Medicine* in 2022, with implications for COVID-19 treatment decisions.

**Natural language processing:** Language models trained on internet text will replicate the biases present in that text. Word embedding studies have documented that names more commonly associated with Black Americans are more likely to be associated with negative concepts in semantic associations learned from text data.

The common thread is not malice. It is the automated replication, at scale and with the authority of mathematical objectivity, of the inequalities that already structure human society. The algorithm does not introduce bias into a neutral world. It codifies and amplifies the bias that was already there.

---

## What Must Change

**Diverse training data:** Systems must be trained on datasets that represent the populations on which they will be deployed. This requires deliberate data collection, not just mining the most conveniently available data.

**Disaggregated evaluation:** Model accuracy must be evaluated separately for defined demographic subgroups. Overall accuracy metrics are insufficient and can be misleading. This is the core methodological contribution of Gender Shades, and it should be a minimum standard for any deployed AI system.

**Algorithmic auditing:** External, independent auditing of AI systems for bias should be a regulatory requirement before deployment in high-stakes contexts — law enforcement, hiring, lending, healthcare. Vendors should not be the sole evaluators of their own systems.

**Diversity in AI development:** The demographic composition of the teams building these systems matters. Not because diverse teams are incapable of producing biased systems — they can and do. But because teams with greater diversity are more likely to notice problems that affect groups they have direct experience with. Buolamwini found the facial recognition problem because she was in the room when it manifested on her own face. Her colleagues, who were not affected, had not noticed.

**Informed procurement:** Government agencies, particularly in the Caribbean and Global South, procuring AI technology from foreign vendors must demand disaggregated accuracy data and must have the regulatory framework to enforce standards.

**Community input:** The communities most affected by high-stakes AI deployments — criminal justice, immigration enforcement, social service allocation — should have meaningful participation in decisions about whether and how these systems are deployed.

---

## Discussion Questions

These questions do not have predetermined correct answers. They are intended for genuine inquiry.

**1.** Joy Buolamwini had to wear a white mask to be detected by a facial analysis system. The system was built by people who, presumably, did not intend for it to fail on dark-skinned faces. At what level is moral responsibility located when a technology causes harm through neglect — through not considering — rather than through deliberate choice? Who is responsible: the individual engineers who selected the training data? The product managers who decided the product was ready to ship? The companies that sold it to law enforcement? The government agencies that used it without auditing its accuracy?

**2.** The COMPAS algorithm does not use race as an explicit input, yet it produces racially disparate outputs. Courts have used COMPAS scores to make decisions about bail and sentencing. Is it possible to design a "fair" risk assessment algorithm for criminal justice? The mathematical impossibility of fairness literature suggests that satisfying all reasonable definitions of fairness simultaneously is provably impossible. Given this, should risk assessment algorithms be used in criminal justice at all?

**3.** The Gender Shades study was published in 2018. IBM improved its system. Microsoft announced it would not sell to police. IBM eventually exited the market. These changes came from public pressure, journalism, and advocacy — not from regulation. The three documented wrongful arrests in Detroit and New Jersey occurred *after* the Gender Shades study was publicly available. What does the gap between knowledge and action tell us about how technology harm is governed? Who should bear the responsibility for bridging that gap?

**4.** Buolamwini explicitly connected her work to Sojourner Truth's 1851 speech, arguing that the failure of facial recognition systems to recognize Black women is a continuation of historical patterns of exclusion. Is this framing accurate? Does framing algorithmic bias as a continuation of historical injustice change how you think about the obligation to address it? Does it change the urgency?

**5.** The Caribbean deploys facial recognition technology from foreign vendors on majority-Black populations. There is currently no regional regulatory framework requiring vendors to disclose disaggregated accuracy data or requiring government agencies to audit the systems they procure. As a student in this region: what would an adequate response look like from within Caribbean civil society? What institutions would need to act? What technical knowledge would be required? And who, realistically, is positioned to build those institutions?

---

## Supplemental Resources

- Buolamwini, J. and Gebru, T. (2018). "Gender Shades: Intersectional Accuracy Disparities in Commercial Gender Classification." *Proceedings of Machine Learning Research*, Vol. 81. [Open access at gendershades.org]
- Angwin, J., Larson, J., Mattu, S., Kirchner, L. (2016). "Machine Bias." ProPublica. [propublica.org/article/machine-bias-risk-assessments-in-criminal-sentencing]
- Buolamwini, J. (2019). "AI Ain't I A Woman?" [YouTube — Algorithmic Justice League]
- Buolamwini, J. (2023). *Unmasking AI: My Mission to Protect What Is Human in a World of Machines*. Random House.
- Obermeyer, Z., et al. (2019). "Dissecting racial bias in an algorithm used to manage the health of populations." *Science*, 366(6464), 447–453.
- Sjoding, M.W., et al. (2020). "Racial Bias in Pulse Oximetry Measurement." *New England Journal of Medicine*, 383(25), 2477–2478.
- Algorithmic Justice League: ajl.org
- MIT Technology Review — ongoing coverage of algorithmic bias
- *Coded Bias* (Netflix, 2020) — documentary film on Joy Buolamwini and algorithmic bias

---

*Standards: NSF Computer Science & Social Studies Grade 10–12 | UWI COMP2601 / SOCI2401 | AP Computer Science Principles | AP Statistics*
*Luminous Works LLC / JUICY Academy — AIS-08*
*© 2026 Luminous Works LLC. All rights reserved.*
