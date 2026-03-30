# Natural Language Processing Basics

---

## 🔗 Quick Navigation (Click to Jump)

- [1. What is RNN?](#1-what-is-rnn)

---

---
---
---


# Recurrent Neural Network (RNN)

---

## Definition
A **Recurrent Neural Network (RNN)** is a type of deep neural network designed for **sequential data**, where the output at a given time step depends on both the **current input** and the **previous hidden state (memory)**.

---

## Intuition

Traditional neural networks assume inputs are independent.  
However, in real-world data like **text, video, and time series**, the **order matters**.

RNN introduces a **hidden state** that acts as memory and carries information across time steps.

### Example:
"I went to the bank"

- Understanding "bank" depends on previous words  
- This context is captured by the hidden state  

---

## Working Mechanism

At each time step \( t \):

$$
h_t = \tanh(W_x x_t + W_h h_{t-1} + b)
$$

$$
y_t = W_y h_t + c
$$

### Where:
- \( x_t \): input at time step \( t \)  
- \( h_t \): hidden state (current memory)  
- \( h_{t-1} \): previous hidden state  
- \( y_t \): output  
- \( W_x, W_h, W_y \): weight matrices  
- \( b, c \): bias terms  

---

## Unrolling the RNN

RNN can be visualized as being **unrolled across time**:


Same weights are reused at every time step.

---

## Key Concepts

### 1. Hidden State (Memory)
- Stores past information  
- Updated at every time step  

### 2. Weight Sharing
- Same weights across all time steps  
- Reduces number of parameters  

### 3. Sequential Processing
- Processes input step-by-step  
- Cannot be fully parallelized  

---

## Types of RNN Architectures

### 1. One-to-One
- Single input → single output  
- Example: Image classification  

### 2. One-to-Many
- Single input → sequence output  
- Example: Image captioning  

### 3. Many-to-One
- Sequence input → single output  
- Example: Sentiment analysis  

### 4. Many-to-Many
- Sequence input → sequence output  
- Example: Machine translation  

---

## Training: Backpropagation Through Time (BPTT)

RNN is trained using **Backpropagation Through Time**.

$$
\frac{\partial L}{\partial W} = \sum_{t=1}^{T} \frac{\partial L_t}{\partial W}
$$

Gradients are computed across all time steps.

---

## Challenges in RNN

---

### 1. Vanishing Gradient Problem

$$
\left( \frac{\partial h_t}{\partial h_{t-1}} \right)^k \rightarrow 0
$$

- Gradients become very small  
- Model fails to learn long-term dependencies  

---

### 2. Exploding Gradient Problem

$$
\left( \frac{\partial h_t}{\partial h_{t-1}} \right)^k \rightarrow \infty
$$

- Gradients become very large  
- Training becomes unstable  

---

### 3. Long-Term Dependency Problem

- Difficulty remembering information from distant time steps  

---

## Disadvantages

- Slow training due to sequential computation  
- Hard to parallelize  
- Suffers from vanishing/exploding gradients  
- Poor performance on long sequences  

---

## Limitations

- Limited memory capacity  
- Cannot effectively capture long-range dependencies  
- Information from early time steps is lost  
- Not suitable for very long sequences  

---

## Advantages

- Handles sequential data effectively  
- Captures temporal dependencies  
- Parameter sharing reduces complexity  
- Works well for text, speech, video  

---

## Improvements over RNN

To overcome limitations:

- **LSTM (Long Short-Term Memory)**  
- **GRU (Gated Recurrent Unit)**  

These use gating mechanisms to retain important information.

---

## Applications

- Natural Language Processing (NLP)  
- Speech recognition  
- Video analysis  
- Time series forecasting  

---

## RNN in Practice

In video-based tasks:

- CNN extracts features from each frame  
- RNN/LSTM captures temporal relationships  

Example:
Frame1 → Frame2 → Frame3 → Action detection  

---

## One-Line Revision

"RNN is a neural network for sequential data that uses a hidden state to remember past information and capture temporal dependencies."

---