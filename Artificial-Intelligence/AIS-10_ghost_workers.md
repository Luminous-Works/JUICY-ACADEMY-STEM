# AIS-10: The Humans Behind the Machine

**Artificial Intelligence — Lesson 10**
**Duration:** 90 minutes
**Level:** Grade 10–University

---

## Before You Read

You have almost certainly used an AI tool. You may use one regularly. When you typed a question into a chatbot, or watched a recommendation algorithm surface exactly the video you wanted to watch, or saw a content warning appear before disturbing material, you were interacting with a system that is described as intelligent, automated, and driven by machine learning.

What you were not told — because the companies that build these systems do not advertise it — is that behind many of those outputs, behind the safety filters and the content policies and the data labels that make the AI work, there are human beings doing cognitive labor, often in Africa, Asia, and Latin America, often for less than $2 an hour, often without knowing that the system they are helping to build is being sold as automated.

This lesson is about those people. It is also about the economic structure that makes their invisibility deliberate — and what that structure means for you and for the Caribbean.

---

## Part I: The Mechanical Turk — Then and Now

### The Original Con

In 1770, a Hungarian inventor named Wolfgang von Kempelen unveiled a chess-playing automaton before the court of Empress Maria Theresa of Austria. The device was called the Mechanical Turk. It was a wooden cabinet topped with a life-size mannequin dressed in Ottoman robes, seated behind a chessboard. The cabinet appeared to house complex clockwork machinery. When the Turk played chess, it moved the pieces with the mannequin's arm.

It beat Benjamin Franklin. It beat Napoleon Bonaparte. For 84 years, across Europe and America, it was exhibited as one of the wonders of mechanical ingenuity — proof that a machine could think.

It was not a machine. Inside the cabinet, hidden in a compartment cleverly designed to remain invisible during inspections, was a human chess master. As the machine appeared to calculate, the human calculated. As the machine appeared to move, a system of levers translated the human's movements into the mannequin's arm. The Mechanical Turk was an elaborate performance of automation in which all the actual intelligence was human and all of it was hidden.

Amazon named their crowdsourced labor platform after this device. The name is **Amazon Mechanical Turk**, and it has been in continuous operation since 2005.

The naming is not a coincidence. It is a confession.

### Amazon Mechanical Turk — The Platform

Amazon Mechanical Turk (commonly abbreviated MTurk) is a marketplace in which companies post small tasks — called **Human Intelligence Tasks (HITs)** — that they need humans to complete. Workers, called Turkers, browse available tasks, complete them, and are paid per task. The platform has been used for everything from transcribing audio files to labeling images to evaluating search results to categorizing customer reviews.

The central premise of the platform — and the reason it bears the name it does — is that the companies posting tasks want the human intelligence that completes the work to be invisible. The results of Turker labor feed into systems that are presented to end users as automated. The human who classified the sentiment of a sentence never appears in the product. The human who identified the stop signs in an image to train a self-driving car dataset is not credited or acknowledged. The person who flagged a piece of content as violating terms of service leaves no trace in the final output.

The task structures reflect this design. Tasks are broken into the smallest possible units to prevent any single worker from developing a full picture of what they are building. A Turker labeling images for a facial recognition system sees one image at a time. They do not know the system's name, its purpose, or the company that will deploy it. They are presented with a task: does this image contain a face? Yes or no. $0.03 per image.

The wages on Mechanical Turk are not regulated by minimum wage laws in the United States because workers are classified as independent contractors, not employees. Studies have consistently found that median hourly earnings on the platform range from $1 to $5 per hour, with many tasks paying effective wages well below $1 per hour when setup and search time are included.

---

## Part II: What Ghost Work Actually Is

### The Taxonomy of Hidden Labor

The term **ghost work** was coined by Microsoft Research sociologist Mary Gray and her colleague Siddharth Suri in their 2019 book of the same name. It describes a category of labor that is essential to AI systems, performed by identifiable human beings, and systematically made invisible by the platforms and companies that depend on it.

Ghost work falls into several categories, each of which deserves examination:

