# DNA Sequence Multi-Class Classification

![DNA Classification](https://img.shields.io/badge/Genomics-DeepLearning-brightgreen)

## Overview

This project applies classical machine learning and deep learning methods to a Kaggle DNA classification dataset.  
The goal is to predict the correct class label for each DNA sequence using k-mer features, nucleotide-derived features, and raw nucleotide sequences.

---

## Workflow

1. **Exploratory Data Analysis (EDA)**
    - Nucleotide composition and distribution
    - k-mer (k=2,3,4) counting and visualization
    - Feature correlations (e.g., GC vs. AT content)

2. **Feature Engineering**
    - Global sequence statistics: nucleotide fractions, AT/GC skew
    - k-mer frequencies extraction (64 for k=3)
    - Data normalization and scaling

3. **Baseline Model Training**
    - Logistic Regression  
    - Random Forest  
    - Support Vector Machine  
    - XGBoost  
    - Lasso Logistic Regression  
    - **Result:** All baselines achieved ~25% accuracy (chance level for 4 classes)

4. **Deep Learning Approaches**
    - LSTM sequence models (Keras)
    - CNN sequence models
    - Transformer-based classifiers (tested)
    - **Input:** One-hot encoded DNA sequences
    - **Result:** Deep learning also achieved ~25% accuracy (random)

---

## Results

| Model                    | Mean Accuracy | Std. Dev. |
|--------------------------|--------------|-----------|
| Logistic Regression      | 0.2473       | 0.0062    |
| Random Forest            | 0.2497       | 0.0155    |
| SVM (RBF Kernel)         | 0.2537       | 0.0007    |
| XGBoost                  | 0.2510       | 0.0209    |
| Lasso Logistic Regression| 0.2497       | 0.0103    |
| LSTM (Deep Learning)     | ~0.25        | -         |

---

## Analysis

- **All models performed near random chance.**
- Both traditional ML and sequence deep learning baselines failed to learn class-separating patterns from features or raw DNA.
- **Reason:**  
    - *Likely due to issues in the data*, such as insufficient class signal, noisy or indistinct labels, or a lack of discriminative features in the dataset provided.

---

## Notes & Next Steps

- **Visualization** with PCA/t-SNE/UMAP suggests high class overlap in feature space.
- Possible improvements could include more advanced feature engineering, alternative encoding strategies, or curated/supplementary datasets.
- Further research is needed to obtain genomic data with clearer class distinctions or to engineer more biology-informed features.

---

## Citation

If you use this code, please cite as:

