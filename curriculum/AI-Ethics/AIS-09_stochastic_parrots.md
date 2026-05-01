# AIS-09: The Paper That Got Her Fired

**Artificial Intelligence — Lesson 9**
**Duration:** 90 minutes
**Level:** Grade 11–University

---

## Before You Read

In 2021, one of the most important papers in the history of AI safety research was published. It warned about risks that are now playing out in the world in real time. The person who led the research was one of the most respected AI scientists at the most powerful AI company on earth.

She was fired for it.

Not quietly pushed out. Fired by email while she was at a conference attending a memorial for a colleague who had just died.

This lesson is about that paper, that firing, and what both of them reveal about how power operates inside the institutions building artificial intelligence — the same institutions whose products you are already using, and whose decisions will shape the next fifty years of your life.

---

## Part I: Who Is Dr. Timnit Gebru?

### The Biography

Timnit Gebru was born in Addis Ababa, Ethiopia. Her family was Tigrinya — from the Tigray region — and when she was a child, the country was under the rule of the Derg, a military junta responsible for widespread political repression and the deaths of hundreds of thousands of Ethiopians. Her family fled. They spent time as refugees before eventually resettling. Gebru came to the United States as a teenager.

This is not incidental context. The experience of displacement, of being rendered stateless, of watching an institution exercise arbitrary power over human life — these are not abstract concepts to someone who lived them. They are the substrate from which a particular kind of intellectual clarity grows.

Gebru went on to earn a Bachelor's degree in Electrical Engineering from Stanford University and then a PhD from MIT, where she worked in the Computer Science and Artificial Intelligence Laboratory (CSAIL). Her doctoral research focused on computer vision — specifically, on using machine learning to analyze satellite imagery and street-level photographs to draw inferences about socioeconomic conditions and demographics. It was rigorous, original work.

After MIT, she joined Apple, then Microsoft Research, and then in 2018 she was hired by Google to co-lead the Ethical AI team within Google Brain — one of the most prestigious AI research organizations in the world. She was, at that point, one of the most prominent Black women in AI research globally. Not because of tokenism. Because of her work.

### Black in AI

In 2017, Gebru co-founded Black in AI with Rediet Abebe, a computer scientist and economist from Ethiopia who later became one of the youngest professors in Harvard's history. Black in AI is a nonprofit organization and community that works to increase the presence and inclusion of Black researchers in artificial intelligence — through workshops, mentorship, research grants, and visibility at major conferences.

The organization exists because the absence it addresses is stark. As of the mid-2020s, Black researchers represent a single-digit percentage of the AI research workforce at major technology companies, and a similarly low percentage of faculty at leading computer science programs. This is not a pipeline problem. It is a structural and historical problem. Black in AI is one attempt to push against it from inside.

Gebru understood that who builds AI determines what AI does. That is not a slogan. It is a technical and empirical claim.

---

## Part II: The Paper

### "On the Dangers of Stochastic Parrots: Can Language Models Be Too Big?"

The paper was submitted to Google's internal review process in late 2020. It was co-authored by Timnit Gebru, Emily M. Bender (a computational linguist at the University of Washington), Angelina McMillan-Major (a PhD student), and Margaret Mitchell (then also at Google, co-lead of the Ethical AI team alongside Gebru). It was eventually published at the ACM FAccT conference in March 2021, without Gebru's and Mitchell's names on it, because both of them had been fired by then.

The paper's title requires unpacking. A **stochastic parrot** is a system that produces statistically plausible sequences of language tokens without any underlying comprehension of what those tokens mean. "Stochastic" means random, or probabilistic. The metaphor is precise: a parrot can reproduce sounds convincingly without understanding them.

The paper's central question is: in the race to build ever-larger language models, are we building increasingly convincing stochastic parrots — and are the costs of that race being ignored?

Here are its core arguments, in full.

---

### Argument 1: The Environmental Cost Is Not Trivial — It Is Catastrophic at Scale

