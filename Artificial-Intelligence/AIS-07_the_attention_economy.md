# AIS-07: The Slot Machine in Your Pocket

**Subtitle:** Artificial Intelligence — Lesson 7
**Module:** AI Ethics
**Duration:** 90 minutes
**Level:** Grade 10–University

---

> *"How do we consume as much of your time and conscious attention as possible?"*
>
> — Sean Parker, founding president of Facebook, 2017

---

## Before We Begin: What Is the Business Model?

Before we discuss algorithms, before we discuss psychology, before we discuss data — you need to understand one thing clearly.

**Social media is not a service. It is an advertising auction.**

Every major social media platform — Facebook, Instagram, TikTok, YouTube, Twitter/X, Snapchat — makes the overwhelming majority of its money by selling your attention to advertisers. Not your data directly. Your *attention*.

Here is how the transaction works:

1. A company wants to sell you something — shoes, a political candidate, a diet plan.
2. They pay the platform to show you an advertisement.
3. The price they pay depends on how many people saw the ad, and crucially, how long they were looking at it.
4. Therefore, the platform's revenue increases directly as a function of how long you use the platform.
5. Therefore, every engineering decision, every design decision, every product decision is ultimately oriented toward one goal: **keep you on the platform as long as possible.**

This is not a conspiracy theory. It is publicly documented business strategy. The platforms publish their advertising revenue in quarterly earnings reports for investors. In 2023, Meta (Facebook, Instagram, WhatsApp) generated $131.9 billion in revenue. Approximately 98% of that came from advertising. Google (YouTube) generated $237.9 billion, the vast majority from advertising.

You are not the customer. You are the product being sold.

Everything that follows in this lesson is a consequence of that economic fact.

---

## Part I: The Science Was Built in a Stanford Laboratory

### B.J. Fogg and the Persuasive Technology Lab

In 1997, a researcher named B.J. Fogg established the Persuasive Technology Lab at Stanford University. The lab's research program was straightforward in its statement of purpose: to understand how computers — software, websites, applications — could be designed to *change human behavior and attitudes*.

Fogg called this field "captology" — from the acronym CAPT: Computers As Persuasive Technology. He developed a formal model called the **Fogg Behavior Model**, which states that a behavior occurs when three things converge simultaneously:

- **Motivation**: the person must want to perform the behavior
- **Ability**: the behavior must be easy to perform
- **Prompt**: there must be a trigger that initiates the behavior at the right moment

This is a legitimate field of academic inquiry with real applications — it has been used to design apps that encourage exercise, medication adherence, and energy conservation. The science itself is not inherently malicious.

What happened next was not Fogg's direct doing, but it was the direct consequence of his work reaching Silicon Valley at the exact moment Silicon Valley had both the motive and the technical capability to deploy it at planetary scale.

Fogg's Stanford students became the architects of the platforms now used by billions of people. Among them:

- **Mike Krieger**, co-founder of Instagram
- **Tristan Harris**, who later became the tech industry's most prominent internal critic, the subject of the documentary *The Social Dilemma*, and a founder of the Center for Humane Technology
- Numerous product designers and engineers at Facebook, Google, Twitter, and Snapchat who applied the principles of persuasive technology not to help users but to maximize their engagement metrics

Fogg himself has expressed discomfort with how his research was applied. In a 2019 interview with the *New York Times*, he distanced himself from the "dark patterns" built using his frameworks, stating that he had always intended the technology to be used for good. Whether that disclaimer is sufficient is a genuine ethical question worth debating.

But the academic lineage is clear: the behavioral science that underpins the modern attention economy was developed at Stanford, and the people who built that economy were trained there.

### The Lever That Does Not Pay Out

To understand why the specific design choices made by social media companies are so effective, you need to understand a finding from 20th-century experimental psychology that predates the internet by sixty years.

In the 1930s, American psychologist **B.F. Skinner** was conducting research on operant conditioning — the process by which behavior is shaped by its consequences. Using specially designed boxes (now called Skinner boxes), he trained rats and pigeons to press levers to receive food pellets.

He then varied the *schedule* of reinforcement — the relationship between pressing the lever and receiving the reward. He identified four primary schedules:

1. **Fixed ratio**: reward every nth press (press 5 times, get a pellet)
2. **Variable ratio**: reward after an unpredictable number of presses
3. **Fixed interval**: reward after a fixed time period has passed
4. **Variable interval**: reward after an unpredictable time period

