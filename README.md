# Optuna-Tuning for Smart Building Classification

This repository contains experiments for **hyperparameter optimization** in smart building sensor classification, using the [Brick by Brick 2024 Challenge](https://www.aicrowd.com/challenges/brick-by-brick-2024) dataset.

## Motivation
Smart building datasets are highly imbalanced and multi-label in nature. Baseline models often underperform due to suboptimal hyperparameters.  
This project demonstrates how **Optuna-based tuning** can improve classification performance beyond strong baselines.

## Experiments

### 1. Optuna Hyperparameter Tuning ✅
- Based on CatBoost baseline from BrickMIR.
- Improved macro-F1 from **0.5079 → 0.5085**.
- Demonstrates that automated search (TPESampler + MedianPruner) is more effective than manual tuning.

### 2. Alternative Tree-based Models（classifierchain） ❌
- Replaced CatBoost with RandomForest / ExtraTrees to test robustness.  
- Best macro-F1 achieved: **0.477**, significantly worse than baseline.  
- Shows the importance of imbalance-aware boosting methods in multi-label BMS tasks.  
- Notebook: `notebooks/failed_trials.ipynb`


## Methods
- Dataset: **BrickMIR 2024** (NeurIPS Brick by Brick Challenge)
- Baseline: CatBoost classifier (from official winning baseline)
- Hyperparameter search with **Optuna**
  - Learning rate
  - Tree depth
  - L2 regularization
- Evaluation metric: **Macro-F1 score**

## Results
- Baseline CatBoost (default params): **Macro-F1 = 0.508**
- Tuned CatBoost (Optuna best trial): **Macro-F1 = 0.509**
- Even marginal gains are significant in highly imbalanced multi-label setups

| Model        | Macro-F1 |
|--------------|----------|
| Baseline     | 0.508    |
| Optuna tuned | 0.509    |

## Repository Structure

## Key Insights

- Hyperparameter tuning (Optuna) improved macro-F1 slightly, but gains were marginal.  
- Negative results from RandomForest/ExtraTrees confirmed that boosting remains superior for BMS data.  
- **Main takeaway:** The bottleneck is not the model itself, but **feature representation**.  
  Future work should focus on improved time-series embeddings, ontology-guided features, or representation learning approaches.