In 2019, Emma Strubell, Ananya Ganesh, and Andrew McCallum published a study at the University of Massachusetts Amherst titled "Energy and Policy Considerations for Deep Learning in NLP." Their central finding: training a single large natural language processing model — specifically a neural architecture search model of the type used to optimize transformer designs — produces an estimated **626,155 pounds of carbon dioxide equivalent emissions**.

That is approximately the equivalent of five cars driven over their entire lifetimes. Or roughly the lifetime carbon emissions of 125 average US citizens for an entire year, in a single training run.

The Stochastic Parrots paper took this finding and extended it. Training does not happen once. It happens repeatedly, across experimental runs, hyperparameter tuning, ablation studies, and incremental improvements. The carbon cost of a single published large language model represents dozens or hundreds of training runs. The infrastructure required — data centers, cooling systems, power grids — runs continuously, not episodically.

The authors noted that this cost is not distributed neutrally. Data centers are frequently located in regions where electricity is cheapest, which often means regions still heavily dependent on fossil fuels. The communities who live near those data centers, or who bear the effects of the carbon emissions, have no voice in the decision to run another training sweep. The executives and researchers who make those decisions typically live elsewhere.

The paper asked a question that seems obvious once asked: before building a model this large, who performed the cost-benefit analysis? Who was in the room? And who bears the cost when the analysis turns out to have been incomplete?

---

### Argument 2: Training Data Amplifies Bias — and Scraping the Internet Is Not Neutral

Large language models are trained on enormous corpora of text — Common Crawl (a scrape of a significant fraction of the public internet), books, Wikipedia, code repositories, news archives. The training corpus for GPT-3, published by OpenAI in 2020, contained approximately 570 GB of filtered text. Models since then have been trained on orders of magnitude more.

The assumption embedded in this approach is that a large enough corpus is neutral — that statistical averaging over enough text will produce something like knowledge. The Stochastic Parrots paper challenged this assumption at its foundation.

The internet is not a neutral sample of human thought. It overrepresents English. It overrepresents educated, Western, relatively affluent speakers. It underrepresents the Global South. It contains decades of racist, sexist, homophobic, ableist, and otherwise harmful content, produced by humans who held those views, in quantities that dwarf the corrective content that also exists in the corpus. A model that learns to predict plausible text from this corpus does not average out those biases. It learns them, encodes them in its weights, and then reproduces them fluently and confidently in outputs.

This is not a fixable edge case. It is a structural feature of the data collection method. To build a model on scraped internet text is to build a model on the biases, ideologies, and power relations embedded in that text. The larger the model, the more precisely it has learned those patterns.

The authors also noted a subtler problem: **the documentation of this data is systematically incomplete**. No one has fully audited what is in Common Crawl. The researchers building the models do not have a complete account of what their training data contains. This means they cannot fully characterize what their models have learned.

This is not a technical complaint. It is a scientific one. A scientist who cannot characterize their experimental materials cannot make reliable claims about their experimental results.

---

### Argument 3: Stochastic Parrots Generate Fluent, Confident Misinformation

A language model does not understand what it is saying. This bears repeating because it is counterintuitive when the outputs look intelligent.

What a large language model does, at a mathematical level, is predict the next token in a sequence given all previous tokens, using a probability distribution learned from training data. That is the complete description of the mechanism. There is no internal representation of truth. There is no model of the world that the system is consulting when it produces text. There is no understanding.

What there is: an extremely precise statistical model of which words follow which other words, in which contexts, as observed in the training corpus. When that corpus is large enough and the model is deep enough, this produces outputs that are indistinguishable from intelligent writing in many contexts.

The problem is that this mechanism produces fluent text whether the underlying claim is true or false. A language model does not have a truth function. It has a fluency function. The system that writes a correct scientific explanation and the system that writes a plausible-sounding false one are running the same computation — they are simply landing on different probability peaks in the distribution.

The Stochastic Parrots paper called this out as a fundamental safety risk. A system that generates fluent misinformation at scale, with no internal mechanism for distinguishing true from false, and which is deployed to millions of people as a knowledge tool, is a system that is structurally suited to spreading false beliefs. The fluency is not a sign of reliability. The fluency is part of the danger.

