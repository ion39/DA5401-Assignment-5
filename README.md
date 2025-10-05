# DA5401 Assignment 5 – Visualizing Data Veracity Challenges in Multi-Label Classification

# Pragati L - CE22B089

## Overview
This notebook explores **data veracity challenges** in the Yeast multi-label dataset using **t-SNE** and **Isomap** for dimensionality reduction. The focus is on visually identifying:

- **Noisy/Ambiguous Labels** – Genes with potentially misclassified or overlapping functions.  
- **Outliers** – Experiments with unusual gene expression patterns.  
- **Hard-to-Learn Samples** – Points in regions where functional categories are thoroughly mixed.

The goal is to understand why real-world biological datasets are challenging for classifiers.

---

## Dataset
- **Source:** [Mulan Repository – Yeast Data](http://mulan.sourceforge.net/datasets-mlc.html)  
- **Features:** 103 gene expression levels per experiment.  
- **Labels:** 14 functional categories (binary multi-label matrix).  
- **Format:** `X` (features) and `Y` (labels) as CSV or ARFF files.

---

## Notebook Structure

### Part A: Preprocessing and Initial Setup
1. **Data Loading:** Load the feature matrix `X` and multi-label target matrix `Y`.  
2. **Dimensionality Check:** Report number of samples and features.  
3. **Label Selection for Visualization:** Reduce 14 labels to a simpler categorical index:
   - Two most frequent single-label classes.  
   - Most frequent multi-label combination.  
   - Remaining points labeled as `Other`.  
4. **Scaling:** Standardize features to ensure fair distance calculations for t-SNE and Isomap.

### Part B: t-SNE and Veracity Inspection
1. **t-SNE Implementation:**  
   - Reduce `X` to 2D using different perplexities (5, 30, 50).  
   - Select final perplexity based on visualization clarity.  
2. **Visualization:** 2D scatter plot with color coding from the simplified categorical index.  
3. **Veracity Analysis:** Identify visually:
   - **Noisy/Ambiguous Labels** – Points of one color embedded in clusters of another.  
   - **Outliers** – Isolated points or small distant clusters.  
   - **Hard-to-Learn Samples** – Mixed regions challenging for simple classifiers.

### Part C: Isomap and Manifold Learning
1. **Isomap Implementation:** Reduce `X` to 2D while preserving **global structure**.  
2. **Visualization:** 2D scatter plot with the same color coding.  
3. **Comparison:**  
   - Compare t-SNE vs Isomap visualizations.  
   - Discuss the **data manifold**, its curvature, and implications for classification difficulty.

---

## How to Run
1. Install dependencies:  
pip install numpy pandas matplotlib scikit-learn liac-arff

2. Open the notebook in Jupyter or VSCode.

3. Download the file yeast.rar and change the path accordingly for the file yeast.arff

4. Run cells sequentially; each section contains explanations and visualizations.