**Data labeling** is the practice of annotating data so that a machine learning model can learn from it. When a self-driving car system needs to learn to recognize pedestrians, engineers gather thousands of images of street scenes and hire people to draw bounding boxes around every person in every image, sometimes annotating posture, direction, and distance. When a medical imaging AI needs to learn to identify tumors, radiologists or trained labelers annotate thousands of medical scans, marking the locations and characteristics of anomalies.

This is not marginal work. It is foundational. A machine learning model without labeled training data is not a model — it is a mathematical structure with nothing to learn from. The quality of the labeling directly determines the quality of the model. The difference between a self-driving system that can reliably identify a child running into the street and one that cannot is, in significant part, the difference between well-labeled training data and poorly labeled training data. The people who produce that data are doing safety-critical work for wages that are among the lowest in the digital economy.

**Content moderation** is the review of user-generated content to determine whether it violates platform policies. When a video platform removes a piece of child sexual abuse material before most users see it, or when a social media platform removes a graphic video of a beheading within minutes of its upload, that often happens because a human being reviewed the content and flagged it.

The scale of this work is staggering. Meta (Facebook and Instagram) processes billions of pieces of user content daily. The content moderation workforce that supports this — reviewing reports, evaluating borderline cases, and labeling content to train the automated systems — is largely outsourced to third-party companies operating in the Global South. These workers review violent deaths, child sexual abuse material, torture, self-harm, and extremist propaganda. Repeatedly. For hours. For wages that would not meet the poverty threshold in any wealthy country.

**Audio transcription** involves converting recorded speech to text, a foundational task for training speech recognition systems. Transcription workers hear audio recordings — which may include conversations recorded without the speakers' knowledge, sensitive medical information, legal proceedings, or personal communications — and type what they hear. This work is done at scale by workers who typically have no legal protections regarding the confidential material they process.

**Search result evaluation** and **sentiment classification** involve human review of search engine outputs and text, respectively, to provide training signal for ranking algorithms and language models. A search evaluator might be asked: is this search result relevant to this query? A sentiment classifier might be asked: is this sentence expressing positive, negative, or neutral emotion? These tasks appear simple but require genuine contextual understanding — understanding that machines are not yet capable of providing reliably, which is why humans are doing it.

**Prompt response rating** — sometimes called reinforcement learning from human feedback (RLHF) — is a newer and increasingly critical form of ghost work. When a large language model is trained, one crucial phase involves having human workers rate the quality and helpfulness of the model's outputs. These ratings are used to fine-tune the model to produce better outputs. The humans doing the rating are providing the signal that shapes what the AI says and how it says it. Their preferences, biases, cultural contexts, and working conditions all influence the model's outputs. They are rarely acknowledged in the model cards or press releases.

---

## Part III: The Kenyan Investigation

### The TIME Magazine Report, January 2023

In January 2023, journalist Billy Perrigo published an investigation in TIME Magazine that documented in precise detail what ghost work looks like in practice for the people doing it.

The company at the center of the investigation was **Sama**, a Nairobi-based outsourcing company that describes itself as a social enterprise providing ethical work opportunities to people in the Global South. Sama had contracted with OpenAI — the company that makes ChatGPT, one of the most widely used AI tools in the world — to provide data labeling services, including a specific and deeply harmful category: labeling toxic content.

For ChatGPT to have a safety filter — for the tool to decline to produce instructions for making weapons or to generate child sexual abuse material when prompted — someone had to train that filter. Training the filter required showing a model examples of harmful content and labeling them as harmful. The examples included written descriptions of child sexual abuse, graphic violence, torture, bestiality, and extremist content of all types.

Sama's workers in Nairobi did this work. They were paid between $1.32 and $2.00 per hour. Their employment contracts, according to Perrigo's reporting, prevented them from discussing their work publicly under threat of termination.

They were not given adequate mental health support. The investigation found that workers were offered approximately 30 minutes of counseling per week — half an hour, for a job that involved reviewing written descriptions of child sexual abuse for multiple hours per day. Multiple workers reported experiencing post-traumatic stress symptoms: nightmares, intrusive thoughts, inability to eat, emotional numbness. Some reported that they could no longer interact normally with their own children.

They were not told, when they took the job, what the content would involve. The contract described data annotation work. The actual work was reviewing some of the most psychologically harmful content that exists.

