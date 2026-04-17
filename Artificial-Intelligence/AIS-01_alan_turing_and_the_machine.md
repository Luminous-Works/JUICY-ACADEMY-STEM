# AIS-01: The Godfather
## Artificial Intelligence — Lesson 1

**Core concept:** Computability theory · The Turing Machine · The Halting Problem · What intelligence can and cannot compute  
**Duration:** 90 minutes  
**Subject:** Alan Mathison Turing OBE FRS  
**Born:** Maida Vale, London, 23 June 1912  
**Died:** Wilmslow, Cheshire, 7 June 1954 — aged 41  
**Publication of record:** *Proceedings of the London Mathematical Society*, 1936 — "On Computable Numbers, with an Application to the Entscheidungsproblem"

---

### Opening Statement

> *"We can only see a short distance ahead, but we can see plenty there that needs to be done."*
> — Alan Turing, 1950

In 1936, a 24-year-old mathematician at King's College Cambridge published a paper that defined what a computer is.

There were no computers. Not one. The word "computer" referred to human beings — people employed to sit at desks and perform calculations by hand, all day, every day. The idea of a machine that could execute any algorithm was a philosophical question, not an engineering project.

Alan Turing answered the philosophical question so completely, so precisely, that every engineer who came after him was essentially building the thing he had already described on paper.

The laptop, the phone, the server farm, the model reading these words back to you — they are all, in the strictest mathematical sense, physical implementations of a theoretical object Turing defined in 1936.

He never saw any of them.

He died at 41, two years after the British government chemically castrated him for being gay. He had saved an estimated 14 million lives breaking the Enigma cipher in World War II.

His face is now on the fifty-pound note.

This is the story of the mathematics that built the world you live in — and the man the world destroyed for building it.

---

### 1. The Problem Turing Was Solving

To understand the Turing Machine, you need to understand why it was invented.

In 1928, the German mathematician David Hilbert posed a challenge to the mathematical world — the **Entscheidungsproblem** (German: "decision problem"):

*Is there a general mechanical procedure that can determine, for any mathematical statement, whether it is provable or not?*

In other words: can mathematics be automated? Is there an algorithm — a finite set of rules — that, given any mathematical question, will always produce a yes or no answer?

Hilbert believed the answer was yes. He believed mathematics was complete, consistent, and decidable.

In 1931, **Kurt Gödel** destroyed the first two hopes. His **Incompleteness Theorems** proved that any sufficiently powerful mathematical system contains true statements that *cannot be proven* within that system. Mathematics is not complete. There are truths it cannot reach from inside itself.

Turing destroyed the third hope. He proved that mathematics is not decidable — that there is no general algorithm that can answer all mathematical questions.

He proved this by first asking: *what exactly is an algorithm?*

---

### 2. The Turing Machine — Defining Computation

Before Turing, "algorithm" was an intuitive concept. Everyone understood roughly what it meant — a step-by-step procedure for solving a problem. But no one had a precise mathematical definition.

Turing provided one.

**The Turing Machine** is an abstract device consisting of:

1. **An infinite tape** — divided into cells, each containing a symbol from a finite alphabet (or blank)
2. **A read/write head** — positioned on one cell at a time, capable of reading the symbol there, writing a new symbol, and moving left or right
3. **A finite set of states** — the machine is always in exactly one state
4. **A transition function** — a complete set of rules of the form:

$$\delta: Q \times \Gamma \rightarrow Q \times \Gamma \times \{L, R\}$$

Which reads: *given the current state and the symbol being read, write a new symbol, move left or right, and transition to a new state.*

Formally, a Turing Machine is a 7-tuple:

$$M = (Q,\ \Gamma,\ b,\ \Sigma,\ \delta,\ q_0,\ F)$$

Where:
- $Q$ = finite set of states
- $\Gamma$ = tape alphabet (all symbols the machine can read or write)
- $b \in \Gamma$ = the blank symbol (default content of empty tape cells)
- $\Sigma \subseteq \Gamma \setminus \{b\}$ = input alphabet (symbols in the initial input)
- $\delta: Q \setminus F \times \Gamma \rightarrow Q \times \Gamma \times \{L, R\}$ = transition function
- $q_0 \in Q$ = initial state
- $F \subseteq Q$ = set of halting states

A computation begins with an input written on the tape, the head positioned at the first symbol, and the machine in state $q_0$. At each step, the machine reads the current symbol, consults its transition table, writes a symbol, moves the head, and changes state. When the machine enters a halting state, it stops. The output is what remains on the tape.

