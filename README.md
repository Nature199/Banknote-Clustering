# Banknote Clustering

K-Means clustering project to explore whether scanned banknote measurements naturally separate into groups that may correspond to genuine and forged notes.

This repository is intentionally lightweight: the main analysis lives in a Jupyter notebook, the dataset is checked in as a CSV, and a stakeholder-facing PDF report is included for a non-technical summary.

## Project goals

- Explore the banknote measurements with basic descriptive statistics and plots.
- Standardize numeric features so distance-based clustering treats each feature fairly.
- Use PCA to visualize the feature space in two dimensions.
- Run K-Means clustering with two clusters and inspect whether the groups look stable.
- Communicate the workflow and findings in both notebook and report form.

## Repository structure

| Path | Purpose |
| --- | --- |
| `Banknote_Authentication__dataset.ipynb` | Main notebook containing imports, data loading, statistics, plots, scaling, PCA, and K-Means clustering. |
| `Banknote-authentication-dataset.csv` | Input dataset used by the notebook. This version contains two numeric features: `V1` and `V2`. |
| `Automating Detection of Forged Banknotes...pdf` | Client/stakeholder-facing report summarizing the project in plain language. |
| `requirements.txt` | Python dependencies needed to run the notebook locally. |

## Dataset note

The checked-in CSV is a simplified two-feature version of the banknote dataset. It does **not** include a `class` label column, so the notebook treats the project as an unsupervised clustering exercise.

That means K-Means can show whether observations form two visible groups, but it cannot prove which group is genuine or forged without external labels or domain review. If you add a labeled dataset later, you can compare clusters against known labels with metrics such as Adjusted Rand Index.

## Quick start

### Option 1: Run in Google Colab

Open the notebook in Colab:

[Open in Google Colab](https://colab.research.google.com/github/Nature199/banknote-clustering/blob/main/Banknote_Authentication__dataset.ipynb)

If using Colab, upload `Banknote-authentication-dataset.csv` into the notebook session before running the data-loading cell.

### Option 2: Run locally

1. Create and activate a virtual environment:

   ```bash
   python -m venv .venv
   source .venv/bin/activate
   ```

2. Install dependencies:

   ```bash
   pip install -r requirements.txt
   ```

3. Start Jupyter:

   ```bash
   jupyter notebook Banknote_Authentication__dataset.ipynb
   ```

4. Run the notebook cells from top to bottom.

## Analysis workflow

The notebook follows this flow:

1. Import `numpy`, `pandas`, `matplotlib`, and scikit-learn utilities.
2. Load `Banknote-authentication-dataset.csv`.
3. Inspect the first rows and column names.
4. Calculate mean and standard deviation for `V1` and `V2`.
5. Plot histograms to understand feature distributions.
6. Standardize features with `StandardScaler`.
7. Project the scaled data into two PCA components.
8. Run K-Means with `n_clusters=2`.
9. Re-run K-Means multiple times to check visual stability.
10. Summarize the insights and limitations.

## Important limitations

- The current dataset has only two numeric columns, so PCA is primarily a visualization aid rather than a major dimensionality-reduction step.
- There are no labels in the CSV, so cluster quality cannot be validated against true genuine/forged classes in this version.
- K-Means assumes roughly spherical clusters and can be sensitive to initialization, which is why the notebook repeats the clustering step.

## Ideas for future improvements

- Add the full labeled Banknote Authentication dataset and compare cluster assignments against true labels.
- Add cluster-validation metrics such as silhouette score, inertia/elbow plots, and Adjusted Rand Index when labels are available.
- Export final plots as image files for the report.
- Convert repeated notebook logic into a small Python script for reproducible command-line runs.
- Add automated checks that confirm the notebook can execute from a clean environment.
