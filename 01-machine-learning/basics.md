# Machine Learning Basics

---
---
---

# 1. **What is Machine Learning?**

**Definition:**
Machine Learning is a subset of Artificial Intelligence that enables systems to learn patterns from data and make predictions or decisions without being explicitly programmed.

**Intuition:**
Instead of writing rules manually, we allow the model to learn relationships directly from data.

**Example:**
Predicting house prices using features like area, location, and number of rooms.

**One-line Revision:**
Models learn patterns from data instead of being explicitly programmed.

---
---
---

# 2. **What is Overfitting?**

**Definition:**
Overfitting occurs when a machine learning model learns not only the underlying pattern in the training data but also the noise, randomness, and irrelevant details, resulting in excellent training performance but poor generalization to unseen data.

---

### **Intuition**

Imagine you are preparing for an exam:

* **Good learning:** You understand concepts → you can solve new questions
* **Overfitting:** You memorize exact answers → if the question changes slightly, you fail

The model is not learning concepts — it is memorizing the data.

---

### **Why Overfitting Happens**

1. **Model is Too Complex**

   * Deep neural network with too many parameters
   * High-degree polynomial

2. **Small Dataset**

   * Model memorizes instead of learning

3. **Too Many Features**

   * Irrelevant features introduce noise

4. **Too Much Training**

   * Model starts memorizing late-stage noise

---

### **Bias-Variance View**

Overfitting = **Low Bias + High Variance**

* **Low Bias:** Fits training data well
* **High Variance:** Sensitive to small changes in data

---

### **How to Detect Overfitting**

1. **Training vs Validation Curve**

   * Training accuracy ↑
   * Validation accuracy ↓

2. **Large Gap Between Train & Test Accuracy**

---

### **How to Prevent Overfitting**

1. **More Data**

   * Best solution — reduces memorization

2. **Regularization**

   * L1 / L2
   * Dropout (in deep learning)

3. **Simpler Model**

   * Reduce layers / parameters

4. **Early Stopping**

   * Stop training before memorization starts

5. **Cross Validation**

   * Ensures model generalization

---

### **One-Line Revision**

Overfitting is when a model memorizes training data (including noise) instead of learning general patterns, leading to poor performance on unseen data.

---
---
---