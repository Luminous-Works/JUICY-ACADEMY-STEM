# AIS-11: The Eye That Never Closes
## Artificial Intelligence — Lesson 11

**Core concept:** AI-enabled surveillance · The colonial gaze · Mass data collection · Predictive policing · Who watches the watchers  
**Duration:** 90 minutes  
**Curriculum track:** JUICY Academy — Artificial Intelligence  
**Standards:** NSF Social Studies & Computer Science Grade 11–12 · UWI POLS2401 / SOCI3401 · AP Government and Politics · AP Human Geography · AP Computer Science Principles

---

### Opening Statement

> *"The slave is watched so that the master does not have to worry. The citizen is watched so that the state does not have to justify itself."*

The plantation was a surveillance system before it was anything else.

Before it was an economy. Before it was a legal institution. Before it was an ideology. It was, first, a system for tracking the movement, labor, and compliance of human beings whose compliance could not be assumed — because they were enslaved and had every rational reason to resist.

This is not metaphor. This is architecture. The overseer on horseback, the pass system, the slave patrol, the plantation ledger that recorded every body by age, gender, and assessed value — these were data collection mechanisms. They served the same function that Clearview AI, Ring doorbell networks, and predictive policing algorithms serve today: to create a persistent record of where certain people are, what they are doing, and whether they are doing what they are supposed to be doing.

The technology has changed. The architecture has not.

This lesson is about the technology. You already know the architecture. You have been living inside it.

---

### 1. What AI Surveillance Is

Before the specific cases, a definition that will hold through the rest of this lesson.

**AI-enabled surveillance** is the use of machine learning systems to collect, process, and act on data about human beings — their location, their appearance, their social connections, their political activity, their purchasing behavior, their emotional states — at a scale, speed, and persistence that human watchers cannot match.

The distinction from earlier surveillance technologies is threefold:

**Scale.** A CCTV camera records footage. A facial recognition system connected to a database of billions of photographs can identify every face in every frame of that footage, cross-reference each face against criminal records, social media profiles, immigration status, and prior contact with police, and flag persons of interest — automatically, continuously, across thousands of cameras simultaneously. No human operator can do this. The scale is qualitatively different.

**Persistence.** Earlier surveillance was bounded by the cost of storage and human attention. AI surveillance generates a permanent, searchable record. The face that passed a camera in Kingston, Jamaica in 2019 can be located in 2026. The phone that pinged a cell tower near a protest can be placed at that protest years later. The record does not degrade. It accumulates.

**Prediction.** The most consequential use of AI surveillance is not retrospective — catching what someone did — but prospective: predicting what someone is likely to do. Predictive policing, social credit scoring, and terror watchlists are all forms of predictive AI surveillance. They act on who a system calculates you are, not on what you have done. This is a fundamental shift in the relationship between state power and individual behavior.

With that framework in place, let us look at who is building this infrastructure and what it is being used for.

---

### 2. Clearview AI — The Largest Face Database in History

**Clearview AI** is a facial recognition company founded in 2017 by Hoan Ton-That, an Australian software developer, and Richard Schwartz, a former aide to New York Mayor Rudy Giuliani.

Their product is simple in concept and staggering in scope.

Clearview built a database of facial images by systematically scraping photographs from the public internet: Facebook, Instagram, Twitter, LinkedIn, YouTube, news sites, and millions of other sources. By 2020, the database contained approximately **3 billion photographs**. By 2023, that figure had grown to more than **30 billion** — more facial images than there are people on Earth, because most people have multiple photographs online.

None of these photographs were taken with consent for this purpose. You did not agree to have your face added to a law enforcement database when you uploaded a photograph to Instagram in 2014. You had no knowledge this was happening. There was no legal mechanism in the United States at the time that prevented it.

Clearview then sold access to this database to:

- **3,100+ US law enforcement agencies**, including local police departments, the FBI, ICE, the US Army, and Customs and Border Protection
- **Non-US governments**, including governments with documented records of political repression
- **Private businesses**, including retailers using it for loss prevention

The system works by taking a photograph of an unknown face — from a CCTV camera, a phone snapshot, a crime scene — and returning a ranked list of potential matches from the database, along with links to the webpages where those photographs appeared. A police officer can photograph a person on a street and within seconds know their name, employer, social media history, and family connections.