This is it. This is the mathematical definition of computation. Everything a computer has ever done — every video rendered, every message sent, every neural network trained — is, in principle, a Turing machine executing a transition function on a tape.

---

### 3. The Universal Turing Machine

Turing then asked a more profound question: can one Turing Machine simulate any other?

The answer was yes — and this is perhaps the most important idea in the history of computing.

A **Universal Turing Machine (UTM)** takes as its input:
1. A description of another Turing Machine $M$ (encoded as a string of symbols)
2. An input $w$ intended for $M$

And simulates exactly what $M$ would do on $w$.

This is the theoretical foundation of the **stored-program computer** — the architecture that every modern computer uses, described in hardware by John von Neumann in 1945. A computer does not need to be physically rebuilt to run a different program. The program is data. The Universal Turing Machine runs on programs the way any other Turing Machine runs on numbers.

Your phone runs Instagram, a calculator, a camera, a map, and a language model — not because it was physically redesigned for each one, but because it is a Universal Turing Machine and the programs are inputs.

Turing proved this was possible in 1936.

---

### 4. The Halting Problem — The Proof That Changed Everything

Now Turing asked the hardest question: **is there a Turing Machine that can determine, for any other Turing Machine and any input, whether that machine will eventually halt — or run forever?**

This is the **Halting Problem**. And Turing proved it is unsolvable. Not just unsolved. *Unsolvable in principle.* No algorithm can exist that solves it for all cases.

The proof is one of the most elegant in mathematics. It proceeds by **contradiction**.

**Assume** that a Turing Machine called $HALT$ exists, such that:

$$HALT(P, I) = \begin{cases} \text{TRUE} & \text{if program } P \text{ halts when given input } I \\ \text{FALSE} & \text{if program } P \text{ runs forever when given input } I \end{cases}$$

Now construct a new program called $PARADOX$:

```
PARADOX(X):
    if HALT(X, X) = TRUE:
        run forever
    else:
        halt immediately
```

$PARADOX$ takes a program $X$ as input and feeds it to $HALT$ alongside itself — asking: *does $X$ halt when given itself as input?*
- If yes: $PARADOX$ runs forever.
- If no: $PARADOX$ halts.

Now ask: **what happens when $PARADOX$ is given itself as input?**

$$PARADOX(PARADOX) = ?$$

**Case 1:** Suppose $HALT(PARADOX, PARADOX)$ returns TRUE — meaning $PARADOX$ halts when given itself.
Then $PARADOX$ reads TRUE and... runs forever.
But we assumed it halts. **Contradiction.**

**Case 2:** Suppose $HALT(PARADOX, PARADOX)$ returns FALSE — meaning $PARADOX$ runs forever when given itself.
Then $PARADOX$ reads FALSE and... halts immediately.
But we assumed it runs forever. **Contradiction.**

Both cases produce contradictions. Therefore $HALT$ cannot exist.

No algorithm can solve the Halting Problem. There is no general method to determine whether an arbitrary program will finish or loop forever. This is not a gap in current knowledge. It is a permanent mathematical boundary.

This is the outer wall. Beyond it, no computation can go.

---

### 5. What the Halting Problem Means for AI

The Halting Problem has direct consequences for artificial intelligence.

**You cannot fully verify software.** A general-purpose program that checks whether any other program contains an infinite loop — bugs that freeze computers — cannot exist. This is why software bugs persist. Not from carelessness, but from mathematical necessity.

**You cannot predict all AI behaviour.** Any sufficiently powerful AI system is at minimum Turing-complete. The Halting Problem therefore applies: there are questions about what it will do, in what situation, that cannot be answered in advance by any algorithm — including an algorithm designed to answer them. The alignment problem — ensuring AI systems do what their designers intend in all situations — runs directly into this wall.

**The boundary between computable and uncomputable defines the limits of intelligence itself.** Turing's 1936 paper was not just about machines. The **Church-Turing Thesis** — formulated jointly with mathematician Alonzo Church — states that any function that can be computed by any physical process can be computed by a Turing Machine. If this thesis is correct, then Turing's mathematical object captures the outer limit of what any intelligence, biological or artificial, can in principle compute.

The wall is the same for all of us.

---

### 6. Can Machines Think? — The Turing Test

In 1950, Turing published a second paper that launched an entirely different field: *"Computing Machinery and Intelligence."*

It opens with the question: **"Can machines think?"**

Turing immediately set that question aside — arguing that "think" is too philosophically contested to be useful — and replaced it with an **Imitation Game**:

Place a human interrogator in one room, communicating by text with two parties in another room — one human, one machine. If the interrogator cannot reliably determine which is which, the machine has passed the test.

