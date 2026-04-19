# AIS-04: The Mathematics of Learning
## Artificial Intelligence — Lesson 4

**Core concept:** The Perceptron · Gradient Descent · Backpropagation · How a neural network learns from error  
**Duration:** 90 minutes  
**Prerequisites:** AIS-01 (Turing), AIS-02 (Manhattan Project), AIS-03 (Industrial AI)  
**Mathematics level:** Calculus — partial derivatives, chain rule

---

### Opening Statement

> *"You don't need to be a genius to understand how machines learn. You need to understand how to follow a hill downward in the dark."*

Every AI system you have ever used — every recommendation, every autocomplete, every image classifier, every language model — was trained using a set of mathematical ideas that were mostly worked out between 1957 and 1986.

The mathematics is not magic. It is calculus applied to geometry.

This lesson teaches you the actual mechanics. The equations. The intuition. By the end of this lesson, you will understand what "training" an AI actually means — not as a metaphor, but as a mathematical process.

---

### 1. The Perceptron — The First Artificial Neuron

**Frank Rosenblatt. 1957. Cornell University.**

Rosenblatt was a psychologist trying to model how biological neurons fire. He built a machine called the Mark I Perceptron. It could learn to recognize simple visual patterns.

A perceptron is the simplest possible neural network: a single artificial neuron.

**How it works:**

A perceptron takes n input values (x₁, x₂, ..., xₙ), multiplies each by a weight (w₁, w₂, ..., wₙ), sums them, and passes the result through an activation function.

```
output = f( w₁x₁ + w₂x₂ + ... + wₙxₙ + b )
```

Where:
- **x** = input features (the data)
- **w** = weights (what the network has learned)
- **b** = bias (a constant offset)
- **f** = activation function (determines if the neuron "fires")

The simplest activation function is the step function:
- If the weighted sum > 0 → output 1 (fires)
- Otherwise → output 0 (silent)

**The learning rule:**

If the perceptron makes an error, update the weights:

```
w_new = w_old + learning_rate × (target - output) × input
```

This is the **perceptron learning rule**. If the network says 0 when it should say 1, increase the relevant weights. If it says 1 when it should say 0, decrease them.

The key insight: **the network adjusts itself based on its own mistakes.**

---

### 2. The XOR Problem — Why One Neuron Is Not Enough

In 1969, Marvin Minsky and Seymour Papert published *Perceptrons*, a book proving that a single-layer perceptron cannot solve the XOR problem.

**XOR (Exclusive OR):**
| Input A | Input B | XOR Output |
|---------|---------|------------|
| 0       | 0       | 0          |
| 0       | 1       | 1          |
| 1       | 0       | 1          |
| 1       | 1       | 0          |

Plot these four points on a 2D grid. There is no single straight line you can draw that separates the 1s from the 0s.

A single perceptron can only create a **linear decision boundary** — one straight line in input space. XOR requires a curved or multi-segment boundary.

This discovery killed perceptron research funding for almost a decade.

The solution was multi-layer networks. But to train them, you needed an algorithm that didn't exist yet.

---

### 3. The Loss Function — Defining "Wrong"

Before a network can learn, you must define what "correct" means mathematically.

A **loss function** measures how wrong the network's prediction is compared to the true answer.

**Mean Squared Error (MSE):**
```
L = (1/n) × Σ(y_pred - y_true)²
```
Good for regression (predicting continuous values).

**Cross-Entropy Loss:**
```
L = -Σ y_true × log(y_pred)
```
Good for classification (predicting categories). This is what most AI classifiers use.

The loss function maps every possible set of weights onto a single number: the network's current error. Your goal in training is to find the weights that make this number as small as possible.

---

### 4. Gradient Descent — Walking Downhill in the Dark

Imagine the loss function as a mountainous landscape. Every point in the landscape represents a different set of weights. The height at each point is the loss — the error.

Your goal: find the lowest valley.

You cannot see the whole landscape. You can only feel the slope under your feet.

**Gradient descent** is the algorithm for walking downhill:

1. Start at a random position in weight space
2. Calculate the slope (gradient) at your current position
3. Take a step in the direction of steepest descent
4. Repeat until you reach a minimum

Mathematically:
```
w = w - α × ∂L/∂w
```

Where:
- **w** = current weight
- **α** = learning rate (step size)
- **∂L/∂w** = gradient of the loss with respect to the weight

The **learning rate** is critical:
- Too large: you overshoot the minimum, bounce around, never converge
- Too small: training takes forever
- Just right: you descend steadily to a good minimum

---

### 5. Backpropagation — The Chain Rule at Scale

In a deep network with many layers, how do you calculate the gradient of the loss with respect to weights in early layers? The output depends on many operations in sequence.

**Backpropagation** solves this using the **chain rule** from calculus.

**Chain rule (single variable):**
```
d/dx[f(g(x))] = f'(g(x)) × g'(x)
```

**Chain rule for neural networks:**

For a network with layers L₁ → L₂ → L₃ → Loss:

```
∂Loss/∂w₁ = (∂Loss/∂L₃) × (∂L₃/∂L₂) × (∂L₂/∂L₁) × (∂L₁/∂w₁)
```

You compute the gradient at the output, then propagate it **backward** through every layer, multiplying by the local gradient at each step.

**Algorithm:**
1. **Forward pass**: run the network, compute the output and the loss
2. **Backward pass**: propagate the gradient from the loss back through every layer
3. **Update**: adjust every weight using the computed gradients