**The accuracy problem.** Facial recognition systems do not perform equally across demographics. The NIST (National Institute of Standards and Technology) evaluation of facial recognition algorithms published in 2019 found that the best-performing algorithms had false positive rates that were **10 to 100 times higher for Black and Asian faces than for white faces**. Clearview's system has not been independently peer-reviewed for demographic accuracy, but independent tests of comparable systems by MIT Media Lab researcher Joy Buolamwini found error rates of up to **35% for dark-skinned women**, compared to less than 1% for light-skinned men.

A false positive in facial recognition is not a minor inconvenience. It means an innocent person's face is returned as a potential match for a crime. In at least three documented cases in the United States between 2019 and 2023 — the cases of Robert Williams, Michael Oliver, and Nijeer Parks — a Black man was wrongfully arrested based on a facial recognition match. All three were innocent. In Williams' case, the detective who made the arrest had no other evidence — only the facial recognition output. Williams was arrested in front of his young daughters.

**Hoan Ton-That's response.** When confronted with privacy concerns, Ton-That has argued that the data Clearview scraped was publicly available, that the company's technology simply does what humans could do manually given enough time, and that the benefits to law enforcement outweigh the privacy costs. He has also argued that Clearview is not responsible for how law enforcement uses the results.

This last argument is the most important to examine carefully. It is the same argument made by weapons manufacturers, chemical companies, and tobacco companies: we made the tool; we are not responsible for its application. The law in the United States has been inconsistent in accepting or rejecting this claim. The European Union's GDPR framework has been more skeptical — Italy, France, Greece, and other EU countries have fined or banned Clearview. Illinois sued Clearview under its Biometric Information Privacy Act. Vermont and California have challenged it.

In most of the world, Clearview operates without meaningful legal constraint.

---

### 3. Palantir Technologies — The Intelligence Infrastructure

**Palantir Technologies** was founded in 2003 by Peter Thiel, Alex Karp, Joe Lonsdale, Nathan Gettings, and Stephen Cohen. Its founding capital came partly from **In-Q-Tel** — the venture capital arm of the Central Intelligence Agency. This is a matter of public record, not conspiracy: In-Q-Tel was created specifically to fund technology companies that serve CIA intelligence needs, and Palantir was one of its early investments.

The company is named after the *palantíri* in J.R.R. Tolkien's *The Lord of the Rings* — the "seeing stones" that allowed those who possessed them to observe distant events and communicate across vast distances. In Tolkien's story, the palantíri were also instruments of corruption: Sauron used one to deceive and manipulate those who looked into it. Whether the founders found this parallel amusing or alarming is not recorded.

**What Palantir actually does.** Palantir's core product is data aggregation and analysis at institutional scale. It ingests data from multiple sources — databases, surveillance systems, financial records, social media, law enforcement records, intelligence feeds — and provides analysts with a unified interface to query, visualise, and act on that data.

For a police department, this means: arrest records, vehicle registration, social media monitoring, phone location data, CCTV footage, gang databases, school records, and parole records — all cross-referenced automatically, generating a "person of interest" profile that synthesizes everything the state knows about an individual in a single dashboard.

Palantir's documented contracts include:

- **US Immigration and Customs Enforcement (ICE):** Palantir built the case management system called **Investigative Case Management (ICM)** that ICE used to manage deportation operations. ICM aggregated data from over 20 databases including the DEA, FBI, SSA, and state driver's license records. A 2019 report by the Center for Constitutional Rights documented that ICM was used to track not only undocumented immigrants but also their US citizen family members and associates.

- **The Los Angeles Police Department (LAPD) and other departments:** Palantir powered predictive policing programs in New Orleans (covertly, without city council knowledge, from 2012-2018) and in multiple other jurisdictions. The New Orleans program was terminated when journalists revealed that residents had never been told it existed.

- **Military targeting:** Palantir's software has been used in US military targeting operations in Afghanistan, Iraq, and other conflict theaters. In 2023, it disclosed contracts with the Israeli Ministry of Defense.

- **COVID-19 response:** In 2020, the UK's NHS awarded Palantir a contract to build a data platform for COVID-19 patient management. The contract was renewed and expanded. Patient data from the NHS — one of the world's largest single-payer health databases — now passes through Palantir infrastructure.

