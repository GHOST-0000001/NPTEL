# 🧾 WEEK 3 – SUPER MASTER NOTES (FINAL)

## 🔹 Training with Multiple Data Samples

Real training uses multiple samples, not single input

$$
L = \frac{1}{LM} \sum_{j=1}^{L} \sum_{i=1}^{M} (\hat{Y}_{ij} - Y_{ij})^2
$$
Loss is averaged across:
- all samples
- all outputs


## 🔹 Gradient Descent Variants

### Batch Gradient Descent

Uses full dataset  
Very slow → not practical  


### Stochastic Gradient Descent (SGD)

Uses one sample  
Fast but unstable  


### Mini-Batch Gradient Descent (MOST USED)

Uses small batches  

$\text{Batches} = \frac{N}{B}$  

Balanced:
- stable + efficient  


## 🔹 Epoch vs Iteration

Iteration = one batch update  
Epoch = one full dataset pass  


## 🔹 Momentum-Based Optimization

$V_t = \gamma V_{t-1} + \alpha \nabla L(\theta_t)$  

$\theta_{t+1} = \theta_t - V_t$

Uses past gradients  
Faster convergence  

Problem:
Overshooting near minima  


## 🔹 Nesterov Accelerated Gradient (NAG)

$V_t = \gamma V_{t-1} + \alpha \nabla L(\theta_t - \gamma V_{t-1})$

Looks ahead  
Reduces oscillation  


## 🔹 Adaptive Learning Rate

### AdaGrad

$\theta_{t+1} = \theta_t - \frac{\alpha}{\sqrt{r_t + \delta}} \nabla L$

Per-parameter learning rate  
Problem: learning slows over time  


## 🔹 Adam Optimizer (MOST IMPORTANT)

$S_t = \rho_1 S_{t-1} + (1 - \rho_1)\nabla L$  

$r_t = \rho_2 r_{t-1} + (1 - \rho_2)(\nabla L)^2$

Combines:
- momentum
- adaptive learning  

Most widely used optimizer  


## 🔹 Generalization vs Overfitting

Training error ↓ always  

Validation error:
- ↓ initially  
- ↑ later → overfitting  


## 🔹 Early Stopping

Stop training when validation error increases  


## 🔹 Data Augmentation

Increase dataset artificially  

Types:
- Geometric: rotation, scaling  
- Photometric: noise, brightness  


## 🔹 Regularization

### L2 Regularization

$L_{new} = L + \beta ||W||^2$

Penalizes large weights  
Encourages simpler models  


Gradient Update:

$\nabla L + \beta W$


Key Insight:
Important weights remain  
Others shrink  


## 🔹 Noise Injection

Add noise to input  

$x + \epsilon$

Equivalent to L2 regularization  


## 🔹 Dropout

Randomly remove neurons  

Training:
neurons dropped  

Testing:
no dropout  
scale outputs  

Effect:
prevents co-adaptation  
acts like ensemble  


## 🔹 Preprocessing

### Input Normalization

$x' = \frac{x - \mu}{\sigma}$

Mean = 0  
Variance = 1  


## 🔹 Internal Covariate Shift

Distribution changes across layers  
Slows training  


## 🔹 Batch Normalization

Steps:
1. Compute mean  
2. Compute variance  
3. Normalize  


Add learnable parameters:

$y = \gamma x + \beta$

Benefits:
- faster training  
- stable gradients  


## 🔹 Weight Initialization

Problem:
Large weights → explosion  
Small weights → vanishing  


Condition:

$\text{Var}(W) = \frac{1}{n}$


## 🔹 Xavier Initialization

$W \sim U\left(-\sqrt{\frac{6}{fan_{in}+fan_{out}}}, \sqrt{\frac{6}{fan_{in}+fan_{out}}}\right)$


## 🔹 He Initialization

Better for ReLU  


Important Rule:
Never initialize all weights equal  


## 🔹 Introduction to CNN

Designed for:
- images  
- spatial data  


## 🔹 CNN vs MLP

| Feature      | MLP  | CNN       |
|--------------|------|----------|
| Connectivity | Full | Local    |
| Parameters   | High | Low      |
| Structure    | Lost | Preserved|


## 🔹 Convolution Operation

$y[n] = \sum x[m] h[n-m]$


2D Convolution:
Apply filter over image  
Extract features  


## 🔹 CNN Core Properties

### Locality

small receptive region  


### Weight Sharing

same filter everywhere  


### Receptive Field

grows with depth  


## 🔹 Feature Maps

Each filter → one feature map  

Meaning:
each map detects different pattern  


## 🔹 Multi-Channel Convolution

Input has multiple channels  

Filter size:

$k \times k \times c$

Output:
sum across channels  


## 🔹 Multiple Filters

produce multiple feature maps  


## 🔹 Flattening

Convert feature maps → vector  


## 🔹 Fully Connected Layers

Perform classification  


## 🔹 Output Layer

Softmax + Cross Entropy  


## 🔹 CNN Pipeline

Input → Conv → Pool → Conv → Pool → Flatten → FC → Output


## 🔹 Key Insights

CNN = feature extractor  
FC = decision maker  


## Next

Week 4 = CNN deep dive + architectures + RNN intro
