# Optuna-Tuning for Smart Building Classification

This repository contains experiments for **hyperparameter optimization** in smart building sensor classification, using the [Brick by Brick 2024 Challenge](https://www.aicrowd.com/challenges/brick-by-brick-2024) dataset.

## 🎯 Motivation
Smart building datasets are highly imbalanced and multi-label in nature. Baseline models often underperform due to suboptimal hyperparameters.  
This project demonstrates how **Optuna-based tuning** can improve classification performance beyond strong baselines.

## ⚙️ Methods
- Dataset: **BrickMIR 2024** (NeurIPS Brick by Brick Challenge)
- Baseline: CatBoost classifier (from official winning baseline)
- Hyperparameter search with **Optuna**
  - Learning rate
  - Tree depth
  - L2 regularization
- Evaluation metric: **Macro-F1 score**

## 📊 Results
- Baseline CatBoost (default params): **Macro-F1 = 0.508**
- Tuned CatBoost (Optuna best trial): **Macro-F1 = 0.509**
- Even marginal gains are significant in highly imbalanced multi-label setups

| Model        | Macro-F1 |
|--------------|----------|
| Baseline     | 0.508    |
| Optuna tuned | 0.509    |

## 📦 Repository Structure
