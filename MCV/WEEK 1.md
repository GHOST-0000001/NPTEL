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
$$
y = 1 \text{ if } (w \cdot x \ge \theta), \text{ else } 0
$$

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
   - If positive misclassified → $W = W + X$
   - If negative misclassified → $W = W - X$

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