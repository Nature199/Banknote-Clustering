# Banknote-Clustering
K-Means clustering project to detect forged banknotes using PCA and unsupervised learning.

---

# Banknote Clustering – Detecting Forged Currency with Machine Learning

This project explores how machine learning can help distinguish between real and forged banknotes — without relying on pre-labeled data. Using K-Means clustering and PCA for visualization, I analyzed scanned banknote features to uncover patterns hidden beneath the surface.

### ▶️ Run the Notebook
Want to explore the code live?  
[Open in Google Colab](https://colab.research.google.com/github/abiodun-code/banknote-clustering/raw/main/Banknote_Clustering.ipynb)

### 🧠 What’s inside
- A full Jupyter Notebook with data cleaning, standardization, visualization, and clustering
- PCA-based 2D plots showing natural groupings
- PDF report explaining the results in plain language — meant for a non-technical client

### 📂 Files
- `Banknote_Clustering.ipynb` – core notebook with code and charts  
- `Banknote_Report.pdf` – summary report written for a bank stakeholder  
- Screenshots and figures used in the report (optional visuals)

### 🧰 Tools & Libraries
- Python 3  
- Pandas  
- Matplotlib  
- Scikit-learn (for KMeans, PCA, and metrics)  

### 🔎 Project Background
The goal: help a bank considering automation detect forged currency by finding hidden structure in note characteristics like variance, skewness, and entropy. The dataset comes from the UCI Machine Learning Repository, and everything was done using unsupervised learning (no label training).

### 📊 Key Steps
1. Cleaned and standardized the features  
2. Reduced dimensionality with PCA  
3. Ran K-Means clustering (tried different k-values, evaluated stability)  
4. Compared clusters to actual classes using Adjusted Rand Score  
5. Translated findings into a client-facing PDF report

### 🚀 What’s next
This is part of my growing machine learning portfolio. More projects coming soon.

---
