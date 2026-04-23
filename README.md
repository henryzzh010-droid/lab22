# lab22
# Unsupervised Learning — Clustering & Dimensionality Reduction

## Objective
Diagnose and repair a flawed clustering workflow, then build a reproducible unsupervised learning pipeline using K-Means, PCA, UMAP, and hierarchical clustering for cross-country economic segmentation.

---

## Project Summary
This lab focused on identifying common implementation errors in clustering analysis and redesigning the workflow using best practices. The original pipeline contained multiple issues, including missing feature standardization, incorrect model parameters, PCA applied before scaling, and lack of reproducibility controls. After correcting these errors, the project extended into customer segmentation, dimensionality reduction comparisons, reusable Python module design, and hierarchical clustering diagnostics.

---

## Methodology

### 1. Pipeline Diagnosis & Repair
Identified and corrected four deliberate errors in the original K-Means workflow:

- Omitted feature standardization before clustering
- Incorrect parameter usage (`k=4` instead of `n_clusters=4`)
- PCA applied before standardization
- Missing `random_state` for reproducibility

Corrected workflow:

StandardScaler → K-Means → PCA Visualization

---

### 2. Country Clustering (World Development Indicators)
Used standardized macroeconomic indicators such as:

- GDP per capita  
- Life expectancy  
- Infant mortality  
- Internet usage  
- Trade openness  
- Urbanization rate  
- Unemployment rate  

Applied K-Means clustering (`K=4`) to group countries with similar economic development profiles.

---

### 3. Dimensionality Reduction Comparison
Compared two visualization techniques:

#### PCA
- Linear projection method
- Strong interpretability
- Useful for variance decomposition

#### UMAP
- Nonlinear manifold learning method
- Better preservation of local cluster structure
- Improved visual separation in heterogeneous data

---

### 4. Reusable Analytics Module
Built a modular Python package:

`clustering_utils.py`

Functions included:

- `run_kmeans_pipeline()`
- `evaluate_k_range()`
- `plot_pca_clusters()`

This improved code reusability, portability, and reproducibility.

---

### 5. Hierarchical Clustering Extension
Implemented Agglomerative Clustering with Ward linkage and visualized the dendrogram to compare nested group structures against K-Means partitions.

---

## Key Findings

- Standardization materially improved cluster balance and silhouette performance.
- Optimal cluster count was approximately **K = 4**, based on silhouette score and interpretability.
- PCA explained broad global variance patterns, while UMAP delivered clearer cluster separation.
- Hierarchical clustering produced similar macro groupings to K-Means, validating segmentation robustness.
- Modular code design substantially improved workflow efficiency and scalability.

---

## Technical Skills Demonstrated

- Unsupervised Machine Learning  
- K-Means Clustering  
- Hierarchical Clustering  
- PCA / UMAP  
- Feature Engineering  
- Model Validation  
- Python Module Development  
- Reproducible Research Design

---

## Business / Economic Interpretation

This project demonstrates how unsupervised learning can classify economies or customers into meaningful groups without labeled outcomes. Such methods are useful in:

- Market segmentation  
- Development benchmarking  
- Risk grouping  
- Policy targeting  
- Behavioral analytics

---

## Repository Structure

```text
econ-lab-22-clustering/
│── notebooks/
│── src/
│── figures/
│── clustering_utils.py
│── README.md