Peter Thiel has described Palantir as a company that helps "Western liberal democracies" compete with authoritarian surveillance states. The irony is that Palantir's technology is functionally the same infrastructure that makes authoritarian surveillance possible — the moral distinction is entirely a function of who is using it and for what purpose, not what the technology does.

Alex Karp, Palantir's CEO, has been more honest about this tension than most technology executives. He has said publicly that Palantir makes moral decisions about which governments and entities it will and will not work with. He has declined to specify those decisions in detail.

---

### 4. Ring / Amazon — The Privatised Surveillance Network

**Ring** is a home security company founded in 2013 and acquired by Amazon in 2018 for approximately $1 billion. Its flagship product is a video doorbell with a camera that records everyone who approaches a front door.

As of 2023, Ring cameras are installed at an estimated **10 million+ homes** in the United States. Amazon's **Neighbors** app allows Ring users to share footage with their local community. Ring also maintains formal data-sharing agreements with **2,161+ US law enforcement agencies** — partnerships through which police departments can request footage from Ring cameras directly through Amazon's law enforcement portal, without obtaining a warrant.

Let that figure settle for a moment.

More than two thousand police departments in the United States have a formal channel to request video footage from private homes — footage that can place any person who walked past any of ten million front doors at any location, at any time, without judicial oversight. A warrant requires a judge to assess probable cause. The Ring partnership portal does not. Ring notifies users when law enforcement requests their footage, but users can consent, and when they do, no warrant is required.

In 2022, Amazon acknowledged that Ring had also provided police with footage in response to emergency requests **eleven times** without even asking the homeowner — in cases Ring deemed to be emergency situations. Amazon did not define the criteria for "emergency."

Internal Amazon documents revealed in 2019 that Amazon employees had accessed customer footage without authorization. The company subsequently implemented additional access controls.

The scale of the Ring network has led the Electronic Frontier Foundation and other civil liberties organizations to describe it as **the largest private surveillance infrastructure in American history** — a distributed CCTV network built at consumer expense, managed by a private corporation, and made available to law enforcement at the corporation's discretion.

In 2022, investigative reporting by Vice documented that Ring footage had been shared with law enforcement in cases involving **immigration enforcement** — specifically, footage of individuals near the US-Mexico border. Amazon does not publish data on the demographics of the neighborhoods where its law enforcement partnerships are concentrated. Independent mapping by civil liberties researchers has suggested a correlation between Ring partnerships and majority-Black and Latino neighborhoods.

---

### 5. NSA / PRISM — The Architecture of Mass Surveillance

On June 5, 2013, *The Guardian* published a story based on documents provided by former NSA contractor **Edward Snowden**: the United States National Security Agency was collecting the **telephone metadata** of virtually every American — all calls made, all calls received, call duration, and location data — without individualized suspicion, under a secret interpretation of Section 215 of the USA PATRIOT Act.

On June 6, *The Washington Post* published a second story: the NSA was operating a program called **PRISM** that collected internet communications — emails, chats, video, photos, stored data, voice calls, file transfers, video conferencing — directly from the servers of nine major US technology companies: Microsoft, Yahoo, Google, Facebook, PalTalk, YouTube, Skype, AOL, and Apple.

The **GCHQ** — Britain's equivalent of the NSA — had access to PRISM data through an arrangement called **MUSCULAR**.

The NSA's legal defense rested on a distinction that has become one of the most consequential fictions in the history of surveillance law: the distinction between **metadata** and **content**.

The argument: reading the text of your email is "content" collection and requires a warrant. Knowing who you emailed, when, how often, for how long, and from where is "metadata" — transactional data — and can be collected in bulk without a warrant. Metadata does not contain the substance of your communications; therefore, the NSA argued, it is not protected by the Fourth Amendment.

This distinction is not technically defensible.

In 2014, former NSA and CIA director **Michael Hayden** said, without apparent irony: "We kill people based on metadata."

What call metadata actually tells you:

- You called a cancer specialist on Tuesday, a medical attorney on Wednesday, and your children twice on Thursday. Your insurance company would like to know this.
- You called the same phone number seventeen times in the past month, between 11 PM and 2 AM. Your spouse may find this interesting.
- Your phone was near the corner of Martin Luther King Jr. Boulevard and 5th Street every Saturday at the time of a political organizing meeting. A police intelligence unit notes this.
- You called a number associated with a labor organizer, a civil rights attorney, and a journalist three weeks before a strike. Your employer would find this useful.

