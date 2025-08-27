# Kaggle Playground Series S5E6 — Fertilizer Name Prediction

This repository contains my solution for the **Kaggle Playground Series S5E6** competition. The goal was to predict the applied fertilizer from agronomic features, using **Mean Average Precision @ 3 (MAP@3)** as the evaluation metric.

**Ranking**: **242nd** out of **2648** participants (Top 9%).

You can access the competition page [here](https://www.kaggle.com/competitions/playground-series-s5e6).

## Approach

1. **Data Preprocessing**:
   * Cleaned and standardized the dataset.
   * Encoded categorical features with **LabelEncoder** and set categorical dtypes.
   * Performed EDA including previews, value distributions, missing-value analysis, and visualizations.

2. **Feature Engineering**:
   * Engineered additional numeric features.
   * Augmented training folds with the external original dataset.

3. **Modeling**:
   * Applied **Optuna** hyperparameter optimization for both **XGBoost** and **CatBoost** to maximize **MAP@3**.
   * Stacked OOF probabilities from both models with a **Logistic Regression meta-model**, also tuned via **Optuna**.

4. **Evaluation**:
   * Reported fold-wise and mean **MAP@3** on validation.
   * Generated submission files using the **top-3 predicted classes** per row.