The authors also pointed out a related problem: users of these systems tend to attribute comprehension to fluency. When a system writes confidently, people believe it is informed. This is a cognitive bias that language models exploit, not by design, but by function. They are optimized to produce convincing text, and convincing text is text that sounds like it knows what it's talking about.

---

### Argument 4: The Size Race Has Diminishing Safety Returns

Between 2018 and 2021, the dominant trend in large language model research was scale. GPT-2 (2019): 1.5 billion parameters. GPT-3 (2020): 175 billion parameters. Each increase in scale produced improvements in certain benchmark metrics. The research community and the technology industry interpreted this as a general law: larger is better.

The Stochastic Parrots paper contested this interpretation. The authors pointed out that benchmark performance improvements do not track to real-world safety, fairness, or reliability improvements in any straightforward way. Models trained on biased data become more precisely biased as they scale — they learn the harmful patterns in the data more thoroughly, not less.

Moreover, the authors pointed out that the published metrics used to evaluate large language models often do not measure the properties that matter most. Perplexity scores and benchmark accuracy on curated test sets do not tell you whether a model will produce racist outputs under certain prompting conditions. They do not tell you whether the model will generate confident misinformation. They do not tell you whether the model is safe to deploy to a general population.

The size race was producing systems that could do more, not systems that were safer. The distinction matters enormously. A system that can do more — write longer text, answer more questions, generate more convincing content — but is not more aligned with human values or more resistant to producing harm is simply a more dangerous system in a larger box.

The paper argued for a fundamental reorientation: the question is not how large we can build these models, but whether we should build them this large at all.

---

### Argument 5: Marginalized Communities Bear the Costs Without Controlling the Benefits

The harms produced by language models are not distributed evenly. The stochastic parrot problem — the generation of fluent harmful text — falls hardest on the communities whose language and experience are already least represented in the training data.

Consider: a language model trained predominantly on English-language internet text will perform better in English than in any other language. Within English, it will perform better on mainstream American and British English than on Caribbean creole Englishes, African American Vernacular English, or other dialects that are underrepresented in formal written text online. For languages like Haitian Creole, Jamaican Patois, or Bajan, the model may have seen so little training data that its outputs are not just less accurate — they are unreliable in ways the user cannot easily detect.

This is not an abstract problem. When a student in Kingston uses a language model as a learning tool and receives confident, fluent, incorrect information in a form of English that misrepresents how they actually speak, they are experiencing a specific harm that a student in Chicago is less likely to experience. The model is not neutral across populations. It is better calibrated to some populations and worse to others, and the populations it is worse calibrated to are generally the populations with the least power to demand better.

Beyond language performance, the paper identified a structural disparity in who bears the costs of large language model development: the carbon emissions, the labor, the harmful outputs, the erosion of linguistic and cultural distinctiveness through homogenization toward English-dominant internet text. These costs fall disproportionately on communities in the Global South, on marginalized communities within wealthy countries, on speakers of minority languages. Meanwhile, the benefits — access to the most capable tools, the ability to shape how they are deployed, the financial returns from their commercialization — accrue disproportionately to those already at the centers of technological power.

The paper named this disparity explicitly. It was, in part, why it was suppressed.

---

## Part III: The Firing

### What Actually Happened

In December 2020, Gebru and her co-authors submitted "Stochastic Parrots" to Google's internal review process, as required before submitting to an external venue. Google researchers are required to get internal approval to publish papers that touch on Google's business interests.

Google's leadership — specifically a research director named Megan Kacholia, acting on instructions from higher up — responded by telling Gebru that the paper needed to be either retracted or her name removed. The stated reason was that the paper had been insufficiently reviewed.

Gebru responded by email asking for specifics: which review steps had been skipped? Who was being asked to review it? What was the process for determining that it fell below publication standards? She also said that if these requests were not addressed, she would consider resigning.