Metadata, in aggregate, constructs a more complete portrait of a person's life than most content. The NSA knew this. The "metadata vs. content" distinction was a legal fiction designed to enable mass surveillance while maintaining technical compliance with a framework written before the internet existed.

**Edward Snowden** is, as of 2026, living in Moscow, having been granted permanent residency by Russia. He has been charged under the Espionage Act by the United States government. He has said he accepts the consequences of his decision. The reforms enacted after his disclosures — the USA FREEDOM Act of 2015 — ended the bulk telephone metadata program in its original form but left most of the legal architecture of mass surveillance intact.

The question this section should leave you with: **if the most powerful government in human history was secretly collecting the communications data of every one of its citizens — and the public only found out because one person broke the law to tell them — what was the appropriate response?** Did the system work, or did the system fail and one person prevent it from staying hidden?

---

### 6. China's Social Credit System

**What the Western media reports:** China has a totalitarian "social credit system" that gives every citizen a single numerical score based on their behavior, and uses that score to grant or deny access to transportation, housing, education, and employment.

**What is actually true:** China has **multiple separate social credit systems** operated by different local governments, national agencies, and private platforms, none of which are yet unified into a single score for every citizen. The system is more fragmented, more uneven in application, and more complex than the Western media account suggests. This nuance does not make it less concerning. It makes it more important to understand accurately.

The systems that do exist include:

**Corporate credit scoring:** China's National Development and Reform Commission operates a system that rates businesses on regulatory compliance — tax filing, food safety, financial reporting. A company with a poor corporate credit rating faces difficulty accessing government contracts and financing. This is analogous to credit rating agencies in Western countries, with significant differences in enforcement and transparency.

**Individual blacklisting:** China has maintained **blacklists** for individuals who have defaulted on court-ordered debts, failed to comply with court orders, or violated specific regulations. These are real and consequential. In 2018, Chinese courts reported that the **Joint Punishment for Trust-Breaking** program had prevented approximately **17.5 million flights** and **5.5 million high-speed rail trips** from being purchased by people on blacklists. The 6 million flights blocked figure cited in news coverage refers to this system.

**Private scoring platforms:** Ant Financial's **Sesame Credit** (Zhima Credit) is a voluntary opt-in credit score used to determine eligibility for loan products. Some municipalities have offered benefits — priority access to shared bicycles, library deposits — to high-scoring users. This is voluntary participation, comparable to loyalty programs in Western retail, though the data inputs include social connections and purchasing behavior.

**What makes this system significant regardless of the nuance:** The infrastructure — the integration of financial data, location data, government records, social media behavior, and biometric identification into a unified framework for assessing and penalizing individual behavior — represents a model that other governments are studying and partially adopting. **Ecuador, Zimbabwe, Venezuela, Pakistan, and Kenya** have received or implemented Chinese surveillance technology. The export of this model — CCTV networks, facial recognition infrastructure, data integration platforms — is an explicit component of China's **Digital Silk Road** initiative.

The behaviors that have been tracked and penalized in documented cases include: defaulting on loans, traffic violations, smoking in non-smoking areas, spreading "misinformation" online, and criticizing government officials. The last two categories are where the distinction between regulatory compliance and political control dissolves.

---

### 7. Stingrays — The Cell Tower That Isn't There

A **Stingray** (formally called an **IMSI catcher** or **cell-site simulator**) is a device that impersonates a cellular tower. When activated, it broadcasts a signal that nearby phones interpret as the strongest available cell tower and connect to automatically. The Stingray intercepts the connection, collects the phone's unique identifier (its IMSI — International Mobile Subscriber Identity), and in many configurations can also intercept calls and SMS messages.

Because phones connect to the strongest tower automatically, without user action, every phone within range of a Stingray connects to it — not just the phone the police are targeting, but every phone in the area.

In a protest of several hundred people, a Stingray activation collects the phone identifiers of every participant. It does not require any participant to have made a call or sent a message. It is passive bulk collection triggered by physical presence in a location.