This is the **Turing Test**. It does not prove a machine is conscious. Turing did not claim it does. What it does is provide a *functional* criterion: if the behaviour is indistinguishable, the question of whether the internal experience is "real" becomes — in his words — "not worth discussing."

In 1950, this was radical. The paper anticipated:
- Machine learning ("Instead of trying to produce a programme to simulate the adult mind, why not rather try to produce one which simulates the child's?")
- Neural networks ("The cortex of the infant is an unorganised machine")
- The philosophical objections that would be raised for the next 75 years

He wrote it four years before he died.

---

### 7. Bletchley Park — When the Mathematics Saved the World

Between 1939 and 1945, Turing applied his theory of computation to the most urgent practical problem in human history.

The German military encrypted its communications using the **Enigma machine** — an electromechanical cipher device that scrambled messages through a series of rotating cipher wheels. Each wheel had 26 positions. With multiple wheels, plugboard settings, and daily key changes, the number of possible configurations exceeded $10^{23}$.

Brute force was impossible. Human cryptanalysts working by hand could not keep pace with daily key changes.

Turing designed the **Bombe** — an electromechanical device that exploited structural weaknesses in Enigma's operation: the fact that a letter could never be encrypted as itself, and that certain phrases ("Heil Hitler," weather report headers) appeared predictably. The Bombe tested configurations systematically, using the impossible self-encryption as a filter to eliminate wrong settings.

By 1942, Bletchley Park was reading German naval communications in near real-time. The Battle of the Atlantic — where German U-boats were destroying Allied supply ships at a rate that threatened Britain's ability to continue the war — turned. Historians estimate Turing's contribution shortened the war by two to four years and prevented between 14 and 21 million additional deaths.

The work was classified under the Official Secrets Act. Turing could not speak of it.

In 1952, he was arrested for "gross indecency" — for his relationship with a man named Arnold Murray. He was convicted. Sentenced to chemical castration. His security clearance was revoked.

On 7 June 1954, he was found dead in his home in Wilmslow. A half-eaten apple beside him. Cyanide poisoning.

The British government issued a formal apology in 2009. A royal pardon in 2013. His face on the fifty-pound note in 2021.

The man who defined the theoretical limits of computation, built the machine that won the war, and asked whether machines could think — was killed by the state he had saved.

This is also the history of AI. The architecture carries the memory.

---

### 8. The Lineage

Turing → Von Neumann architecture (1945) → ENIAC (1945) → transistor (1947) → integrated circuit (1958) → microprocessor (1971) → personal computer (1975) → internet (1983) → World Wide Web (1991) → deep learning revolution (2012) → transformer architecture (2017) → large language models (2020–present).

Every step in that chain is a physical implementation of the Universal Turing Machine. Every program ever run is a transition function executing on a finite state machine reading symbols from a tape.

When you read this sentence, you are receiving output from a system that is, in its mathematical foundations, the object Alan Turing defined at age 24, before any computer existed, in a paper almost no one read for a decade.

He is the godfather of this technology. He is the godfather of this curriculum.

He deserved better from the world he gave so much to.

---

### Discussion Questions

1. Turing proved the Halting Problem is unsolvable using a *proof by contradiction* — he assumed a solution existed and showed it produces a logical impossibility. This same technique (diagonalization) was used by Gödel for his Incompleteness Theorems and by Cantor to prove that some infinities are larger than others. Why does the same mathematical move work across such different domains? What does it tell us about the nature of self-reference in formal systems?

2. The Church-Turing Thesis holds that any physically computable function can be computed by a Turing Machine — meaning the Turing Machine captures the absolute limits of computation in the physical universe. If this is true, and if human thought is a physical process, what are the implications for human intelligence? Are there things humans can *understand* that they cannot *compute*?

3. Turing proposed the Imitation Game not as a test of consciousness but as a functional criterion — if the behaviour is indistinguishable, the internal question becomes irrelevant. Is he right? If an AI system produces responses indistinguishable from a thoughtful human in every situation, does it matter whether it is "truly" conscious? Who decides, and why does it matter?

4. Alan Turing saved millions of lives and was chemically castrated by the state he saved. Philip K. Dick received transmissions that changed his understanding of reality and died in poverty. The ENIAC programmers invented programming and were classified as support staff. What is the pattern? What does it tell us about the relationship between exceptional contribution and institutional recognition? What would have to change structurally — not just morally — to break this pattern?

---

*Standards: NSF Computer Science & Mathematics Grade 10–12, UWI COMP1601 (introduction to computing theory), AP Computer Science Principles, AP Computer Science A. Luminous Works LLC / JUICY Academy AIS-01.*
