Modern Computer Vision - Week 1 MASTER NOTES (Full Detailed)

1. INTRODUCTION TO COMPUTER VISION

Computer Vision is the field of enabling machines to interpret and understand visual data (images/videos).

Key Problem:
Computers see images as matrices of numbers (pixel intensities), while humans interpret them as meaningful objects and scenes.

Example:
Image → [255, 0, 120, ...] (computer view)  
Human → “person sitting in a room”

Goal:
Convert numerical representation → semantic understanding.

Why is it difficult?
- Humans use memory, context, and prior knowledge
- Machines rely only on data
- Human visual system itself is not fully understood


2. LEVELS OF COMPUTER VISION

To handle complexity, CV is divided into levels:

Low-Level Vision:
- Edge detection
- Filtering
- Noise removal
- Works directly on pixels

Mid-Level Vision:
- Feature grouping
- Shape detection
- Object parts

High-Level Vision:
- Object recognition
- Scene understanding
- Semantic interpretation

Pipeline:
Pixels → Edges → Features → Structure → Meaning


3. TYPES OF INFORMATION

Semantic Information:
- What is present in the image
- Example: car, person, building

Metric Information:
- Where is it, how far is it
- Example: distance, depth, position


4. DEPTH ESTIMATION

Parallax Concept:
- Near objects move more
- Far objects move less

Stereo Vision:
- Two cameras (like human eyes)
- Compare displacement → compute depth

Structure from Motion (SfM):
- Single moving camera
- Multiple images → reconstruct 3D structure

Challenges:
- Matching points across images
- Camera motion estimation


5. COMPUTER VISION TASKS

Image Classification:
- Assign one label
- Example: dog, cat

Object Detection:
- Detect object + location (bounding box)

Segmentation:
- Pixel-wise classification

Tracking:
- Follow object across frames

Pose Estimation:
- Detect body joints

Activity Recognition:
- Identify actions


6. MACHINE LEARNING TYPES

Supervised Learning:
- Uses labeled data
- Example: image → label

Unsupervised Learning:
- No labels
- Example: clustering, PCA

Self-Supervised Learning:
- Uses data structure itself
- Example: predicting depth from image sequences


7. TRADITIONAL VS DEEP LEARNING

Traditional CV:
- Handcrafted features (SIFT, HOG)
- Separate classifier (SVM)

Deep Learning:
- End-to-end learning
- Automatic feature extraction
- Learns hierarchical features


8. PERCEPTRON (NEURON MODEL)

Equation:
y = 1 if (w.x ≥ θ), else 0

Steps:
1. Multiply inputs with weights
2. Sum them
3. Compare with threshold
4. Output binary result

Interpretation:
- Linear classifier
- Creates decision boundary (line)


9. LINEAR SEPARABILITY

If data can be separated using a straight line → linearly separable

Example:
OR gate → separable  
XOR gate → not separable


10. XOR PROBLEM

Truth Table:
(0,0) → 0  
(0,1) → 1  
(1,0) → 1  
(1,1) → 0  

Cannot be separated by one line → perceptron fails


11. MULTILAYER PERCEPTRON (MLP)

Solution:
Use multiple neurons + hidden layers

Structure:
Input → Hidden → Output

Hidden layer:
- Creates multiple linear boundaries
- Combines them to form non-linear boundary

Key Idea:
Multiple lines → complex shapes


12. NON-LINEARITY

Without activation:
- Network is linear
- Equivalent to single perceptron

With activation:
- Enables complex decision boundaries

Conclusion:
Non-linearity is essential


13. PERCEPTRON LEARNING ALGORITHM (PLA)

Goal:
Learn weights automatically

Steps:
1. Initialize weights randomly
2. For each data point:
   - If positive misclassified → W = W + X
   - If negative misclassified → W = W - X

Effect:
Adjusts decision boundary

Limitation:
Works only if data is linearly separable


14. UNIVERSAL APPROXIMATION THEOREM

Statement:
A neural network with one hidden layer can approximate any continuous function.

Implication:
Neural networks are universal function approximators

Limitations:
- Needs sufficient neurons
- Needs proper training


15. DEEP LEARNING INSIGHTS

Success Factors:
- Large datasets
- GPU computing
- Better algorithms

Limitations:
- Needs data
- Not interpretable
- Can fail in real-world conditions


FINAL INTUITION

Perceptron → draws a line  
MLP → combines multiple lines  
Deep Network → approximates complex functions


---

WEEK 1

