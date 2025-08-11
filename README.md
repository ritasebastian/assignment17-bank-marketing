
# Assignment 17.1 — Comparing Classifiers on Bank Marketing

This repo contains a clean, well-organized solution comparing **k-NN**, **Logistic Regression**, **Decision Tree**, and **SVM** on the UCI Bank Marketing dataset.

## Quick Start
1. Create a Python 3.10+ environment and install requirements:
   ```bash
   pip install -r requirements.txt
   ```
2. Open the notebook:
   ```bash
   jupyter lab Assignment17_Bank_Marketing_Comparison.ipynb
   ```
3. **Kernel → Restart & Run All**

## Notebook
- **Primary notebook:** `Assignment17_Bank_Marketing_Comparison.ipynb`  
- Organized with headings and explanatory text (CRISP-DM).  
- Uses sklearn Pipelines, ColumnTransformer, Stratified CV, and GridSearchCV.  
- Visualizations with **matplotlib** and **seaborn** (labeled, titled, legible; includes appropriate subplots).

## Data
- We include the **reduced** dataset for quick runs: `data/bank-additional.csv`  
- Feature names: `data/bank-additional-names.txt`  
- (The full dataset is available from the UCI repository; not committed here to keep the repo lean.)

## Findings (High-Level Summary)
- The target (`y = yes`) is **imbalanced**; evaluation emphasizes **ROC AUC** and **PR AUC**.
- Among the tested models, the best performing model by ROC AUC on the held-out test set will be shown in the notebook's **summary table** and **ROC/PR curves**.
- **Key drivers** typically include recent contact outcomes, call duration, contact type, month, and macroeconomic indicators (see permutation importance).

### Actionable Insights (Non-technical Audience)
- **Prioritize** calling customers with characteristics associated with higher predicted conversion.
- Use model **probabilities** to **rank** leads; focus agent time on top deciles.
- Introduce **call time limits** or early stopping if engagement signals are weak.
- Run controlled **experiments** (A/B) to validate uplift among targeted segments.

## Next Steps & Recommendations
1. **Probability calibration** for better thresholding in operations.
2. **Cost-sensitive** threshold selection using business costs for FP/FN.
3. **Temporal validation** using month-based splits to reflect campaign drift.
4. **Monitoring**: conversion rate, AUC, data drift; retrain quarterly or on drift.
5. **Fairness & privacy** checks on sensitive attributes.
6. **Deployment** with persisted sklearn pipeline and joblib.

## Repository Hygiene
- Clear directory names (`data/`, notebook at root).
- No extraneous files; concise `.gitignore` included.
- Variables, imports, and comments follow best practices.

## Link to Notebook
- **`Assignment17_Bank_Marketing_Comparison.ipynb`** (in this repo)