The finding that has since reverberated through casino design, video game design, and social media design is this:

**Variable ratio reinforcement produces the highest, most persistent rate of responding, and is the most resistant to extinction.**

In plain language: if you do not know when the reward is coming, you press the lever *more* than if you do know. You press it compulsively. You press it even when you are tired. You press it even when the rewards have largely stopped. The uncertainty itself drives the behavior.

This is why slot machines work. The gambler does not know when the next win is coming. The uncertainty is not a bug — it is the core mechanism. Remove the unpredictability and replace it with a fixed payout schedule, and people play far less.

Now look at your phone.

When you pull down to refresh your Instagram feed, or scroll down through TikTok, or open Twitter — you do not know what you are going to get. Sometimes you get something that makes you laugh, or surprises you, or moves you, or connects you to someone you care about. Sometimes you get nothing interesting. The ratio is variable. The reward is unpredictable.

This is not an accident. This is the Skinner box, rebuilt at global scale, optimized by machine learning.

The "pull to refresh" gesture — which mimics the physical action of pulling a slot machine lever — was deliberately designed to activate this response. Aza Raskin, who invented the infinite scroll (the continuous feed that never ends and therefore never gives you a natural stopping point), has publicly stated: *"It's as if they took behavioral cocaine and sprinkled it on the interface."* He has also stated that he regrets the invention.

---

## Part II: The Architects Confess

### Sean Parker: The Founding Admission

In November 2017, Sean Parker — who was the first president of Facebook, an early investor, and one of the architects of its initial growth strategy — gave a remarkable interview at an Axios event in Philadelphia. He said:

*"The thought process that went into building these applications, Facebook being the first of them... was all about: 'How do we consume as much of your time and conscious attention as possible?' And that means that we need to sort of give you a little dopamine hit every once in a while, because someone liked or commented on a photo or a post or whatever. And that's going to get you to contribute more content, and that's going to get you... more likes and comments. It's a social validation feedback loop... exactly the kind of thing that a hacker like me would come up with, because you're exploiting a vulnerability in human psychology."*

*"The inventors, creators — it's me, it's Mark [Zuckerberg], it's Kevin Systrom on Instagram, it's all of these people — understood this consciously. And we did it anyway."*

He concluded: *"God only knows what it's doing to our children's brains."*

Read that last sentence again. The person who helped design these systems, who understood exactly what they were building and built it deliberately, does not know what it is doing to children's brains. This is not a philosophical uncertainty. It is an admission that the experiment was run on a population — including children — before anyone knew the results.

### Chamath Palihapitiya: The Growth Machine Repents

Chamath Palihapitiya served as Facebook's Vice President of User Growth from 2007 to 2011. In December 2017, speaking at a Stanford Business School event, he said:

*"I feel tremendous guilt. I think we all knew in the back of our minds — even though we feigned this whole line of, like, there probably aren't any bad unintended consequences. I think in the back, deep, deep recesses of our minds, we kind of knew something bad could happen. But I think the way we defined it was not like this."*

*"So we are in a really bad state of affairs right now, in my opinion. It is eroding the core foundation of how people behave by and between each other. And I don't have a good solution. My solution is I just don't use these tools anymore. I haven't for years."*

He went on: *"We have created tools that are ripping apart the social fabric of how society works. That is truly where we are."*

Palihapitiya has since partially walked back these remarks, saying he had been "being dramatic." You should evaluate that retraction alongside the fact that he is a venture capitalist who invests in technology companies.

### What These Confessions Tell Us

Parker and Palihapitiya were not whistleblowers in the traditional sense. Neither of them was exposing internal documents or data the company wanted hidden. They were describing, from memory, what they had consciously designed and why. The decisions were deliberate. The goal — maximum engagement, maximum time-on-platform, exploitation of psychological vulnerabilities — was explicit.

This is important to understand because a common defense of these platforms is that the harmful outcomes were unintended consequences that no one could have foreseen. Parker's own words refute that defense.

---

## Part III: The Algorithm Learns What Keeps You Watching

### How Recommendation Algorithms Work

The core technology driving engagement on modern platforms is the **recommendation algorithm** — the system that decides what content to show you, in what order, and how often.

