# AIS-05: The Attention Mechanism
## Artificial Intelligence — Lesson 5

**Core concept:** Self-attention · The Transformer architecture · "Attention Is All You Need" · How language models work  
**Duration:** 90 minutes  
**Prerequisites:** AIS-04 (gradient descent, neural networks)  
**Publication of record:** Vaswani, Shazeer, Parmar, Uszkoreit, Jones, Gomez, Kaiser & Polosukhin — *"Attention Is All You Need"*, NeurIPS 2017

---

### Opening Statement

> *"The model described in this paper is not a recurrent network. It does not process language sequentially. It looks at every word in relation to every other word, simultaneously, all at once."*  
> — Paraphrase of the central claim of Vaswani et al., 2017

In 2017, eight researchers at Google published a 15-page paper with an absurd title: **"Attention Is All You Need."**

It was not a modest claim. The recurrent neural network (RNN) had dominated natural language processing for a decade. Researchers had spent years solving its problems. The paper discarded it entirely.

The architecture they proposed — the **Transformer** — became the foundation of GPT, BERT, Claude, Gemini, Llama, and every major language model built since 2018.

This lesson teaches you how it works. The mathematics is not optional. You cannot understand what you are using until you understand what is happening inside it.

---

### 1. The Problem: Why RNNs Failed

Before Transformers, the dominant architecture for language was the **Recurrent Neural Network (RNN)**.

An RNN processes a sequence one token at a time, maintaining a "hidden state" — a compressed representation of everything seen so far — that gets updated at each step:

```
h_t = f(W_h × h_{t-1} + W_x × x_t)
```

The problem: **vanishing gradients across long sequences.**

By the time the gradient flows back from the end of a long sentence to the beginning, it has been multiplied by thousands of small numbers and is effectively zero. The network cannot learn relationships between words that are far apart.

In the sentence: *"The bauxite mined in the Cockpit Country, whose water table feeds nearly half the island's population through a labyrinthine karst conduit system, flows eventually to the sea"* — an RNN loses the connection between "bauxite" and "flows" by the time it gets there. The intervening clause is too long.

**LSTMs (Long Short-Term Memory networks)** were invented to partially solve this — adding explicit memory gates. They helped. They did not fully solve it. And they were slow to train because they must process tokens sequentially: you cannot parallelize a recurrent computation.

---

### 2. The Key Insight: Every Word Should Look at Every Other Word

The core idea of the Transformer is conceptually simple:

**Instead of processing sequentially, let every position in the sequence attend to every other position simultaneously.**

When you read the word "mined" in a sentence about Jamaica, your brain instantly relates it to "bauxite" and "Cockpit Country." You don't have to reach back through a chain of hidden states. You see the whole sentence at once.

The Transformer formalizes this: each token produces a query, and attends to all other tokens' keys. The relevance between any two positions can be computed directly, regardless of distance.

---

### 3. Attention: Query, Key, Value

The attention mechanism uses three matrices derived from the input:

- **Query (Q)**: "What am I looking for?"
- **Key (K)**: "What do I contain?"
- **Value (V)**: "What information do I provide?"

These are learned linear transformations of the input embedding X:

```
Q = X × W_Q
K = X × W_K
V = X × W_V
```

Where W_Q, W_K, W_V are learned weight matrices.

**The attention formula:**

```
Attention(Q, K, V) = softmax( QK^T / √d_k ) × V
```

Step by step:
1. **QK^T** — dot product between every query and every key. Produces a matrix where entry (i,j) scores how relevant position j is to position i.
2. **/ √d_k** — scale by the square root of the key dimension. Without this, dot products become large in high dimensions, pushing softmax into regions where gradients vanish.
3. **softmax(...)** — convert scores to probabilities. Each row sums to 1. This is the attention weight: how much each position should contribute to the output.
4. **× V** — weighted sum of values. Each output position is a blend of all value vectors, weighted by how relevant each position was.

**Dimensions:**
- Q, K: shape (sequence_length, d_k)
- V: shape (sequence_length, d_v)
- Output: shape (sequence_length, d_v)

---

### 4. Multi-Head Attention

A single attention operation might capture one type of relationship (syntactic, semantic, proximity). **Multi-head attention** runs h parallel attention operations:

```
MultiHead(Q, K, V) = Concat(head_1, ..., head_h) × W_O

where head_i = Attention(QW_Q_i, KW_K_i, VW_V_i)
```

Each head has its own learned weight matrices (W_Q_i, W_K_i, W_V_i). The h heads can specialize:
- One head might attend to syntactic dependencies
- Another to semantic similarity
- Another to positional proximity

The outputs are concatenated and projected back down by W_O.

In GPT-3: h = 96 heads, d_k = 128, d_model = 12288. The model maintains 96 simultaneous, specialized views of every sequence it processes.

---

### 5. Positional Encoding — Teaching the Model Where Things Are

Self-attention is **permutation-invariant**: shuffle the words and the attention scores are the same (just shuffled). The model has no inherent sense of order.

To encode position, the Transformer adds a **positional encoding** to the input embedding before attention:

```
PE(pos, 2i)   = sin( pos / 10000^(2i/d_model) )
PE(pos, 2i+1) = cos( pos / 10000^(2i/d_model) )
```

These sine and cosine functions at different frequencies give each position a unique vector fingerprint. The model can learn to use this positional information during training.

Newer models use **Rotary Position Embeddings (RoPE)** or **ALiBi** — more sophisticated schemes that generalize better to sequence lengths not seen during training. But the sine/cosine method from the original paper remains elegant and instructive.

---

### 6. The Full Transformer Block