Google's response was to fire her. By email. While she was at a virtual conference. Attending a memorial for a colleague who had died.

The company later claimed that she had resigned. She had not. She had said she was considering resigning if certain questions were not answered. They fired her instead, and then characterized it as a resignation.

Margaret Mitchell, Gebru's co-lead of the Ethical AI team and co-author of the paper, was fired two months later, in February 2021. Google stated that Mitchell had violated their code of conduct by searching for documentation of what had happened to Gebru. She was looking, inside her own files, for evidence of what had been done to her colleague.

Both women's names were removed from the published version of the paper. The paper was published at FAccT 2021 without two of its four authors.

### What This Pattern Means

The firing of Timnit Gebru is documented. It is not disputed in its basic facts. What is disputed is its meaning.

Google's official position is that it was a personnel matter, that the paper had not completed proper review, and that the decision was procedurally justified. This position has been consistently contradicted by the testimony of people who were present for the events, by the emails that were subsequently made public, and by the observable fact that the review process Gebru asked for was never provided.

The observable pattern is this: a researcher who worked inside one of the most powerful AI development organizations in the world published research that challenged the safety of the core product that organization was building. She was fired. Her co-lead was fired two months later. The research was published without their names. The development of large language models continued and accelerated.

This is not an anomaly. It is a pattern.

The Oppenheimer parallel is instructive. J. Robert Oppenheimer helped build the atomic bomb and then, after witnessing what it did, became one of its most prominent critics. He advocated for international oversight, arms control, and a slower approach to further development of nuclear weapons. He was stripped of his security clearance in 1954. The nuclear arms race continued.

The structural dynamic is identical. The difference is that Oppenheimer's story played out over years and involved the apparatus of Cold War national security. Gebru's story played out in months, inside a private company, with no external oversight, no congressional hearing, no formal process of accountability. The speed and completeness of the suppression was possible precisely because it happened inside a corporation, not a government. Corporations have fewer obligations to explain themselves.

---

## Part IV: After the Firing

### The DAIR Institute

In 2021, after leaving Google, Timnit Gebru founded the **Distributed AI Research Institute (DAIR)**. The name is deliberate. The institute's founding premise is that AI research accountable only to its funders is not trustworthy research, and that the communities most affected by AI systems should be involved in the research about those systems — not as subjects of study, but as participants in it.

DAIR operates with community input, publishes openly, and does not depend on funding from the companies whose products it studies. It is, by design, the thing that Google Brain's Ethical AI team was supposed to be and could not be — an organization that can say things that are true about AI regardless of whether those truths are commercially inconvenient.

The institute has since produced research on algorithmic harm, AI labor, and the societal consequences of large language model deployment, all of it independent of the commercial interests that make such research difficult inside technology companies.

### The Broader Suppression Pattern

Gebru's case was the most publicly documented, but it was not isolated.

- **Margaret Mitchell**: Fired from Google two months after Gebru. Mitchell had previously led Google's model cards initiative — a transparency framework for documenting AI model limitations. After her firing, she joined Hugging Face, where she continued similar work.

- **AI safety researchers at major companies** have consistently reported that findings which challenge the deployment timeline or commercial viability of a system face significant internal resistance. The specific mechanisms vary: papers are delayed in internal review, critical findings are reframed as positive in public communications, researchers are moved to different projects, or their findings are simply not acted on.

- In 2023 and 2024, multiple former employees of OpenAI, Google DeepMind, and Anthropic spoke publicly about internal disagreements over deployment safety. Several signed letters to regulators requesting oversight mechanisms that their employers were actively lobbying against.

- **Geoffrey Hinton**, often called one of the "godfathers of deep learning" for his foundational contributions to neural networks, resigned from Google in May 2023 and immediately began warning publicly about the risks of the technology he had helped build. He described, in interviews, the difficulty of raising these concerns while inside a company financially committed to the technology's rapid development.

The pattern across these cases is consistent: internal safety research that challenges the development trajectory gets suppressed. External researchers who make similar arguments are dismissed as sensationalists or as not understanding the technology. The development continues.