These algorithms are trained using machine learning. They observe enormous amounts of behavioral data: what you click, what you linger on, what you scroll past quickly, what you share, what you comment on, what you come back to. Using this data, they build a model of what will keep you engaged, and they optimize their recommendations to maximize that engagement.

The key metric these systems optimize for is **engagement** — typically measured as time spent on the platform, clicks, likes, comments, and shares. This seems reasonable on its surface: if people are engaging with content, they must find it valuable, right?

The problem is that human psychology does not work that way. The content that generates the most behavioral response is not necessarily the content that is most beneficial, most accurate, or most conducive to human wellbeing.

### The Outrage Premium

In 2017, Facebook's own internal research, as later reported by *The Wall Street Journal* citing internal documents, found that posts using "angry" reactions drove engagement at a significantly higher rate than posts using "like" or "love" reactions. The company subsequently adjusted its algorithm to weight angry reactions more heavily in determining what to show to other users — and then, after internal concerns were raised about increasing divisiveness, quietly reversed this change.

Multiple researchers have documented that content generating anger, fear, moral outrage, and disgust receives dramatically higher engagement than content generating positive emotions. Studies published in *Nature Human Behaviour* and the *Proceedings of the National Academy of Sciences* have found that on Twitter, the inclusion of "moral-emotional" words (words that are both morally charged and emotionally activating) increases the spread of tweets by approximately 20% per word.

The figure you will see cited in many analyses — that outrage content generates 5 to 8 times more engagement than content generating positive emotions — is an approximation drawing on multiple studies rather than a single definitive number. But the directional finding is consistent across the research: anger and fear drive engagement. Therefore, algorithms optimizing for engagement will systematically promote anger and fear.

No one at Facebook or Twitter or YouTube sat in a meeting and said "let's make the world angrier." What happened instead is a failure of proxy measurement: the engineers chose engagement as the metric to optimize, and the algorithm found that outrage was the most efficient path to that metric. The division and polarization are emergent properties of the optimization function.

William Brady and colleagues at NYU found in a 2023 study that social media algorithms "amplify content containing moral outrage disproportionately" — and that users who receive this amplified outrage become more likely to produce it themselves, creating a feedback loop.

The technical term for this is **algorithmic amplification of divisive content**. The plain-language description is: the machines are making us angrier because anger keeps us watching.

---

## Part IV: The Data Scandal That Was Not a Theft

### Cambridge Analytica

In 2018, it was revealed that a political consulting firm called Cambridge Analytica had obtained the personal data of approximately 87 million Facebook users and used it to build psychological profiles for targeted political advertising. The firm worked for Donald Trump's 2016 presidential campaign and for the Leave.EU campaign in the Brexit referendum.

The way this data was obtained is crucial to understand because it exposes a structural feature of the platform, not simply a one-time breach.

In 2014, a researcher at Cambridge University named Aleksandr Kogan built a personality quiz app called "thisisyourdigitallife." The app was distributed through Facebook. Approximately 270,000 people took the quiz and granted the app permission to access their Facebook profile data.

Here is the part that matters: **through Facebook's API at the time, accessing a user's data also allowed access to that user's friends' data, without those friends' knowledge or consent.**

270,000 people took the quiz. But 270,000 people's friend networks totaled approximately 87 million profiles. All of that data — posts, likes, political affiliations, relationship statuses, workplace information, location history — was legally extracted using Facebook's own developer tools, which Facebook had deliberately designed to encourage exactly this kind of sharing, because third-party apps that used Facebook data increased platform engagement and growth.

The data was not stolen. It was harvested through a mechanism Facebook had built and knew existed. Facebook was aware that Kogan's data was being passed to Cambridge Analytica and did not act until the story was already breaking publicly. A 2019 FTC investigation resulted in a $5 billion fine against Facebook — the largest in the agency's history at the time — for privacy violations.

Cambridge Analytica used the 87 million profiles to build a psychographic targeting system: mapping individuals' psychological profiles to the "OCEAN" personality model (Openness, Conscientiousness, Extraversion, Agreeableness, Neuroticism) and then using that information to serve them specifically targeted political messaging designed to exploit their psychological vulnerabilities.

Former Cambridge Analytica employee Christopher Wylie, who became the primary whistleblower, described it this way: *"We exploited Facebook to harvest millions of people's profiles. And built models to exploit what we knew about them and target their inner demons."*

The 2019 Netflix documentary *The Great Hack* documents this case in detail and is assigned supplemental viewing for this lesson.

