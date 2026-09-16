# Classification Track

## Dataset Selection 

### The following criteria were used while comparing potential datasets :

| Criterion | Requirement |
|---|---|
| Class Balance | Moderate imbalance |
| Number of Samples | Large enough for meaningful comparison |
| Number of Features | Sufficient predictive features |
| Feature Type | Numerical / easily preprocessable |
| Target Variable | Clearly defined fraud/non-fraud label |
| Dataset Size | Computationally manageable |
| Algorithm Compatibility | Must support all 10 classifiers |
| Evaluation | Must support all required classification metrics |

### Several fraud-detection datasets were considered before finalizing the dataset :

| Dataset | Approx. Samples | Approx. Features | Fraud Distribution | Decision |
|---|---:|---:|---|---|
| ULB Credit Card Fraud Dataset | 284,807 | 30 | ~0.17% fraud | ❌ Rejected |
| Online Banking Fraud Inference Logs (2026) | 56,962 | Multiple | ~0.17% confirmed fraud | ❌ Rejected |
| IEEE-CIS Fraud Detection | ~590,000 | ~871 | ~3.5% fraud | ❌ Rejected |
| PaySim | ~6.3 million | ~10+ | Highly imbalanced | ❌ Rejected |
| Credit Card Fraud Detection Dataset 2023 | ~568,630 | ~30 | ~50:50 | ✅ Selected |

**Finalized Dataset Link :**
https://www.kaggle.com/datasets/nelgiriyewithana/credit-card-fraud-detection-dataset-2023
