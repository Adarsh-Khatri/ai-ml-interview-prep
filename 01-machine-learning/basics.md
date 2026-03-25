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

# 3. **What is Underfitting?**

---

**Definition:**
Underfitting occurs when a machine learning model is too simple to capture the underlying patterns in the data, resulting in poor performance on both training data and unseen data.

---

### **Intuition:**

Imagine again you’re preparing for an exam:

* **Good learning:** You understand concepts → solve most questions
* **Overfitting:** You memorize → fail on new questions
* **Underfitting:** You didn’t study properly → you fail even the basic questions

The model is not even able to learn the training data properly.

---

### **Why Underfitting Happens**

1. **Model is Too Simple**

    * Linear model for complex non-linear data
    * Very shallow neural network

2. **Insufficient Training**

    * Model hasn’t learned enough patterns yet
    * Training stopped too early

3. **Too Much Regularization**

    * Over-penalizing the model
    * Forces weights to be too small

4. **Poor Feature Selection**

    * Important features missing
    * Data representation is weak

---

### **Bias-Variance View**

Underfitting = **High Bias + Low Variance**

* **High Bias:** Model makes strong assumptions → misses patterns
* **Low Variance:** Predictions don’t change much → but they are wrong

---

### **How to Detect Underfitting**

1. **Training vs Validation Performance**

    * Training accuracy → Low
    * Validation accuracy → Also Low

Both are bad → clear sign

---

### **How to Fix Underfitting**

1. **Use a More Complex Model**

    * Move from Linear → Polynomial / Neural Network
    * Increase layers / neurons

2. **Train Longer**
    
    * Increase epochs
    * Allow model to learn patterns

3. **Reduce Regularization**

    * Lower L1 / L2 penalty
    * Reduce dropout

4. **Better Features**

    * Feature engineering
    * Add meaningful input variables

---

### **One-Line Revision**
Underfitting is when a model is too simple to learn patterns from data, leading to poor performance on both training and test data.

---
---
---

# 4. Bias vs Variance and the Tradeoff

---

## **What is Bias?**

**Definition:**
Bias is the error caused by overly simplistic assumptions in the model.

---

### **Intuition**

Bias is like having a **fixed mindset**:

* The model assumes a simple pattern
* Ignores complexity in data

Result: It **misses important relationships**

---

### **Example**

Trying to fit a **straight line** to curved data.

---

### **Key Point**

* High Bias → **Underfitting**
* Model is too simple

---

## **What is Variance?**

**Definition:**
Variance is the error caused by the model being too sensitive to small changes in the training data.

---

### **Intuition**

Variance is like being **over-sensitive**:

* Learns every tiny detail (even noise)
* Changes drastically with new data

Result: Poor generalization

---

### **Example**

A very complex curve passing through every data point.

---

### **Key Point**

* High Variance → **Overfitting**
* Model memorizes data

---

## **Bias–Variance Tradeoff (The Core)**

---

### **Meaning**

You cannot minimize both bias and variance at the same time.

> When you decrease one → the other tends to increase.

---

## **Understanding the Tradeoff**

| Model Complexity | Bias     | Variance | Result       |
| ---------------- | -------- | -------- | ------------ |
| Very Simple      | High     | Low      | Underfitting |
| Moderate         | Balanced | Balanced | ✅ Best Model |
| Very Complex     | Low      | High     | Overfitting  |

The goal is to find:

> **Optimal model complexity where both bias and variance are balanced**

At this point:

* Validation error is minimum
* Model generalizes well

---

## **How to Control Bias and Variance**

### **To Reduce Bias (Fix Underfitting)**

* Use a more complex model
* Add more relevant features
* Train for longer

---

### **To Reduce Variance (Fix Overfitting)**

* Collect more data
* Apply regularization (L1 / L2, Dropout)
* Use a simpler model
* Apply cross-validation

---

## **One-Line Revision**

Bias is error due to simplicity, variance is error due to sensitivity, and the tradeoff is finding the right balance between them.

---
---
---

# 5. What is a Dataset?

---

## **Definition**

A dataset is a collection of data points (samples) used to train, validate, and test a machine learning model.

---

## **Intuition**

Think of a dataset as your **study material**

* The model learns from this data
* The quality of learning depends on this data

Better data → Better model

---

## **Basic Structure of a Dataset**

A dataset typically consists of:

### **1. Features (Input Variables)**

* Inputs to the model
* Also called **independent variables**

**Examples:**

* Area of house
* Number of rooms
* Location

---

### **2. Labels (Target / Output)**

* The value we want to predict
* Also called **dependent variable**

**Example:**

* House price

---

## **Types of Datasets**

### **1. Training Dataset**

* Used to train the model
* Model learns patterns from this data

---

### **2. Validation Dataset**

* Used to tune hyperparameters
* Helps detect overfitting

---

### **3. Test Dataset**

* Used to evaluate final performance
* Never seen during training

---

## **Types Based on Data Format**

### **1. Structured Data**

* Organized in tables
* Example: CSV, Excel

---

### **2. Unstructured Data**

* No fixed format
* Example: Images, videos, text

---

### **3. Semi-Structured Data**

* Partially organized
* Example: JSON, XML

---

## **One-Line Revision**
A dataset is a collection of input-output data used to train and evaluate a machine learning model.