---

## Part V: The Caribbean and Global South Dimension

### The Stochastic Parrot Problem Is Worst for the Communities Least Represented

The paper's warning about the relationship between training data and harm falls with particular weight in the Caribbean and Global South.

**Jamaican Patois** (Patwa) is a creole language with an estimated 2–3 million native speakers and significantly more second-language speakers throughout the Jamaican diaspora. It is a grammatically complex language with its own phonological rules, syntax, and vocabulary. It is not a degraded form of English. It is a distinct language.

The training corpora for major large language models contain negligible amounts of Patois text. This means that a Jamaican student using a language model tool will encounter a system that may occasionally attempt to process Patois inputs but does so with poor calibration — generating outputs that do not track the actual meaning, sometimes confidently. When the model encounters text it poorly understands, it does not report uncertainty. It continues generating plausible-sounding text. The stochastic parrot problem — fluent output without understanding — is most acute precisely where the training data is thinnest.

**Haitian Creole** (Kreyòl ayisyen) has approximately 12 million speakers, making it one of the largest creole languages in the world. Despite this, it is profoundly underrepresented in major training corpora, which skew heavily toward English, followed by other European languages.

**Caribbean English varieties** — Bajan, Trinidadian, Guyanese, and others — are similarly underrepresented. The effect is that language models reflect, reinforce, and extend the marginalization of these languages and their speakers. When AI tools are deployed in educational settings across the Caribbean without acknowledgment of these limitations, students receive worse educational tools than students in English-dominant markets. They may not know this is happening. The tool produces confident text; the confidence is not informative.

This is the structural point the Stochastic Parrots paper was making: the communities who bear the most risk from poorly calibrated AI systems are the communities with the least ability to demand better calibration. The power to shape how these systems are built — what data they train on, what languages they prioritize, what harms they are evaluated for — is concentrated in a small number of companies in a small number of cities. The consequences are distributed globally, and not evenly.

### Epistemic Cowardice

There is a concept worth naming directly: **epistemic cowardice**. It refers to the institutional behavior of prioritizing self-preservation over truth-telling — of knowing something true, having the capacity to say it clearly, and choosing not to, because saying it is costly.

Epistemic cowardice is not the same as not knowing. It is knowing, and choosing not to say, because saying would be inconvenient, expensive, or professionally risky.

Google knew what the Stochastic Parrots paper said. It had been reviewed internally. The concerns were understood. The company chose to suppress the paper rather than address its arguments. This is epistemic cowardice at the institutional level.

It is also recognizable as a pattern that appears across many institutions: corporations that know about product harms before they become public, governments that suppress uncomfortable data, universities that protect powerful faculty by silencing students. The mechanism is the same regardless of the institution. The stakes in AI development are higher than most, because the technology scales faster and the potential harms are larger.

---

## Vocabulary

**Stochastic Parrot** — a system that generates statistically plausible language without understanding its meaning

**Large Language Model (LLM)** — a neural network trained on massive text corpora to predict and generate text; examples include GPT models, Gemini, Claude, LLaMA

**Training Corpus** — the dataset on which a model is trained; its composition determines what the model learns

**Epistemic Cowardice** — institutional behavior that suppresses truthful findings to protect commercial or reputational interests

**DAIR Institute** — Distributed AI Research Institute; founded by Timnit Gebru in 2021 as an independent, community-accountable AI research organization

**Black in AI** — nonprofit organization co-founded by Timnit Gebru and Rediet Abebe to increase the representation and inclusion of Black researchers in artificial intelligence

**FAccT** — ACM Conference on Fairness, Accountability, and Transparency; a major venue for research on the societal impacts of AI systems

**Common Crawl** — a nonprofit that maintains an open repository of web crawl data widely used in LLM training; contains petabytes of internet text

---

## Primary Sources and Further Reading

