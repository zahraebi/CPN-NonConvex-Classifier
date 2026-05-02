# Hybrid Neural Networks: Counter-Propagation Network (CPN) for 2D Classification

## 1. Project Overview
This project explores the implementation and architectural optimization of a **Counter-Propagation Network (CPN)**. Designed to solve a complex, non-convex 2D classification problem, CPNs utilize a unique hybrid learning approach: combining **Unsupervised Competitive Learning** (Kohonen layer) with **Supervised Learning** (Grossberg layer).

The study focuses on how the competitive layer partitions the input space and provides a detailed performance comparison against the **Back-propagation Network (BPN)** developed in the previous study.

## 2. Methodology: Parametric Study
A systematic manual tuning approach was conducted to evaluate the influence of various hybrid parameters on the model's decision boundaries:

* **Kohonen Layer Sensitivity ($N_k$):** Tested competitive layer sizes ranging from 10 to 500 neurons to find the optimal resolution for non-convex regions.
* **Weight Initialization Strategy:** Evaluated the impact of **Competitive Sampling** (initializing weights from training data) versus random initialization to prevent "dead neurons".
* **Dual Learning Rate Tuning:** Optimized the interplay between the unsupervised rate ($\alpha$) and supervised rate ($\beta$) using grid search.
* **Feature Standardization:** Demonstrated that feature scaling is essential for accurate Euclidean distance calculations in the competitive layer.

## 3. Comparative Analysis: CPN vs. BPN
A key finding of this project is the trade-off between classification accuracy and training efficiency.

| Metric | Counter-Propagation (CPN) | Back-Propagation (BPN) |
| :--- | :--- | :--- |
| **Test Accuracy** | ~95.64% | **~99.21%** |
| **Boundary Resolution** | Discrete / Jagged | Smooth / Continuous |
| **Learning Type** | Hybrid (Clustering + Mapping) | Purely Supervised |

**Conclusion:** While BPN offers superior boundary precision for interlocking geometries, CPN serves as a highly efficient, cluster-based alternative for rapid classification tasks.

## 4. Visualizing Results

### CPN Decision Boundary
*The model partitions the input space into discrete Voronoi-like regions. Using $N_k=100$ neurons provided the best balance between stability and accuracy.*

<img width="790" height="1390" alt="image" src="https://github.com/user-attachments/assets/fecb167c-b451-4590-b4b2-5ec216d28c72" />

### Accuracy vs. Competitive Neurons
*Analyzing the impact of increasing the Kohonen layer capacity on final validation accuracy.*


<img width="855" height="474" alt="image" src="https://github.com/user-attachments/assets/db261190-4f82-4111-a898-f7b255e55458" />
<img width="525" height="455" alt="image" src="https://github.com/user-attachments/assets/d8c8e4ae-9aa5-4a47-8056-8e3b41604b8b" />

<img width="867" height="552" alt="image" src="https://github.com/user-attachments/assets/ba144ef0-6a2b-428e-8287-93464c6633d5" />

---
> **Academic Integrity Note:** This repository serves as a portfolio to showcase methodology and analytical results. The original source code is maintained in a private repository to comply with university academic integrity policies.