When workers spoke to Perrigo for his investigation, they did so at significant personal and professional risk. Several of them were subsequently let go by Sama after the story was published. The company stated that the timing was unrelated to the investigation.

### The Arithmetic of Exploitation

In January 2023, the same month as Perrigo's investigation, Sam Altman's net worth was estimated at approximately $2 billion.

The Kenyan content moderator making $1.50 per hour would need to work without stopping — no breaks, no sleep, no weekends — for approximately 152 years to earn $2 billion.

This comparison is not offered as a rhetorical flourish. It is a structural fact about how value flows through the AI economy. The Kenyan worker's labor is a direct input to the product that generates the revenue that produces the wealth. The product is not possible without the labor. The labor is valued, by the market, at $1.50 per hour. The company is valued, by the market, at tens of billions of dollars.

The mechanism that produces this gap is not an accident and it is not a market imperfection. It is a design feature. The labor is classified as contracting work to avoid employment law protections. It is located in countries where wages are lower to minimize costs. It is structured as small, disconnected tasks to prevent workers from organizing around shared interests. It is rendered invisible in the final product to prevent consumers from making purchasing decisions based on how the product was made.

### What Sama Says

Sama's defense of its practices is worth understanding, because it is representative of the defenses offered by all companies operating in this space.

Sama describes itself as a social impact company providing stable employment and skills training to people in low-income communities. In the context of Nairobi's labor market, the wages it pays, though low by any international standard, are above what many alternative employment options offer. The company argues that it is improving conditions for its workers relative to the baseline.

This argument has a name: **comparative advantage under structural inequality**. It is not false that a $1.50/hour wage in Nairobi is better than no wage in Nairobi. It is also not a defense of $1.50/hour as adequate compensation for safety-critical, psychologically damaging work that makes possible a product worth tens of billions of dollars.

The argument that exploitation is acceptable because worse exploitation exists is not an argument that the exploitation is just. It is an argument about the local baseline. The baseline itself is the problem.

---

## Part IV: The Colonial Extraction Structure

### The Uranium Parallel

In AIS-02, this curriculum examined the Congo's provision of uranium for the Manhattan Project — the material from which the atomic bombs dropped on Hiroshima and Nagasaki were made. The workers who mined that uranium, under Belgian colonial administration, did so at enormous physical cost and for wages that bore no relationship to the value of what they were extracting. The value flowed outward. The cost stayed.

The structure of AI ghost work is the same structure.

The Congo provided the physical material that made nuclear weapons possible. Kenya, the Philippines, India, and Venezuela provide the cognitive material that makes AI systems possible. In both cases, the resource is extracted from communities in the Global South. In both cases, the extraction is made possible by wage differentials that reflect historical economic inequalities, not the intrinsic value of the labor. In both cases, the product is sold — at enormous profit — by entities in wealthy countries to wealthy-country markets. In both cases, the communities that provide the resource receive none of the profit.

The difference is that digital cognitive labor leaves less visible wreckage than uranium mines. The wreckage it leaves is psychological. It is harder to photograph, harder to litigate, harder to regulate. This makes it easier to ignore.

### The Structural Irony

AI is marketed, consistently and aggressively, as a replacement for human labor. The dominant narrative about AI in economic policy, in business media, and in the technology industry's public communications is that AI will automate away repetitive and low-skill tasks, freeing humans for higher-value work.

The complete structural irony is this: **the AI only works because of human labor that costs less than any alternative**.

The automation is not replacing human labor. The automation is a consumer-facing interface that hides human labor from the people who pay for the product. The product appears automated. Behind the appearance, there are human beings doing the annotation, the moderation, the evaluation, the rating that make the appearance of automation possible. Those humans are paid as little as the market will allow.

The "automation" is a performance, in the same way that the Mechanical Turk's chess-playing was a performance. The intelligence is inside the cabinet. The cabinet is designed to prevent you from knowing that.

---

## Part V: Ghost Work and Data Dignity

### Mary Gray and Siddharth Suri's "Ghost Work"

In 2019, Microsoft Research sociologist Mary Gray and her colleague Siddharth Suri published **"Ghost Work: How to Stop Silicon Valley from Building a New Global Underclass."** The book is the first systematic documentation of the ghost work economy.

