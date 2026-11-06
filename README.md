# Is 99.99% Enough? Shortcut Learning and Sampling Bias in the PhiUSIIL Phishing URL Dataset

Code for the paper of the same name, written for the course AIS500 Fundamentals of Artificial Intelligence, Qatar University (2026).

## What this repository shows

Recent studies report about 99.99% accuracy for phishing URL detection on the PhiUSIIL dataset.
We show that every legitimate URL in the dataset starts with `https://www.` (versus 2.4% of phishing URLs),
so a single rule reaches 98.96% accuracy, and that URL-only accuracy falls to about 78% once this shortcut is removed.

## Data

PhiUSIIL Phishing URL Dataset (A. Prasad and S. Chandra), UCI Machine Learning Repository, dataset 967:
https://archive.ics.uci.edu/dataset/967 — licence CC BY 4.0.
The data is not included here. Download `PhiUSIIL_Phishing_URL_Dataset.csv` and place it next to the notebook.

## How to run

```bash
pip install -r requirements.txt
jupyter lab PhiUSIIL_Shortcut_Study.ipynb
```

Then **Kernel → Restart Kernel and Run All Cells**. All experiments repeat over 5 random seeds (42, 0, 1, 2, 3);
the full run takes about 10–20 minutes on a laptop.

## Experiments

| # | Experiment | Notebook section |
|---|---|---|
| E1 | Replication of Bao et al. (2026) with RF, linear SVM and MLP | 5 |
| E2 | Training on row sub-sets (0.1% to 50% of training rows) | 6 |
| E3 | Hard test sub-set: phishing URLs starting with `https://www.` | 7 |
| E4 | One-rule baseline: `https://www.` means legitimate | 4 |
| E5 | Matched sub-sets with 5-fold cross-validation | 8 |
| — | Leakage check: train/test split by domain | 9 |

Outputs: `fig1`–`fig4` PNG files and `results_*.csv` tables.

## Authors

Faisal Al Shahwani · Khalid Al Qahtani · Hamad Al Hajri
Master’s Program in Security Artificial Intelligence, Qatar University, Doha, Qatar.

## AI-use disclosure

As stated in the paper’s Acknowledgment, Claude (Anthropic) was used to assist with selecting the dataset
and the reference study, writing and debugging the analysis code, checking numerical results, and giving
feedback on draft sections. The authors ran every experiment and verified every reported result.