US law enforcement agencies have used Stingrays extensively. The American Civil Liberties Union has documented their use by **75 agencies in 27 states**. This is almost certainly an undercount because the FBI, under the **Harris Corporation** equipment contracts, required local law enforcement agencies that received Stingrays to sign non-disclosure agreements preventing them from disclosing their use — even to defense attorneys, even to judges, even when the evidence in a criminal case was derived from Stingray data.

In **multiple documented cases**, prosecutors dropped charges rather than disclose to courts that Stingray data had been used. The right to know the basis of evidence against you — a foundational principle of due process — was routinely suppressed to protect the secrecy of the surveillance method.

**Warrant requirements** vary by jurisdiction and have been the subject of ongoing litigation. In most jurisdictions, law enforcement does not require a warrant to use a Stingray. The third-party doctrine — which holds that you have no reasonable expectation of privacy in data shared with a third party, including your phone carrier — has been interpreted to mean that cell location data can be collected without judicial authorization. The Supreme Court's 2018 decision in *Carpenter v. United States* limited this doctrine for historical cell location records, but Stingray interception in real time remains in a legal gray area in most states.

**Documented uses at protests include:** the 2014 Ferguson, Missouri protests; the 2016 Dakota Access Pipeline protests at Standing Rock; the 2020 Black Lives Matter protests in multiple cities. ICE has used Stingrays in immigrant communities.

---

### 8. The Colonial Gaze

Now we name it properly.

The plantation was a surveillance system. The overseer on horseback — the man with the whip whose job was to know where every enslaved person was, what they were doing, and whether their output matched the expected rate — was performing the same function as a facial recognition camera. The plantation ledger — which listed every enslaved person by name, age, assessed monetary value, physical description, and labor productivity — was a database. The slave pass system — which required enslaved people traveling off the plantation to carry a written document from the enslaver authorizing the trip — was an access control mechanism.

The **slave patrols** of colonial Virginia and South Carolina, established in the early 1700s, were organized surveillance and enforcement institutions whose explicit purpose was to monitor Black movement and punish resistance. They were funded by colonial governments. They operated at night. They had authority to stop, search, and beat any Black person — enslaved or free — who could not produce documentation. They were the first publicly funded policing institutions in what became the United States.

The transition from slave patrols to municipal police forces after the Civil War was not a break in the architecture. It was a continuity. The **Black Codes** of the 1865-1866 period replaced the pass system with vagrancy laws that criminalized Black unemployment — meaning any Black person who could not produce documentation of employment could be arrested, convicted, and leased as forced labor to plantations. The labor had changed its legal name. The surveillance architecture — who moves, who works, who has papers — had not.

**Stop-and-frisk**, which at its peak in New York City in 2011 produced **685,724 stops**, of which **88% were Black or Latino**, of which **88% were found to have done nothing wrong** — was a direct descendant of this system. The architecture was: Black and Brown people in public space are presumptively suspicious. Documentation, compliance, and explanation are required. The assumption of innocence flows in the opposite direction from where the law says it should flow.

AI surveillance is not an intrusion into a just system. AI surveillance is a technological acceleration of a system that has operated continuously since the 17th century. Clearview AI does not introduce mass facial identification of Black people — it automates it at a scale and speed no human overseer could match. Predictive policing does not introduce the premise that Black neighborhoods are presumptively criminal — it builds that premise into code and calls it an algorithm.

The important word is **continuous**. This is not history. This is not something that happened and was corrected. The plantation surveillance system did not end. It evolved. Every decade it has found new legal forms, new technological expressions, and new institutional homes. The names change. The architecture persists.

The question this section must force is: **when we deploy AI surveillance technology into communities that are already surveilled more heavily, policed more harshly, and trusted less by the legal system — what does the technology do?** It does not correct the bias. It inherits it. It amplifies it. It runs it faster.

---

### 9. Predictive Policing — How Algorithms Encode Bias

**Predictive policing** systems use machine learning to predict where crimes are likely to occur and who is likely to commit them. The most widely deployed systems include **PredPol** (now Geolitica), **ShotSpotter**, and various in-house systems built by companies including Palantir.

The technical argument for predictive policing is intuitive: historical data contains patterns, machine learning can identify patterns, therefore machine learning can predict future crime better than human intuition.

The technical flaw in this argument is equally clear once you understand how supervised learning works.

**Supervised machine learning** trains a model by showing it labeled examples: inputs paired with known correct outputs. The model learns to produce the correct output for novel inputs by generalizing the patterns in the training data. The quality of the model is only as good as the quality of the training data.