Gray and Suri conducted interviews with hundreds of ghost workers in the United States and India, tracking their working conditions, earnings, and experiences over multiple years. Their findings contradicted several of the dominant narratives about this work.

First: ghost workers are not a temporary underclass waiting to be displaced by better automation. They are a permanent and growing workforce, because the tasks they perform are not easily automated. Tasks that require cultural context, nuanced judgment, language comprehension, or interpretation of ambiguous content are exactly the tasks where automated systems fail most badly — and exactly the tasks that are most critical for AI safety. The ghost work economy grows as AI capabilities grow, not despite them.

Second: ghost workers are not predominantly uneducated. Many of the workers Gray and Suri interviewed had university degrees or technical training. They were doing ghost work because local labor markets did not provide equivalent-wage alternatives for their skills, not because they lacked skills.

Third: the platform structures actively prevent workers from building skills or careers. Task fragmentation ensures that workers cannot develop expertise in any particular domain. The lack of worker profiles or reputations across tasks prevents skill accumulation from being rewarded. Workers are trapped in the low-wage segment of the digital economy by the design of the platforms themselves.

### Data Dignity

Against this background, several researchers and economists have proposed the concept of **data dignity**: the idea that individuals and communities whose data and labor power AI systems should be compensated for that contribution.

The core argument is straightforward. The training data that makes a large language model work was produced by human beings — through their writing, their conversations, their creative work, their annotations. The model's value derives from that data. Under current commercial structures, none of that value flows back to the people who produced the data. Data dignity frameworks propose mechanisms to change this: micropayments for data contribution, data cooperatives that negotiate collectively on behalf of their members, or regulatory requirements that AI companies compensate the workers and data contributors who make their products possible.

Several specific proposals have been developed:

**Data unions** are collective organizations that aggregate the data of their members and negotiate licensing terms with AI companies. In this model, a community of speakers of Haitian Creole could form a data union, pool their linguistic data, and negotiate payment from companies that want to train models on Haitian Creole text. The community would receive the value their data generates rather than having it scraped for free.

**Compensated contribution models** involve AI companies paying individuals directly for labeled data, creative work, or other contributions used in training. This is a more direct form of data dignity and has been experimented with by several smaller AI companies, though not yet adopted at scale by the major players.

**Labor law extension** would classify ghost work platforms as employers, requiring them to provide minimum wage protections, employment benefits, and safety standards to workers. This is the most straightforward remedy and faces the most significant political resistance, because it would substantially increase the cost of ghost work and thus reduce the cost advantage that makes offshoring to the Global South attractive.

---

## Part VI: The Caribbean Dimension

### Jamaica and the BPO Industry

Jamaica has had a **business process outsourcing (BPO)** industry since the early 2000s. BPO refers to the practice of companies in wealthy countries outsourcing back-office and customer-facing work — call centers, data entry, customer support, claims processing — to lower-wage markets. Jamaica's BPO sector employs tens of thousands of people and has been actively encouraged by successive governments as an employment and economic development strategy.

The work is real. The wages are significantly above the Jamaican median wage, though far below what equivalent work pays in the United States, Canada, or the United Kingdom. Companies like Sutherland Global Services, Teleperformance, and IBEX operate large facilities in Kingston, Montego Bay, and other Jamaican cities.

The ghost work economy that this lesson describes is an extension of the BPO model into AI-specific tasks. Data labeling, content moderation, and AI evaluation work are structurally identical to the kind of work the BPO industry has already established infrastructure to perform in Jamaica and across the Caribbean. As AI companies scale their demand for ghost work, they will look for labor markets with the characteristics the BPO industry already values: English-language capability, educated workforce, favorable time zone for North American clients, and wages substantially below OECD country minimums.

This means the ghost work economy will expand into the Caribbean. The question is not whether this will happen. It is whether it will happen under terms that protect Caribbean workers or under the same terms under which Sama's workers in Nairobi reviewed child sexual abuse material for $1.50 an hour.

### The Absence of Local Regulation

Jamaica, like most Caribbean nations, does not currently have specific regulatory frameworks governing AI labor. The existing labor law framework does not clearly cover ghost work platform arrangements. Workers classified as independent contractors do not have the same protections as employees. There is no requirement that companies disclose the nature of the content that data labeling workers will be asked to review before they take the job.