A single Transformer block:

```
Input X
  ↓
LayerNorm
  ↓
Multi-Head Self-Attention  →  + residual (X)
  ↓
LayerNorm
  ↓
Feed-Forward Network (2 linear layers, ReLU in between) → + residual
  ↓
Output
```

**Residual connections** (the "+ X" terms) add the input directly to the output of each sublayer. This prevents vanishing gradients in very deep stacks of Transformer blocks.

**Layer normalization** stabilizes training by normalizing the activations within each sample (not across the batch).

**The feed-forward network** is applied identically to each position independently — it adds depth and nonlinear capacity beyond what attention provides.

A complete model stacks N of these blocks. GPT-3 uses N = 96 layers.

---

### 7. The Encoder-Decoder vs. Decoder-Only

The original Transformer had two components:

**Encoder:** processes the input sequence (e.g., a sentence in French)
**Decoder:** generates the output sequence (e.g., the translation in English)

The decoder uses **cross-attention** — it attends to the encoder's output as well as its own previous outputs.

This architecture is used by translation models (T5, BART).

**BERT (Bidirectional Encoder Representations from Transformers, Google 2018):** encoder only. Sees the full sequence in both directions. Good for classification and understanding.

**GPT (Generative Pre-trained Transformer, OpenAI 2018):** decoder only. Generates text left-to-right. Each position can only attend to previous positions (causal mask). This is how language generation works.

**Claude, GPT-4, Gemini:** all decoder-only Transformers at their core, with various modifications to training, alignment, and scale.

---

### 8. Pre-Training and Fine-Tuning

A Transformer is first **pre-trained** on a massive corpus:
- GPT-3: ~300 billion tokens from web text, books, code
- The training objective: predict the next token

At the start, the model has random weights. It predicts randomly. The loss is high. Backpropagation adjusts every parameter. After training on hundreds of billions of examples, the model has compressed extraordinary amounts of linguistic and factual structure into its weights.

Then **fine-tuning**: the pre-trained model is further trained on specific tasks:
- Instruction following
- Safety alignment (RLHF — Reinforcement Learning from Human Feedback)
- Domain specialization (medical, legal, scientific)

The pre-trained weights represent general capability. Fine-tuning steers the behavior.

---

### 9. The Complexity Problem

Self-attention is **quadratic in sequence length**:
- For a sequence of length n, the attention matrix is n × n
- Computing it requires O(n²) operations

For n = 1000 tokens: 1,000,000 operations.  
For n = 100,000 tokens (a short book): 10,000,000,000 operations.

This is why "context window" is a real technical constraint. Processing very long documents is computationally expensive.

Research into **linear attention**, **sparse attention**, and **state space models** (Mamba, RWKV) is active — attempts to process long sequences more efficiently.

---

### 10. What the Model Actually Knows

A Transformer language model does not "understand" language the way you do. It does not have beliefs, experiences, or consciousness (see AIS-09).

It has compressed the statistical regularities of an enormous text corpus into a 175-billion-parameter lookup structure. When it generates text, it is computing: "given everything I've seen so far, what is the probability distribution over the next token?"

This is staggeringly powerful. It has encoded grammar, facts, reasoning patterns, code, poetry, mathematics.

But it is not understanding. The distinction matters enormously — for alignment, for safety, for how we deploy these systems in the Caribbean and everywhere else.

---

### Caribbean Application: Creole and Patois

Language models trained primarily on standard English perform poorly on Jamaican Patois, Haitian Creole, and other Caribbean creole languages. The attention mechanism can in principle represent any language — but only if that language is in the training data.

Jamaican Patois is spoken by approximately 2.5 million people. The amount of Patois text on the internet is vanishingly small compared to English. A language model's "knowledge" of Patois is therefore thin, distorted by code-switching contexts, and likely to hallucinate.

This is not a technical problem. It is a data curation problem. It is a political problem: whose language is legible to the machine?

Building better NLP for Caribbean languages requires:
1. Curated, labeled corpora of Patois, Creole, and other Caribbean languages
2. Multilingual pre-training that includes these languages
3. Fine-tuning on Caribbean-specific tasks (medical advice in Patois, legal documents in Creole)

This is work that must be done here, by people who speak these languages.

---

### Review Questions

1. What is the key mathematical operation in self-attention? Write the formula and explain each term.

2. Why is the scaling factor √d_k important in the attention formula?

3. A sequence has 512 tokens. The attention matrix is 512 × 512. How many entries does this matrix have? What does this mean for very long sequences?

4. Explain the difference between a BERT-style encoder and a GPT-style decoder. Which one generates text? Why?

5. Why do language models perform poorly on Jamaican Patois? What would it take to fix this?

---

### Glossary

| Term | Definition |
|------|-----------|
| Self-attention | Mechanism by which each position in a sequence attends to all other positions |
| Query / Key / Value | The three projections used to compute attention scores and outputs |
| Multi-head attention | Parallel attention operations with different learned projections |
| Positional encoding | A signal added to token embeddings to give the model a sense of order |
| Transformer block | The repeating unit: LayerNorm → MHA → residual → LayerNorm → FFN → residual |
| Causal mask | Restriction preventing each position from attending to future positions |
| Pre-training | Initial training on massive corpora via next-token prediction |
| Fine-tuning | Further training to adapt a pre-trained model to specific behavior or tasks |
| Context window | Maximum sequence length the model can process in one forward pass |

---

*JUICY Academy — AIS-05 — Luminous Works LLC*  
*Standards: AP Computer Science Principles · UWI COMP1601 · NSF Computational Thinking*