---

## Part V: The Company Knew

### Frances Haugen and the Facebook Files

In September 2021, Frances Haugen — a former Facebook product manager who had previously worked at Google, Pinterest, and Yelp — left Facebook and brought with her thousands of pages of internal company documents. She gave copies to the Securities and Exchange Commission and to a consortium of news organizations including the *Wall Street Journal*, which published a landmark series called "The Facebook Files."

Haugen's testimony before the United States Senate Commerce Committee in October 2021, and before the British Parliament, and before the European Parliament, constitutes one of the most significant corporate whistleblowing disclosures since the tobacco industry hearings of the 1990s.

The documents she disclosed revealed several findings that are directly relevant to this lesson:

**On Instagram and teenage girls:**
Facebook's internal researchers had, by 2019, documented that Instagram use was associated with negative mental health outcomes for teenage girls, particularly around body image. One internal slide read: *"We make body image issues worse for one in three teen girls."* Another noted that among teenagers who reported suicidal ideation, 13% of British users and 6% of American users traced the desire to kill themselves to Instagram.

The company knew this. Senior executives, including Mark Zuckerberg, were briefed on these findings. The response was to commission further internal research — some of which was, according to Haugen's testimony, suppressed or not published — and to continue operating Instagram without substantive changes to the features identified as harmful.

Facebook had been developing a version of Instagram targeted at children under 13 ("Instagram Kids"). Following the Haugen disclosures, this project was paused. It has since been revived in modified form.

**On political polarization:**
The internal documents revealed that Facebook's own researchers had designed and proposed changes to the algorithm that would reduce the spread of divisive and misinformation-laden content. These proposals were rejected or not implemented because they were associated with reduced engagement metrics — that is, the changes that would have made the platform less harmful would also have made it less profitable.

**On the network's awareness of its own harms:**
Across hundreds of pages of internal communications, the documents show a company that understood, in granular detail, the harms its platform was generating — and that consistently prioritized engagement metrics and revenue over acting on that knowledge.

Haugen's framing before Congress: *"Facebook's products harm children, stoke division, and weaken our democracy. The company's leadership knows how to make Facebook and Instagram safer but won't make the necessary changes because they have put their astronomical profits before people."*

---

## Part VI: What the Numbers Say

### The Correlation Between Smartphones and Teen Mental Health

The statistician and social psychologist **Jonathan Haidt** at New York University's Stern School of Business has assembled and synthesized the largest body of research on the relationship between social media use and adolescent mental health. His 2023 book *The Anxious Generation* and his collaboration with Jean Twenge draw on multiple large datasets.

The key empirical finding:

In the United States, rates of adolescent depression, anxiety, loneliness, and self-harm began increasing sharply around 2012–2013. The timing correlates closely with the widespread adoption of smartphones and the growth of social media platforms, particularly Instagram (launched 2010) and Snapchat (launched 2011).

Specific data points from Haidt's research synthesis:

- From 2010 to 2020, the percentage of U.S. high school girls who reported persistent feelings of sadness or hopelessness rose from 36% to 57%.
- From 2010 to 2020, the percentage of U.S. high school boys who reported the same rose from 21% to 31%.
- Hospital admissions for self-harm among U.S. girls aged 10–14 nearly tripled between 2009 and 2015.
- Suicide rates among U.S. females aged 10–14 doubled between 2007 and 2015.
- Similar trends have been documented in Canada, the United Kingdom, Australia, and other countries with high smartphone adoption rates, all following similar timing patterns.

Jean Twenge's large-scale survey research, published in *Clinical Psychological Science*, found that adolescents who spent 5 or more hours per day on electronic devices were 66% more likely to have at least one suicide risk factor (suicidal ideation, making a plan, or attempting suicide) than those who spent 1 hour per day.

**The causation question:**
It is important to be precise here. The existence of a correlation — the two trends occurring at the same time — does not automatically prove that social media *caused* the increases in depression and anxiety. Researchers debate this. Alternative explanations have been proposed: economic stress, academic pressure, climate anxiety, the effects of the 2008 financial crisis on family stability.

Haidt's argument is that the correlation is too strong, too consistent across countries, and too specifically tied to girls' use of image-based social media to be dismissed. He cites the asymmetry between boys and girls (girls are more affected, and girls use Instagram and Snapchat more than boys do), the dose-response relationship (more use correlates with worse outcomes), and the narrowing of the gap in places that have regulated social media use.