For a predictive policing system, the training data is historical arrest records. The model learns: in these neighborhoods, with these demographic characteristics, people are more frequently arrested. Therefore predict future crime in these neighborhoods, with these demographic characteristics.

Here is what the model does not know and cannot know from arrest data alone: **whether arrest rate reflects crime rate, or whether arrest rate reflects policing rate.**

This is not a subtle distinction. The same behavior — carrying a small quantity of marijuana, for example — results in arrest at dramatically different rates depending on the neighborhood where it occurs. A 2013 ACLU report found that Black people were **3.73 times more likely to be arrested for marijuana possession** than white people nationally, despite similar usage rates. In some counties, the disparity was over **10:1**.

The behavior is the same. The arrest rate is different. The arrest rate is different because policing is not uniform — it is concentrated in Black and Brown communities for reasons that are historical, political, and architectural, as described in the previous section.

A machine learning model trained on arrest data learns: Black neighborhoods generate more arrests. Its prediction: Black neighborhoods will generate more arrests. It recommends: send more police to Black neighborhoods. The additional police generate more arrests. The model is updated with the new arrest data. Its confidence that Black neighborhoods generate more crime increases.

This is a **feedback loop** — also called a **positive feedback loop** or **self-fulfilling prophecy** in machine learning contexts. The formal name is **label bias** combined with **distributional shift**: the labels (arrests) do not accurately measure the underlying quantity of interest (crime), and the deployment of the model changes the distribution of the data it then uses to retrain itself.

The mathematics are unambiguous. If $P(\text{arrest} | \text{behavior}, \text{Black neighborhood}) > P(\text{arrest} | \text{behavior}, \text{white neighborhood})$, then a model that predicts "arrest probability" from historical data has learned to encode racial geography as a proxy for criminality. It is not predicting crime. It is predicting policing. And then it is used to increase policing in the places it predicted would have high policing.

The RAND Corporation, the Brennan Center for Justice, and academic researchers at UCLA and Princeton have all published analyses documenting this mechanism. It is not disputed. The companies that sell predictive policing software dispute whether the bias is large enough to outweigh the benefits. The communities that live under these systems dispute whether there are benefits.

---

### 10. The Caribbean Specificity

The Caribbean context for AI surveillance is not hypothetical.

**Jamaica** has one of the highest rates of police killings per capita in the world. The human rights organization Jamaicans for Justice has documented persistent patterns of extrajudicial killings, particularly in inner-city communities in Kingston and Spanish Town. The **State of Emergency** powers used repeatedly in Jamaica — invoked in Zones of Special Operations (ZOSOPs) since 2017 — permit detention without charge for extended periods. These are not historical facts. They are current conditions.

Into this context, the Jamaican government and governments across the Caribbean region have been acquiring and deploying:

- **CCTV networks:** Jamaica's national CCTV network has expanded significantly since 2010, with cameras concentrated in inner-city communities. The National Intelligence Bureau has direct access to the network.
- **Facial recognition technology:** Trinidad and Tobago announced deployment of facial recognition integrated into its CCTV infrastructure in 2021. Jamaica has tested similar systems.
- **Phone surveillance:** IMSI catchers have been used by Caribbean law enforcement. The legal frameworks governing their use are, in most territories, either absent or opaque.

The question this surveillance is supposed to answer is: how do we reduce crime? The question it actually raises is: in a jurisdiction where the state itself commits extrajudicial killings and is rarely held accountable for them, what does it mean to give the state more surveillance capacity?

The technology does not fix the accountability problem. Technology does not create accountability. Institutions create accountability. The Caribbean does not lack surveillance technology. It lacks — in multiple territories — independent judiciaries, civilian oversight of police, functional witness protection, and political will to prosecute security forces for unlawful killings.

Deploying AI-enabled surveillance in a system without accountability does not produce accountable security. It produces a system that can surveil at greater scale, catch more people it wants to catch, and harm more people it decides to harm — with the same absence of consequence for the harm.

This is not an argument against technology in Caribbean policing. It is an argument for sequencing: accountability infrastructure before surveillance infrastructure. Otherwise, the technology serves the existing power structure, not justice.

---

### 11. The Legal Frameworks — And Their Limits

