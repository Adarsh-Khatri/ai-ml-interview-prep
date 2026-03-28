# Deep Learning Basics

---
---
---

# 1. What is Deep Learning?

---

## **Definition**

Deep Learning is a subset of Machine Learning that uses multi-layered neural networks (called deep neural networks) to automatically learn complex patterns from large amounts of data.

---

## **Intuition**

Think of Deep Learning as **learning in layers**

* Instead of manually designing features
* The model automatically learns features from data

Each layer learns progressively complex representations:

* First layer → edges
* Next → shapes
* Next → objects

---

## **Real-Life Example**

### **Image Recognition**

Suppose we want to detect a **cat**

* **Traditional Machine Learning:**

  * Manual feature engineering (edges, textures, colors)

* **Deep Learning:**

  * Automatically learns:

    * Edges → ears → face → cat

No manual feature engineering required

---

## **What Makes It “Deep”?**

“Deep” refers to the presence of **multiple layers** in a neural network.

* Shallow model → 1–2 layers
* Deep model → many hidden layers

More layers enable learning of **complex patterns**

---

## **Basic Structure of a Deep Learning Model**

### **1. Input Layer**

* Receives raw data (image, text, audio, etc.)

---

### **2. Hidden Layers**

* Perform computations
* Extract hierarchical features
* Multiple layers = deeper understanding

---

### **3. Output Layer**

* Produces the final prediction

---

## **Types of Deep Learning Models**

* **CNN**
* **RNN/LSTM**
* **Transformers**

---

## **Why Deep Learning Works Well**

* Handles **large-scale data**
* Learns **complex patterns automatically**
* Works effectively with **unstructured data** (images, text, video)

---

## **Limitations**

* Requires **large datasets**
* Needs **high computational power (GPU/TPU)**
* Often behaves like a **black box** (less interpretable)

---

## **One-Line Revision**
Deep Learning is a type of machine learning that uses multi-layer neural networks to automatically learn complex patterns from data.

---
---
---


# 2. What is Convolutional Neural Networks (CNN)

---

## **1. Overview**

A Convolutional Neural Network (CNN) is a deep learning architecture designed to process data with **grid-like structure** (e.g., images), using convolution operations to efficiently learn spatial hierarchies.

---

## **2. Why CNN Instead of Fully Connected Networks?**

### **Problem with Fully Connected Layers**

* For an image of size (224 \times 224 \times 3):

  * Parameters become extremely large
  * No spatial structure is preserved

---

### **CNN Solution**

* **Local Connectivity** → Focus on small regions
* **Parameter Sharing** → Same filter reused
* **Spatial Awareness** → Preserves image structure

---

## **3. Mathematical Formulation**

### **Convolution Operation**

Y(i,j) = \sum_m \sum_n X(i+m, j+n) \cdot W(m,n)

* (X): Input
* (W): Kernel (filter)
* (Y): Output feature map

---

## **4. Tensor Representation**

* **Input:**
  (X \in \mathbb{R}^{H \times W \times C})

* **Kernel:**
  (W \in \mathbb{R}^{k \times k \times C})

* **Output:**
  (Y \in \mathbb{R}^{H' \times W' \times F})

---

## **5. Output Size Calculation**

\frac{N - F + 2P}{S} + 1

Where:

* (N): Input size
* (F): Filter size
* (P): Padding
* (S): Stride

---

## **6. CNN Building Blocks**

### **6.1 Convolution Layer**

* Applies filters to extract features
* Each filter detects specific patterns

$$
Y_f = X * W_f + b_f
$$

---

### **6.2 Activation (ReLU)**

f(x) = \max(0, x)

* Introduces non-linearity
* Prevents linear model collapse

---

### **6.3 Pooling Layer**

* Reduces spatial dimensions
* Keeps important information

**Max Pooling:**

y = \max(x_{ij})

---

### **6.4 Fully Connected Layer**

* Flattens features
* Performs classification

---

## **7. Hierarchical Feature Learning**

| Layer Depth | Features Learned   |
| ----------- | ------------------ |
| Shallow     | Edges, gradients   |
| Mid-level   | Textures, patterns |
| Deep        | Objects, semantics |

---

## **8. Important Variants**

### **Strided Convolution**

* Downsampling via stride

### **Dilated Convolution**

* Larger receptive field without more parameters

### **Batch Normalization**

* Stabilizes training

### **Dropout**

* Prevents overfitting

---

## **9. Popular Architectures**

* **LeNet** → Early CNN
* **AlexNet** → Breakthrough model
* **VGG** → Deep architecture
* **ResNet** → Skip connections (very important)

---

## **10. Complexity Advantage**

Compared to fully connected networks:

$$
O(n^2) \rightarrow O(k^2)
$$

Significant parameter reduction

---

## **11. One-Line Revision**

CNN is a deep learning architecture that efficiently learns spatial hierarchies using convolution, parameter sharing, and local connectivity.