The debate about causation is scientifically legitimate. What is not legitimate is the position that there is no evidence of harm. There is substantial evidence of harm. The question is how much and by what mechanism.

---

## Part VII: The Unequal Platform

### Content Moderation and Racial Disparity

Content moderation — the process by which platforms decide what content to remove, restrict, or amplify — is not a neutral process. Multiple investigations and first-hand accounts have documented systematic disparities in how these systems treat content from Black creators and communities.

**Documented findings:**

A 2021 audit of Facebook's content moderation practices, conducted by civil rights organizations including the NAACP Legal Defense Fund and Color of Change, found evidence of inconsistent enforcement of Community Standards, with content posted by Black users more likely to be removed or flagged than equivalent content from white users.

Black creators across Instagram, TikTok, YouTube, and Twitter have documented experiences of "shadowbanning" — a practice in which content is made invisible to other users or removed from recommendation systems without the creator being notified or given an explanation. TikTok, in a 2019 leak of internal moderation documents, was found to have instructed moderators to suppress content from users who were "ugly," overweight, or disabled — raising immediate questions about whose definition of "ugly" was being applied.

The "hashtag suppression" phenomenon has been documented specifically around Black Lives Matter content. During the 2020 protests following the murder of George Floyd, multiple users reported that hashtags associated with the movement were not auto-completing in search, or that posts using those hashtags were receiving reduced reach without explanation.

**Why this happens:**

There are two distinct mechanisms:

1. **Algorithmic bias in automated moderation**: Machine learning models trained on historical content moderation decisions will replicate the biases of those decisions. If human moderators historically flagged Black vernacular English as "threatening" or "aggressive" at higher rates, the automated system will do the same. This is the same training data problem discussed in Lesson AIS-08, applied to content moderation.

2. **Disparate impact of neutral-seeming rules**: Rules that appear race-neutral can have racially disparate impacts. A rule that removes "graphic content" without adequate context for what constitutes "graphic" may result in the removal of documentation of racial violence — the kind of footage that has historically been essential to holding law enforcement accountable — while leaving intact other graphic content that does not document racial harm.

The platforms have not resolved these disparities. They have, largely, denied or minimized them, published diversity statistics, and continued operating.

---

## Part VIII: The Caribbean Dimension

### Small Islands, Outsized Damage

The dynamics described in this lesson — algorithmic amplification of outrage, psychological manipulation for engagement, data exploitation, content moderation disparities — do not operate uniformly across the world. In small, densely connected communities, they operate with particular intensity.

Consider the specific context of the Caribbean:

**Social graph density:** In a country with a population of 300,000 people (approximately the size of Barbados or Saint Lucia), social media platforms do not connect strangers — they connect neighbors, extended family networks, co-workers, church communities. A piece of disinformation or outrage content does not travel across ideological silos; it travels through the same social fabric that holds communities together.

**Political weaponization:** Caribbean elections are fought in small electorates where individual votes matter significantly. Multiple documented cases have emerged across the region of politically motivated disinformation campaigns, coordinated inauthentic behavior (fake accounts creating the illusion of mass opinion), and foreign-funded political advertising deployed through Facebook and Instagram. The same Cambridge Analytica firm that operated in the United States and United Kingdom operated in the Caribbean — including in Trinidad and Tobago, where it was hired by the People's National Movement ahead of the 2010 elections. Former Cambridge Analytica CEO Alexander Nix identified the Caribbean as a key market for the firm's services.

**Economic exploitation:** The platforms extract advertising revenue from Caribbean users while providing minimal local content moderation, minimal local language support (particularly for Caribbean Creole languages and Patois), and minimal local accountability structures. The economic value of Caribbean users' attention flows to Silicon Valley while the harms of the platform's design remain in the communities.

**The Haiti information environment:** Following the 2021 assassination of President Jovenel Moïse, social media platforms became vectors for competing disinformation campaigns, political manipulation, and gang recruitment content. With mainstream news infrastructure degraded, Facebook became a primary information source for millions of Haitians at precisely the moment when the information being circulated on that platform was least reliable and most algorithmically amplified for outrage.

**Jamaica and regional specific:** Research documented by the University of the West Indies has noted the role of social media in the spread of gang-affiliated content and community intimidation. The same algorithmic dynamics that make outrage content viral in the United States make gang threats, community feuds, and politically motivated harassment viral in Jamaican communities — but with less institutional infrastructure to respond.

