![Bank Customer Churn Prediction](assets/banner.svg)

**English** · [Português](README.pt-BR.md) · [Notebook](notebooks/bank_customer_churn_prediction.ipynb) · [Portfolio](https://github.com/joaovspereira)

# Bank Customer Churn Prediction

## Business question

Identify customers likely to leave Beta Bank and meet the project requirement of test F1 ≥ 0.59.

## Results and evidence

| Evidence | Saved result |
|---|---:|
| Selected approach | Random Forest + oversampling |
| Test F1 | **0.6141** |
| Test ROC-AUC | **0.8575** |
| Validation F1, selected approach | 0.5950 |
| Validation F1, unbalanced baseline | 0.5596 |
| Test confusion matrix (TN / FP / FN / TP) | 1438 / 135 / 178 / 249 |

The final model uses 200 trees and maximum depth 15. Validation and test scores refer to different samples and should not be treated as a before-and-after lift.

## Methodology

1. Remove row identifiers, encode categorical features and split the data into 60% training, 20% validation and 20% test.
2. Fit tenure imputation and numerical scaling on the training set only.
3. Compare an unbalanced Random Forest with class weighting, oversampling and undersampling.
4. Select using validation F1, then report test F1, ROC-AUC and the confusion matrix.

## Technologies

Python · pandas · NumPy · scikit-learn · Matplotlib

## Explore the repository

- [Notebook](notebooks/bank_customer_churn_prediction.ipynb) — analysis, code and saved evidence
- [Data requirements](data/README.md) — expected source files
- [Validation notes](VALIDATION.md) — provenance, corrections and checks
- [Dependencies](requirements.txt)

## Run locally

```bash
git clone https://github.com/joaovspereira/bank-customer-churn-prediction.git
cd bank-customer-churn-prediction
python -m venv .venv
```

Activate the environment with `source .venv/bin/activate` on macOS/Linux or `.\.venv\Scripts\Activate.ps1` in Windows PowerShell. Then run:

```bash
python -m pip install -r requirements.txt
python -m notebook notebooks/bank_customer_churn_prediction.ipynb
```

Add the datasets listed in [data/README.md](data/README.md) before executing the notebook. The analysis is in Portuguese, with this English guide for navigation. Dependencies are an installation list, not a lockfile for the original environment.

## Key learning

Churn scores can support prioritization, but the decision threshold must reflect intervention cost, capacity and missed customers. Model discrimination does not establish that an intervention will prevent churn.

## Limitations

Saved metrics come from the original notebook, not a fresh training run. The split is random and not stratified; one-hot categories were determined before splitting. Exact historical dependency versions are unavailable. F1 and ROC-AUC measure different properties and must not be compared numerically as competing scores. A deployment would need calibration, temporal validation, fairness checks and an intervention experiment.

## Next improvements

Use a training-only preprocessing pipeline, stratified or time-aware validation, precision–recall analysis and a retention-cost model.

## Context

Educational project developed during the TripleTen Data Science Bootcamp and prepared for this public portfolio. No production deployment or realized business impact is claimed.

[João Vitor Pereira](https://github.com/joaovspereira) · [LinkedIn](https://www.linkedin.com/in/joao-vitor-de-souza-pereira) · [Email](mailto:joaovitorsouza20pereira@gmail.com)
