# Iteration Log (Step 8.5)

Record each change you make between runs (balancing, feature selection, algorithm params) and its effect on metrics.

| Iteration | Change                                 | Reason                      | Accuracy | Sensitivity | Specificity | AUC  | Notes |
|-----------|-----------------------------------------|-----------------------------|----------|-------------|-------------|------|-------|
| 1         | Baseline Logistic (no balance)          | Establish baseline          |          |             |             |      |       |
| 2         | Add SMOTE, keep all features            | Handle class imbalance      |          |             |             |      |       |
| 3         | Feature filter (Chi-square top N)       | Reduce variance/overfit     |          |             |             |      |       |
| 4         | C5.0 with costs (FN penalty ↑)          | Improve recall              |          |             |             |      |       |
| 5         | Random Forest (grid search trees)       | Robustness/accuracy         |          |             |             |      |       |