If ghost work expands into the Caribbean on current terms, Caribbean workers will experience the same conditions as workers in other Global South markets: psychological harm without support, non-disclosure agreements that prevent them from speaking about their working conditions, wages calculated to be competitive with local alternatives rather than proportional to the value being created, and no participation in the economic upside of the products they make possible.

This is not inevitable. It is a policy choice. Countries that develop regulatory frameworks in advance — that require disclosure, minimum wage protections for platform workers, mandatory mental health support for content moderation workers, and transparency about what AI systems ghost workers are building — can shape the terms on which this industry operates in their labor markets.

The window for that policy work is narrow. Once the infrastructure is in place and the industry is established, changing the terms becomes much harder. The history of the BPO industry in Jamaica suggests that the pattern, once established, is durable.

### Who Owns the Regional Linguistic Heritage

There is a secondary dimension that is specific to the Caribbean and to other communities with distinctive languages and cultural heritages.

Jamaican Patois, Haitian Creole, Bajan, Trinidadian Creole, Papiamentu, and other Caribbean languages are, at present, largely uncompensated inputs to AI training data. When web scrapes collect text from Caribbean English media, social media posts in Patois, or Creole-language community forums, they collect the linguistic expression of communities without payment or permission.

This is the same dynamic as the data dignity problem, applied to cultural heritage. The language of a community is not a raw material waiting to be extracted. It is the product of centuries of adaptation, resistance, creativity, and survival. Jamaican Patois carries the history of enslaved people creating a language of their own in conditions of extreme oppression. Haitian Creole is the language in which the only successful slave revolution in human history was organized. These languages are not neutral data points.

When AI companies train multilingual models using scraped Caribbean linguistic data, they are extracting value from those languages and their communities without compensation. The resulting models may then be sold back into Caribbean markets. The direction of value flow is the same as in every other form of extraction: outward.

---

## Vocabulary

**Ghost Work** — essential AI-enabling labor performed by humans but rendered invisible in the final product; term coined by Mary Gray and Siddharth Suri (2019)

**Amazon Mechanical Turk (MTurk)** — Amazon's crowdsourced labor marketplace; named after an 18th-century chess "automaton" that concealed a human player inside

**Human Intelligence Task (HIT)** — the term MTurk uses for individual tasks posted to its platform; the name itself acknowledges that the tasks require human intelligence

**Data Labeling** — the annotation of datasets to create training data for machine learning models; a foundational form of ghost work

**Content Moderation** — human review of user-generated content to enforce platform policies; involves repeated exposure to psychologically harmful material

**RLHF (Reinforcement Learning from Human Feedback)** — a training methodology in which human workers rate AI outputs to provide optimization signal; ghost workers are often central to this process

**Data Dignity** — proposed frameworks for compensating individuals and communities whose data and labor power AI systems

**BPO (Business Process Outsourcing)** — the practice of contracting back-office and customer-facing work to lower-wage markets; the established infrastructure into which AI ghost work is expanding

**Independent Contractor Classification** — the legal categorization used by ghost work platforms to avoid providing workers with employment law protections, minimum wage guarantees, and benefits

**Data Cooperative / Data Union** — a collective organization that aggregates member data and negotiates compensation terms with AI companies on behalf of its members

---

## Primary Sources and Further Reading

- Gray, M. L., & Suri, S. (2019). *Ghost Work: How to Stop Silicon Valley from Building a New Global Underclass.* Houghton Mifflin Harcourt.

- Perrigo, B. (2023, January 18). Exclusive: OpenAI Used Kenyan Workers on Less Than $2 Per Hour to Make ChatGPT Less Toxic. *TIME.*

- Posner, E. A., & Weyl, E. G. (2018). *Radical Markets: Uprooting Capitalism and Democracy for a Just Society.* Princeton University Press. (Chapter on data as labor.)

- Tubaro, P., & Casilli, A. (2019). Micro-work, artificial intelligence and the automotive industry. *Journal of Industrial and Business Economics, 46*(3), 333–345.

- Hao, K. (2019, December 12). Annotating the world: The invisible human workforce behind AI. *MIT Technology Review.*