**The Fourth Amendment** to the US Constitution protects against "unreasonable searches and seizures" and requires warrants to be supported by "probable cause." It was written in 1791. It was designed to prevent the government from entering your house without justification.

It was not designed for:
- Government requests to third parties who hold your data
- Passive location tracking via cell towers you connect to automatically
- Facial recognition in public space (you have no privacy expectation in your public face, under current doctrine)
- Metadata collection
- Surveillance of public social media activity

The **third-party doctrine** is the legal principle that governs most digital surveillance: you have no reasonable expectation of privacy in information you have voluntarily shared with a third party. This was established in *Smith v. Maryland* (1979) — a case about telephone numbers dialed, decided before email, smartphones, social media, or internet-connected devices existed.

Under third-party doctrine:
- Your email provider can turn over your emails without a warrant
- Your phone carrier can turn over your location data without a warrant (subject to the partial *Carpenter* exception)
- Your apps can be compelled to turn over their data about you
- Your internet service provider can turn over your browsing history

This is not because Congress decided this was acceptable surveillance. It is because the legal framework was built for an era when sharing data with a business meant writing a letter, and a court decided in 1979 that dialing a number waived privacy. The technological context has changed beyond recognition. The legal principle has not been fundamentally revised.

The **EU's General Data Protection Regulation (GDPR)**, implemented in 2018, represents the most significant regulatory challenge to this framework. It establishes: the right to know what data is collected about you, the right to have that data deleted, the right to object to automated decision-making that significantly affects you, and requires meaningful consent for data collection. Several EU member states have used GDPR to challenge Clearview AI — fining it and ordering it to delete facial recognition profiles of EU citizens.

The GDPR does not apply in Jamaica, Trinidad, Barbados, Guyana, or most of the Caribbean. **Barbados** has a Data Protection Act (2019). **Trinidad and Tobago** has data protection legislation. **Jamaica** passed a Data Protection Act in 2020, but implementation has been slow and enforcement capacity is limited. **Most Caribbean territories have no effective legal framework** governing how the state or private companies can collect, store, and use personal data.

The technology arrives before the law. This is always the pattern. The law is always catching up. In this gap — between the deployment of surveillance technology and the enactment of frameworks governing it — the people who bear the risk are those who already have the least protection from state power.

---

### 12. Discussion Questions

1. **The colonial gaze question:** The slave patrol, stop-and-frisk, and predictive policing have all been described as public safety measures by those who deployed them. At what point does a "public safety measure" become a tool of social control? What criteria would you use to distinguish between them? Does the disproportionate burden on Black and Brown communities change the answer, or is it evidence of the answer?

2. **The Snowden question:** Edward Snowden broke the law to reveal that the US government was engaged in mass surveillance of its own citizens. He was charged with espionage. Should he be considered a criminal or a whistleblower? What, if anything, makes the distinction? What would the world look like today if he had not leaked the documents?

3. **The feedback loop question:** A predictive policing algorithm is shown to have a feedback loop that amplifies existing racial bias in arrest data. The company that builds it says the algorithm is just predicting based on the data it has. The police department says the algorithm is just a tool and officers still make the final call. The city council says crime has fallen in the areas where it's deployed. Who bears responsibility for the harm caused to people incorrectly flagged as likely criminals? Is there a way to build a predictive system that does not inherit historical bias?

4. **The Caribbean sovereignty question:** A Caribbean government is offered a facial recognition system by a Chinese technology company at significantly subsidized cost. The system has been effective at reducing certain types of street crime in urban areas where it has been deployed. The government has documented problems with extrajudicial killings by police and limited civilian oversight of security forces. Should the government accept the offer? What conditions, if any, would make accepting it acceptable? Who should make this decision?

5. **The architecture question:** This lesson argues that AI surveillance is a technological expression of a surveillance architecture that has operated continuously since the plantation era. Someone might respond: that's polemical; modern policing is not the same as slavery. Make the strongest version of both arguments. What evidence would be required to determine which argument is correct? What would it mean for policy if the "continuity" argument is substantially right?

---

*Luminous Works LLC / JUICY Academy AIS-11 · NSF Social Studies & Computer Science Grade 11–12 · UWI POLS2401 / SOCI3401 · AP Government and Politics · AP Human Geography · AP Computer Science Principles*
