# Lab 3 — Ticket Resolution Time Regression

Estimates how long a software support ticket takes to resolve, comparing a mean baseline, linear regression,
polynomial regression (degrees 2 and 3), Ridge and Lasso on a synthetic dataset.

## Files

| File | Description |
|---|---|
| `Lab3_ticket_resolution.ipynb` | Completed lab: Tasks 1–9 and analysis questions 10–17 |
| `lab_ticket_resolution.csv` | Dataset (240 tickets) |
| `Lab_3.pdf` | Lab brief |

## How to run

```bash
pip install numpy pandas matplotlib scikit-learn jupyter
jupyter notebook Lab3_ticket_resolution.ipynb
```

## Summary

- Features: `complexity_score`, `team_experience_years`, `reopened`. `lines_changed` is excluded because it is
  only known after the fix (leakage).
- 80/20 train/test split (`random_state=42`); model settings chosen with 5-fold CV on the training set.
- Recommended model: **Linear Regression** (test MAE ≈ 2.59 h, RMSE ≈ 3.22 h, R² ≈ 0.91).
  Polynomial features did not improve validation error, and Ridge/Lasso selected near-zero α.
