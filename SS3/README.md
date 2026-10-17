# CAP182 Capstone — SS3 Part B: Fraud Anomaly Detection for STADIOalot

Applies the final method from SS2 (Part C/D, **Model 2: hybrid Isolation Forest + Neural Network**) to the client's full data extract.
**Notebook:** [`SS3_PartB.ipynb`](SS3_PartB.ipynb) — all outputs are already saved in it.

## Notebook map
| Section (header in notebook) | What it does |
|---|---|
| 1. DATASET LOADING | Loads orders, payments, demographics (non-PII columns only), chargebacks, flags. Defines the fraud label. Markdown block gives instance counts, classes and imbalance. |
| 2. DATASET PREPROCESSING | Cleaning, ZAR conversion, SS2 feature families (temporal, contextual, customer velocity, customer history), train-only risk tiers, chronological 60/20/20 split, train-only scaler. Markdown table explains *why* for each step. |
| 3. MODEL TRAINING | Stage 1: Isolation Forest on legitimate training orders (anomaly score/flag/bin). Stage 2: SMOTE 0.5 + 64-32-1 dropout network, Adam 0.001, early stopping on validation PR-AUC. Markdown table lists SS2 value vs value used and why. Training history, models and config saved to `outputs/`. |
| 4. MODEL VALIDATION | Unseen test set: ROC-AUC, PR-AUC with bootstrap CIs, precision/recall/F1 at 0.5, validation-F1-optimal and review-capacity thresholds, precision@k, lift, rand value caught; comparison with NN alone, Random Forest, Isolation Forest alone; alternative-label check. |
| 5. RESULTS VISUALISATION | 8 labelled panels (A-H): fraud rate per subset, loss and PR-AUC per epoch, anomaly scores, ROC, PR, confusion matrix, cumulative gains, model comparison. |

## How to run
```bash
pip install -r requirements.txt
# put stadioalot_data_extract.zip in this folder
jupyter nbconvert --to notebook --execute SS3_PartB.ipynb --output SS3_PartB.ipynb
```
Random seeds are fixed, so results are reproducible. Runtime ≈ 2-3 minutes (CPU).

## Saved outputs (`outputs/`)
`training_history.csv`, `training_config.json`, `test_metrics.json`, `test_predictions.csv`, `validation_predictions.csv`, `model_comparison.csv`, `label_sensitivity.json`, `fig_*.png`, `model_neural_network.keras`, `model_isolation_forest_and_prep.joblib` (git-ignored).

## Key assumptions
* **Fraud label** = fraudulent chargeback **or** flag resolved as *Blocked* / *Escalated to bank* (401 of 8,412 paid orders, 4.8%).
* **Currency:** amounts are converted to ZAR with fixed approximate rates (USD 18, EUR 20, GBP 23). The extract supplies no rates.
* **Leakage controls:** chargebacks, flags, resolutions, star ratings, delivery data and the lifetime `10_purchase_histories` table are never used as features. Customer history is rebuilt from earlier orders only.
* **SS2 adaptations:** batch size 128 (not 2048) and up to 60 epochs with early stopping (not 5 fixed) because the data is ~250x smaller; everything else as in SS2.
* **Star ratings** are excluded (post-delivery, would leak); comments are used only as a presence flag.
* **Unused tables:** search history, abandoned carts, listings, sellers, complaints (different problems, or not linkable to orders).
* **PII:** name/email/phone are never loaded; see `data/README.md`.

## Headline result
Hybrid test ROC-AUC 0.513 (95% CI 0.43-0.59), PR-AUC 0.048 (95% CI 0.036-0.069) vs 0.043 random baseline: not distinguishable from chance. Random Forest, NN alone and Isolation Forest alone score the same. The client's order-time fields carry little fraud signal (no geolocation or card ID, rare repeat orders); the notebook reports this transparently and lists the data to request.