- Irani, L. (2015). Difference and dependence among digital workers: The case of Amazon Mechanical Turk. *South Atlantic Quarterly, 114*(1), 225–234.

- Jamaican BPO sector employment data: JAMPRO (Jamaica Promotions Corporation) annual reports.

---

## Discussion Questions

These questions require reasoning from evidence, not recitation of facts. There are no correct answers that can be read off the page.

**1. The Naming of Mechanical Turk**
Amazon named its crowdsourced labor platform after an 18th-century device that concealed a human chess master inside a machine to make it appear automated. What does that naming decision tell you about how Amazon understands the platform it built? Is this naming an acknowledgment, a warning, a joke, or something else? What would it mean for a company to be honest — in its marketing, in its product documentation, in its contracts with clients — about the degree to which its "automated" AI products depend on human labor?

**2. The Sama Workers' Choice**
Sama's defense of its labor practices is that the wages it pays, though low by international standards, are above the local baseline in Nairobi and that the alternative for many workers is worse employment or unemployment. Evaluate this defense carefully. At what point does "better than the alternative" stop being a sufficient justification? What additional conditions would need to be met before you would consider the arrangement fair? Does your answer change if you imagine yourself as the worker, the CEO of Sama, the CEO of OpenAI, or a Kenyan government official?

**3. The Invisibility Architecture**
Ghost work is designed to be invisible. Tasks are fragmented. Workers are classified as contractors. Non-disclosure agreements are standard. The products that result are marketed as automated. Map the specific mechanisms that maintain this invisibility. For each mechanism, identify who benefits from the invisibility and who would benefit from transparency. Then consider: if ghost work were visible — if every AI product disclosed the labor conditions of the workers who helped build it — what would change?

**4. Caribbean Policy Design**
You are advising the Jamaican government on how to develop a regulatory framework for AI ghost work before it establishes itself in the Jamaican labor market. What specific regulations would you recommend? What industry interests would oppose each of your recommendations? What international precedents or comparative examples would you draw on? What would you prioritize if you could only get one regulation passed?

**5. Data and Cultural Heritage**
AI companies scrape Caribbean linguistic data — text written in Jamaican Patois, Haitian Creole, Bajan, and other regional languages — to train multilingual models, without compensation to the communities whose linguistic heritage this represents. Design a data dignity framework specifically for Caribbean linguistic heritage. Who would negotiate on behalf of the community? What form would compensation take? Who would administer it? What would prevent the framework from being captured by the same interests it is meant to constrain?

---

## Activities (Choose One Based on Available Time)

**Activity A — Supply Chain Mapping (30 minutes)**
Take a specific AI product you have used (a chatbot, an image generator, a content recommendation system, a spam filter). Map its supply chain as completely as you can: what types of labeled data were likely required to build it? Where was that labeling work likely performed? What are the probable wages for that work? What is the retail price of the product, or the estimated revenue it generates? Construct the value chain from the data labeler to the end user and identify where value is created and where it is captured.

**Activity B — Contract Analysis (45 minutes)**
Obtain and read Amazon Mechanical Turk's current terms of service for workers (publicly available at mturk.com). Identify every clause that limits worker rights, prevents collective action, or disclaims company liability. Then find the comparable document for Amazon's business clients who post tasks. Compare the protections offered to each party. Write a one-page analysis of what the asymmetry in these documents reveals about how MTurk understands its relationship to its workers.

**Activity C — Interview Design and Conduct (60 minutes)**
Design a 10-question interview protocol for a ghost worker, a BPO worker, or someone who has done any form of remote digital piecework. Your questions should be open-ended, non-leading, and designed to elicit honest accounts of their experience. If possible, conduct the interview. If not, roleplay the interview with a partner, with one person drawing on the documented experiences described in the Perrigo investigation and Gray/Suri's research. Write a 500-word reflection on what the interview revealed about the conditions under which AI products are made.

---

*Standards: NSF Social Studies & Computer Science Grade 10–12. UWI SOCI3401 / ECON2201. AP Economics. AP Human Geography. AP Computer Science Principles.*
*Luminous Works LLC / JUICY Academy AIS-10. Version 1.0.*