---

## Part IX: What Can Be Done

This section is deliberately shorter than the preceding ones. The purpose is not to offer false reassurance. The problems documented here are structural — they arise from the business model, not from individual bad actors — and structural problems require structural solutions.

**Regulatory approaches under active consideration:**
- Age verification requirements for social media platforms (enacted in several U.S. states; under consideration in the EU and UK)
- Requirements to offer "chronological feed" options without algorithmic ranking
- Prohibition on the use of behavioral manipulation techniques (variable reward schedules, infinite scroll, push notifications designed to create compulsive checking) for users under 18
- Mandatory algorithmic audits by independent researchers with access to internal data
- Data minimization requirements — platforms may only collect data necessary for their stated function
- Separation of advertising from content recommendation (so that the advertising business does not directly drive content amplification decisions)

**Individual-level interventions:**
- Chronological feed settings (where available)
- Notification reduction
- Scheduled usage times
- Awareness of the variable reward mechanism — naming it does not remove its effect, but it can reduce it

**The structural point:**
Individual interventions help at the margins. They do not change the business model. A platform that generates revenue from advertising has an inherent incentive to maximize your time on-platform. This incentive will continue to shape every product decision as long as advertising is the revenue model.

The most honest thing this lesson can tell you is that the people who built these systems, at the time they built them, told you clearly what they were doing and why. Sean Parker said it in 2017. The question of what to do about it is political, economic, and social — not primarily technological.

---

## Discussion Questions

These questions do not have predetermined correct answers. They are intended for genuine inquiry.

**1.** Sean Parker described the design of Facebook as "exploiting a vulnerability in human psychology" — and said the designers did it knowingly. At what point does exploiting a psychological vulnerability become an ethical violation? Is there a meaningful difference between Facebook's design choices and the design choices made by cigarette companies to make nicotine more addictive? What distinguishes one from the other, if anything?

**2.** Facebook's internal research showed that Instagram was harming teenage girls' body image and mental health. The company knew this. What should the legal and ethical obligation of a company be when its own research identifies harm to its users — particularly to minors? Does a company have a duty to act on this knowledge even if acting on it reduces profits? Who should have the authority to enforce such a duty?

**3.** The algorithmic amplification of outrage was not an explicitly chosen outcome — it emerged from optimizing an engagement metric. When a harmful outcome emerges from an optimization process rather than from a direct decision, who is morally responsible? The engineers who chose the metric? The executives who approved the product? The algorithm itself? The shareholders who benefit from the revenue?

**4.** Cambridge Analytica used psychological profiles derived from social media data to target political messages at individual voters' "inner demons." Many democracies have strict rules governing political advertising on television and radio. Should the same rules apply to micro-targeted social media advertising? What would it mean for democracy if political campaigns could target individual voters with personalized messages no one else could see?

**5.** The Caribbean has been specifically targeted by political consulting firms using the same tools described in this lesson. Given that Caribbean nations have smaller populations, less developed media fact-checking infrastructure, and higher social media penetration relative to traditional media than many Western nations, does this create specific obligations for the platforms? For governments? For educators? What would an adequate response look like from within the Caribbean itself?

---

## Supplemental Resources

- *The Social Dilemma* (Netflix, 2020) — documentary featuring Tristan Harris, Aza Raskin, and other former tech insiders
- *The Great Hack* (Netflix, 2019) — documentary on Cambridge Analytica
- Jonathan Haidt and Jean Twenge, ongoing research synthesis at AfterBabel.com and the Heterodox Academy
- Frances Haugen's full Senate testimony (publicly available, United States Senate Commerce Committee, October 5, 2021)
- The Facebook Files, *Wall Street Journal*, September–October 2021
- Fogg, B.J. (2003). *Persuasive Technology: Using Computers to Change What We Think and Do*. Morgan Kaufmann.
- Skinner, B.F. (1938). *The Behavior of Organisms: An Experimental Analysis*. Appleton-Century-Crofts.

---

*Standards: NSF Social Studies & Computer Science Grade 10–12 | UWI SOCI2401 / PSYC2301 | AP Psychology | AP Computer Science Principles*
*Luminous Works LLC / JUICY Academy — AIS-07*
*© 2026 Luminous Works LLC. All rights reserved.*