# 🧾 Week 1 – Video 1 (With Explanation)

## 📌 1. What is Computer Vision?

Computer Vision =

> Teaching a machine to **understand images like humans do**

### Problem:

* Computer sees: **numbers (pixels)**
* You see: **objects + meaning**

Example:

* Image = matrix like `[255, 0, 120...]`
* You = “that’s a person sitting”

👉 So the whole field is:

> Convert **numbers → meaning**

---

## 📌 2. Why this is hard

Humans are annoyingly good at vision.

You can:

* Recognize a friend in bad lighting
* Recognize objects from weird angles
* Use context automatically

Machines:

* Need thousands of examples
* Still mess up if lighting changes

Even worse:

> We don’t fully understand how *our own brain* does this 

So yeah, we’re trying to replicate something we don’t fully understand. Great plan.

---

## 📌 3. Breaking the problem (very important)

Since full understanding is too hard, we split it:

### 🔹 Low-Level Vision

Basic stuff:

* edges
* brightness
* filters

👉 Think: “raw pixel processing”

---

### 🔹 Geometry

Understanding **space and position**

* Where is object?
* How far is it?

👉 This is where depth comes in

---

### 🔹 Mid-Level Vision

Combine features:

* edges → shapes
* shapes → structures

---

### 🔹 High-Level Vision

Actual understanding:

* “this is a car”
* “this is a classroom”

---

### 🔥 Easy way to remember:
Pixels → Features → Structure → Meaning

---

## 📌 4. Two Types of Information

### 🔸 (A) Semantic = Meaning

Answers:

* What is this?

Examples:

* dog
* building
* road

👉 Used in:

* classification
* object detection
* segmentation

---

### 🔸 (B) Metric = Measurement

Answers:

* Where is it?
* How far is it?

Examples:

* distance = 5m
* object is in front/back

---

### ⚠️ Important:

* Semantic = **understanding**
* Metric = **measurement**

---

## 📌 5. Example: Semantic Vision

Imagine an image:

* sky
* building
* car

Computer labels each part.

👉 That’s **modern deep learning vision**

---

## 📌 6. Why old methods still matter

Before deep learning:

* Humans designed features manually

Now:

* Networks learn automatically

BUT:

> Old methods give **intuition + math understanding** 

Also used in:

* physics-based models
* hybrid systems

So no, you can’t ignore them just because CNNs exist.

---

## 📌 7. Depth (Metric Vision) – Core Idea

Now the interesting part.

### How do we know depth?

Using **parallax**.

---

### 🔹 What is Parallax?

When you move:

* Near objects shift a lot
* Far objects shift less

Example:

* Sit in a train:

  * nearby pole → zooms past
  * mountain → barely moves

👉 That difference = depth clue 

---

## 📌 8. Stereo Vision (like human eyes)

We have:

* Left eye
* Right eye

Each sees slightly different image.

Brain:

* compares both
* calculates depth

---

### Machine version:

* Two cameras
* Compare positions of same object
* Use math → get depth

---

### Output:

👉 **Depth Map**

* bright = near
* dark = far

---

## 📌 9. Why humans don’t need 2 cameras always

You can close one eye and still judge depth.

Why?

Because you also use:

* memory
* size of objects
* shading
* context

Machines:

* don’t have this luxury
* rely on strict methods

---

## 📌 10. Structure from Motion (SfM)

Now things get spicy.

Instead of:

* 2 fixed cameras

We use:

* 1 moving camera

---

### Process:

* Take multiple images from different positions
* Combine them
* Build 3D structure

---

### Output:

👉 **Point Cloud (3D model)**

---

### Why harder?

Because you must find:

1. What is the structure?
2. Where was the camera?

Two unknowns = more pain.

---

## 📌 11. Real-world problems (this matters)

Reality is messy:

* Cameras shake
* Images misalign
* Can’t retake data

So we use:

* rectification (fix alignment)
* post-processing

---

## 📌 12. Advanced idea

You can even:

* take images from internet
* combine them
* reconstruct 3D scene

Example:

* Taj Mahal from random tourist photos

---

# 🎯 What you MUST remember

If exam comes and your brain freezes, remember this:

### Core ideas:

* Image = numbers → need meaning
* Semantic vs Metric
* Parallax → depth
* Stereo = 2 cameras
* SfM = moving camera + 3D reconstruction

---

# 🧠 Intuition (this is your cheat code)

* Near things move more → closer
* Far things move less → farther
* Humans use experience → machines don’t
* CV = breaking a huge problem into smaller ones