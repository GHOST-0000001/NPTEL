---

# 🧾 WEEK 2 – SUPER MASTER NOTES (FINAL)

---

## 🔹 Neural Network Learning Setup

* Given:

  * Input-output pairs ((x, y))

* Goal:
  [
  \hat{y} = f(x) \approx g(x)
  ]

* Unknown:

  * True function ( g(x) )

* Learning = finding weights such that:

  * prediction ≈ actual
  * loss is minimized

---

## 🔹 Perceptron Learning Recap

* Decision rule:
  [
  W^T X \ge 0 \rightarrow \text{positive}, \quad W^T X < 0 \rightarrow \text{negative}
  ]

* Update rule:

  * Positive misclassified → ( W = W + X )
  * Negative misclassified → ( W = W - X )

* Geometric view:
  [
  W^T X = |W||X|\cos(\theta)
  ]

* Learning adjusts:

  * angle with positive samples → acute
  * angle with negative samples → obtuse

---

## 🔹 Universal Approximation Theorem

* A neural network with:

  * 1 hidden layer
  * sufficient neurons

* Can approximate any function:
  [
  |g(x) - f(x)| < \epsilon
  ]

* Limitation:

  * does NOT tell:

    * number of neurons
    * architecture
    * training method

---

## 🔹 Neural Network Structure

* Input layer → features

* Hidden layers → transformations

* Output layer → final prediction

* Fully connected:

  * each neuron connects to all neurons in next layer

---

## 🔹 Parameter Growth

* Input → hidden:

  * ( m \times n ) weights + ( n ) biases

* Hidden → output:

  * ( n \times p ) weights + ( p ) biases

* Leads to:

  * large parameter count
  * high computation

---

## 🔹 Limitation of Fully Connected Networks

* For images:

  * flattening destroys spatial structure
* Cannot capture:

  * locality
  * spatial patterns

---

## 🔹 Deep Networks

* Use multiple layers instead of one large layer
* Provide:

  * hierarchical learning
  * efficient representation

---

## 🔹 Feature Hierarchy

* Early layers → edges
* Middle layers → shapes
* Deep layers → objects

---

## 🔹 Loss Functions

### Regression:

[
L = \frac{1}{L} \sum (\hat{Y} - Y)^2
]

* Use: Mean Squared Error

---

### Classification:

[
H(P, Q) = -\sum P_i \log Q_i
]

* Use: Cross Entropy

---

### Insight:

* Loss = measure of prediction error
* Training = minimizing loss

---

## 🔹 Information Theory Concepts

* Information:
  [
  I(A) = -\log P(A)
  ]

* Entropy:
  [
  H(P) = -\sum P_i \log P_i
  ]

* Cross Entropy:
  [
  H(P, Q) = -\sum P_i \log Q_i
  ]

---

## 🔹 Generalization vs Fitting

### Underfitting:

* Model too simple
* High error

---

### Good Fit:

* Captures pattern
* Good generalization

---

### Overfitting:

* Model too complex
* Memorizes data

---

## 🔹 Key Goal

* Generalize to unseen data

---

## 🔹 Occam’s Razor

> Prefer simpler models among equally good ones

---

## 🔹 Cost Surface

* Loss depends on:

  * weights + biases

* Properties:

  * non-convex
  * many minima

---

## 🔹 Important Insight

* Global minimum not required
* Good local minimum sufficient

---

## 🔹 Gradient Descent

### Update rule:

[
\theta_{n+1} = \theta_n - \alpha \nabla L(\theta)
]

---

### Key points:

* Move in:

  * negative gradient direction
* Step size (α):

  * small → slow
  * large → unstable

---

### Taylor approximation:

[
L(\theta + \alpha \Delta \theta)
≈ L(\theta) + \alpha \Delta \theta^T \nabla L
]

---

### Optimal direction:

[
\Delta \theta = - \nabla L
]

---

## 🔹 Activation Functions

### Purpose:

* introduce non-linearity

---

### Sigmoid:

* range: (0,1)
* problem: vanishing gradient

---

### Tanh:

* range: (-1,1)
* problem: vanishing gradient

---

### ReLU:

[
f(x) = \max(0,x)
]

* efficient
* widely used

---

### Leaky ReLU:

* avoids dead neurons

---

## 🔹 Important Rule

* Without activation → network becomes linear

---

## 🔹 Backpropagation

### Goal:

* compute gradients efficiently

---

### Key idea:

* propagate error backward

---

## 🔹 Notation

[
Z^l = W^{l-1} A^{l-1} + B^l
]

[
A^l = f(Z^l)
]

---

## 🔹 Delta Definition

[
\delta^l = \frac{\partial L}{\partial Z^l}
]

---

## 🔹 Output Layer Delta

[
\delta^L = (\hat{Y} - Y) \cdot f'(Z^L)
]

---

## 🔹 Hidden Layer Delta

[
\delta^l =
(W^l)^T \delta^{l+1} \cdot f'(Z^l)
]

---

## 🔹 Weight Gradient

[
\frac{\partial L}{\partial W^l}
= \delta^{l+1} (A^l)^T
]

---

## 🔹 Bias Gradient

[
\frac{\partial L}{\partial B^l}
= \delta^{l+1}
]

---

## 🔹 Backprop Flow

1. Forward pass
2. Compute output error
3. Backpropagate delta
4. Compute gradients
5. Update weights

---

## 🔹 Core Insight

* Weight update:

  * depends on:

    * error
    * input

---

## 🔹 Matrix Form (Efficient Computation)

[
\delta^l = (W^l)^T \delta^{l+1} \odot f'(Z^l)
]

[
\frac{\partial L}{\partial W^l} = \delta^{l+1} (A^l)^T
]

---

## 🔹 Final Definition

> Backpropagation is a chain-rule-based method to compute gradients of loss with respect to weights and biases by propagating error backward through the network. 

---

## 🔥 FINAL INTUITION (WEEK 2)

* Network = function
* Loss = error
* Gradient = direction to reduce error
* Backprop = compute gradients
* Gradient descent = update weights

---
