# DA5401-Assignment-5
🎯 Objective

Use t-SNE and Isomap on the Yeast multi-label dataset to visualize data veracity issues — noisy/ambiguous labels, outliers, and hard-to-learn samples — and understand challenges in biological classification.

🧬 Dataset

Source: Mulan Repository – Yeast Data

Features: 103 gene expression levels

Labels: 14 functional categories (multi-label)

Target: Identify and explain visual data quality issues.

⚙️ Steps

Load Data

X, Y, label_names = load_yeast_data(arff_path='data/yeast.arff')


Preprocess

Report shape of X, Y

Create simplified label index (top 2 single labels + most frequent multi-label)

Standardize features using StandardScaler()

t-SNE Visualization

X_tsne = run_tsne_and_plot(X_scaled, cat_idx, cat_names, perplexities=(5,30,50))


→ Identify noisy, outlier, and mixed regions.

Isomap Visualization

X_iso = run_isomap_and_plot(X_scaled, cat_idx, cat_names)


→ Compare global vs local structure with t-SNE. give markdown format