- Bender, E. M., Gebru, T., McMillan-Major, A., & Shmitchell, S. (2021). On the Dangers of Stochastic Parrots: Can Language Models Be Too Big? *FAccT '21 Proceedings of the 2021 ACM Conference on Fairness, Accountability, and Transparency.*

- Strubell, E., Ganesh, A., & McCallum, A. (2019). Energy and Policy Considerations for Deep Learning in NLP. *ACL 2019.*

- Perrigo, B. (2023, January 18). Exclusive: OpenAI Used Kenyan Workers on Less Than $2 Per Hour to Make ChatGPT Less Toxic. *TIME.*

- Wired staff coverage of the Gebru firing: multiple pieces, December 2020 – February 2021.

- Timnit Gebru's own documentation on Twitter/X, December 2020, which constitutes primary source evidence about the sequence of events.

- DAIR Institute: dair-institute.org

---

## Discussion Questions

These questions do not have single correct answers. They require reasoning from evidence, not recitation of facts.

**1. The Procedural Defense**
Google's public justification for suppressing the Stochastic Parrots paper was procedural: the paper had not completed proper internal review. Evaluate this justification. What would you need to know to determine whether it was legitimate? What evidence exists about whether the review process was followed or circumvented? Does the procedural justification change your evaluation of the underlying facts?

**2. Who Pays**
The Stochastic Parrots paper identifies a gap between who bears the costs of large language model development (carbon emissions, harmful outputs, marginalization of non-English speakers) and who controls the decisions that produce those costs. Map this gap in concrete terms: list at least three specific populations and the specific costs they bear. Now list who controls the development decisions. Does this distribution seem acceptable? If not, what would have to change to shift it?

**3. The Oppenheimer Parallel**
The lesson draws a parallel between J. Robert Oppenheimer and Timnit Gebru — both were leading figures in powerful technologies, both became prominent critics, both were professionally punished for that criticism. Where does the parallel hold and where does it break down? What does the difference in their situations — a government program versus a private corporation — tell you about accountability structures in AI development?

**4. Caribbean Calibration**
You are a Jamaican student using a large language model for homework help. The model performs significantly better on Standard American English than on Jamaican Patois. You may not know this. The model will not tell you. What would need to be true for this situation to be fair? What would need to change about the way these tools are built, documented, or deployed to address it? Who would have to do that work, and what incentives do they currently have to do so?

**5. Institutional Honesty**
The lesson introduces the concept of epistemic cowardice — institutions that know something true and choose not to say it because saying is costly. Can you identify an example from your own experience of an institution (a school, a government, a company, a family) exhibiting epistemic cowardice? What was the cost of the silence? What would have been required to break it? What protected the people who maintained it?

---

## Activities (Choose One Based on Available Time)

**Activity A — Close Reading (30 minutes)**
Obtain the abstract and conclusion sections of "On the Dangers of Stochastic Parrots" (publicly available). Read them carefully. Write a 300-word summary in your own words that captures all five of the paper's core arguments. Then write one sentence for each argument explaining why a technology company building large language models might not want that argument to be widely read.

**Activity B — Timeline and Analysis (45 minutes)**
Build a detailed timeline of the events from the paper's submission to Gebru's firing to Mitchell's firing to the paper's publication without their names. For each event, record: what happened, who made the decision, what the stated justification was, and what the observable consequences were. At the end, write a one-paragraph analysis of what the timeline shows about how the review process functioned.

**Activity C — Data Audit (60 minutes)**
Using publicly available documentation about Common Crawl and GPT training data, research what languages are represented in major LLM training corpora and in what proportions. Then research the number of speakers of Jamaican Patois, Haitian Creole, and at least two other Caribbean languages. Write a one-page analysis comparing representation in training data to speaker population size. What does the discrepancy look like, and what are its probable consequences for users of these tools in the Caribbean?

---

*Standards: NSF Computer Science & Social Studies Grade 11–12. UWI COMP3601 / SOCI3401. AP Computer Science Principles. AP Research.*
*Luminous Works LLC / JUICY Academy AIS-09. Version 1.0.*
