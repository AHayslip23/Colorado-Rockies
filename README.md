# Colorado Rockies

An analysis of Colorado Rockies franchise batting and pitching statistics, with exploratory analysis, regression models and classification models for each.

## Repository Contents

| File | Description |
|---|---|
| `Rockies Batting Data.ipynb` | Batting analysis: franchise leaders, feature engineering and handedness classification |
| `Rockies Pitching.ipynb` | Pitching analysis: performance tiers, regression models and pitcher-role classification |

## Commit History

### `1333dea`: Notebooks for Rockies batting and pitching stats (2025-12-14)

**Batting notebook**
- **Feature engineering:**
  - added total extra-base hits
  - added left- and right-handed batter flags
  - added infielder and outfielder flags
- **Franchise leaders:** found the most successful players in Rockies history (e.g. Dante Bichette's career totals).
- **Classification: predicting whether a batter is left-handed:**

  | Model | Accuracy |
  |---|---|
  | Logistic regression (base) | 68.5% |
  | Logistic regression with cross-validation | 71.5% |
  | Grid search | 72.1% |
  | Class-balanced base model | 70.3% |

**Pitching notebook**
- **Cleaning:**
  - dropped the rank column, null rows and the switch-hitter field
  - added left/right flags and starter, reliever and closer flags
- **Performance tiers:** functions that rate each pitching season on ERA, WHIP, FIP, strikeouts per nine and walks per nine. Most seasons fall in the poor tiers, so the classes are imbalanced.
- **EDA:**
  - an age histogram
  - the 10 best and worst seasons by ERA
  - strikeouts by handedness
  - starters vs. relievers
  - a look at the 2007 Rockies
- **Simple linear regressions:**

  | Relationship | Base R² | With cross-validation |
  |---|---|---|
  | Hits allowed → home runs allowed | 73.5% | 75.2% |
  | Hits allowed → runs allowed | 92.9% | 94.5% |
  | Hits allowed → earned runs | 93.0% | 93.8% |

- **Multiple regression:** predicts earned runs from pitching stats (R² = 99.6%).
- **Logistic regression classifiers:** predict whether a pitcher is left-handed (66.2% accuracy), right-handed, a starter, a reliever or a closer. Accuracies across these models ranged from about 66% to 96%.

## Tools
Python, pandas, NumPy, scikit-learn, matplotlib, seaborn, Jupyter Notebook