This is backpropagation. It was formalized for neural networks in 1986 by Rumelhart, Hinton, and Williams — and it is still the algorithm that trains every neural network today.

---

### 6. Activation Functions — The Nonlinearity That Makes Deep Learning Possible

Without nonlinearity, stacking layers of linear functions produces only another linear function. Deep networks only gain expressive power from **nonlinear activation functions**.

**Sigmoid:**
```
σ(x) = 1 / (1 + e^(-x))
```
Output range: (0, 1). Was the standard for years. Problem: gradient vanishes for very large or very small inputs.

**ReLU (Rectified Linear Unit):**
```
f(x) = max(0, x)
```
Output: 0 if negative, x if positive. Simple. Fast. Works surprisingly well. Now the most common activation in hidden layers.

**Softmax (for output layer in classifiers):**
```
softmax(xᵢ) = e^(xᵢ) / Σ e^(xⱼ)
```
Converts raw scores into a probability distribution. All outputs sum to 1.

---

### 7. The Full Training Loop

```python
# Pseudocode for training a neural network

for epoch in range(num_epochs):
    for batch in dataloader:
        # Forward pass
        predictions = model(batch.inputs)
        loss = loss_function(predictions, batch.targets)
        
        # Backward pass
        loss.backward()          # compute gradients via backprop
        
        # Weight update
        optimizer.step()         # gradient descent: w = w - α × ∂L/∂w
        optimizer.zero_grad()    # reset gradients for next batch
```

That loop — forward, backward, update — is what "training" an AI means. Run it millions of times on millions of data points, and the weights gradually shift to encode whatever pattern the data contains.

---

### 8. The Vanishing Gradient Problem

In very deep networks (many layers), the gradients computed during backpropagation can become **exponentially small** as they propagate toward earlier layers.

Each multiplication by a partial derivative < 1 makes the gradient smaller. After 50 layers, the gradient might be 10⁻³⁰ — effectively zero. Early layers stop learning.

This is why sigmoid activations fell out of favor — their gradient is at most 0.25, guaranteeing exponential decay in deep networks.

Solutions:
- **ReLU** (gradient = 1 for positive inputs, doesn't decay)
- **Residual connections** (skip connections that add the input directly to the output, preserving gradient flow)
- **Layer normalization** (normalizes activations to prevent explosion or vanishing)

The residual connection was the key innovation that made networks with 50, 100, 1000 layers trainable. It was introduced in **ResNet (He et al., 2015, Microsoft Research)**. Every major deep learning architecture since uses some form of it.

---

### Caribbean Application: Pattern Recognition in Disease Diagnosis

Sickle cell disease affects approximately 1 in 12 Jamaicans of African descent. Malaria remains a regional risk. Dengue fever is endemic across the Caribbean.

Neural networks trained on clinical data — blood cell images, temperature patterns, symptom sequences — are being deployed in resource-limited settings in the Caribbean and across sub-Saharan Africa to assist diagnosis where specialist physicians are scarce.

The mathematics in this lesson is the same mathematics keeping people alive.

When Dr. Cicely Williams (WIS-06) worked in Jamaica and Ghana diagnosing kwashiorkor, she had only her eyes and her training. The tools being built today compress decades of clinical pattern recognition into gradient descent on a hundred thousand examples.

The question this raises for you: **who owns the data the network trains on, and whose health outcomes were used to teach the machine?**

---

### 9. Dimensions of a Modern Network

To give you a sense of scale:

| Model | Parameters | Approximate Training Cost |
|-------|-----------|--------------------------|
| GPT-2 (2019) | 1.5 billion | ~$50,000 |
| GPT-3 (2020) | 175 billion | ~$4.6 million |
| GPT-4 (2023) | ~1.8 trillion | ~$100 million |
| Claude 3 Opus | Undisclosed | Comparable range |

Every one of those parameters is a number — a weight — updated by backpropagation during training. The mathematics in this lesson scaled to sizes Rosenblatt could not have imagined.

---

### Review Questions

1. A perceptron has three inputs: x₁ = 0.5, x₂ = -1.0, x₃ = 2.0, with weights w₁ = 0.8, w₂ = 0.5, w₃ = -0.3 and bias b = 0.2. Calculate the weighted sum. Does the step function produce 0 or 1?

2. Why can a single perceptron not solve the XOR problem? Draw a diagram.

3. If the learning rate is too large, what happens during gradient descent? What happens if it is too small?

4. Explain the vanishing gradient problem. Why is ReLU better than sigmoid for deep networks?

5. You are training a network to diagnose dengue fever from blood cell images. What would your loss function measure? What does a "correct" training example look like?

---

### Glossary

| Term | Definition |
|------|-----------|
| Perceptron | A single artificial neuron performing weighted sum + activation |
| Loss function | A mathematical measure of the network's prediction error |
| Gradient descent | An optimization algorithm that minimizes loss by following the negative gradient |
| Backpropagation | Algorithm for computing gradients through a network using the chain rule |
| Learning rate (α) | Step size for each gradient descent update |
| ReLU | Rectified Linear Unit — the activation function f(x) = max(0,x) |
| Vanishing gradient | Exponential decay of gradients in deep networks, preventing early layers from learning |
| Parameters | The learnable weights and biases of a neural network |

---

*JUICY Academy — AIS-04 — Luminous Works LLC*  
*Standards: AP Computer Science Principles · UWI COMP1601 · NSF Computational Thinking*
