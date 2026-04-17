# High-Dimensional-Probabilistic-Clustering-Pipeline-PCA-GMM-
A highly constrained input matrix ($N=200$) was deliberately utilized to benchmark the Expectation Maximization algorithm's convergence behavior and boundary overlap in low density, multi dimensional coordinate spaces.


# High-Dimensional Probabilistic Clustering Pipeline (PCA & GMM)

## System Objective
This repository contains a computational pipeline engineered to execute unsupervised classification on multi-dimensional categorical and continuous data. The architecture deliberately bypasses standard $L_2$ norm partitioning (K-Means) in favor of probabilistic density estimation, optimizing for non-isotropic variance and latent spatial relationships.

## Architectural Methodology

### Phase 1: Matrix Pre-Processing & Non-Linear Transformation
* **Data Ingestion & Pruning:** Ingestion of target data via dynamic web request. Identification and deletion of statistical outliers via Interquartile Range (IQR) thresholding to constrain global variance.
* **Orthogonal Projection:** Application of binary mapping to discrete categorical vectors.
* **Isotropic Standardization:** Application of Z-score normalization ($x' = \frac{x - \mu}{\sigma}$) to enforce a variance of $1.0$ across all coordinate axes.
* **Polynomial Feature Expansion:** Dimensionality expansion mapping the input matrix from $\mathbb{R}^4 \rightarrow \mathbb{R}^{14}$ to calculate second degree interaction terms and surface non linear structural boundaries.

### Phase 2: Dimensionality Reduction & Probabilistic Clustering
* **Principal Component Analysis (PCA):** Orthogonal projection of the $\mathbb{R}^{14}$ matrix to mitigate the Hughes Phenomenon, extracting only the principal components required to explain 95% of the system's cumulative variance.
* **Gaussian Mixture Model (GMM):** Deployment of Expectation Maximization (EM) to fit multivariate Gaussian distributions to the orthogonal space. 
* **Soft Assignment:** Computation of full covariance matrices ($\Sigma$) for each cluster to support elliptical spatial boundaries, outputting strict probability density functions rather than rigid scalar assignments.

### Phase 3: System Diagnostics & Data Extraction
* Iterative compilation of continuous coordinate profiles (Means) and variance metrics (Standard Deviations).
* Extraction of Principal Component loading weights to identify specific polynomial vectors driving the spatial divergence.
* Dynamic rendering of multi dimensional data via interactive Plotly geometry.

## Data Sparsity & System Constraints
A highly constrained input matrix ($N=200$ rows) was deliberately utilized as the baseline execution environment. This localized parameter constraint was implemented specifically to benchmark the Expectation Maximization algorithm's convergence behavior and probability overlap boundaries in a low density coordinate space prior to any large-scale hardware deployment.

## Execution Environment
Execute the pipeline locally via standard Jupyter kernels. Ensure dependency state matches the included parameters.
```bash
pip install -r requirements.txt
