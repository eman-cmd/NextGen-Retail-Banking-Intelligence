# Digital Banking Analytics & AI Portfolio

Three end-to-end projects covering predictive modeling, marketing analytics, and NLP-based search — built to mirror real problems in digital banking: customer retention, campaign ROI, and internal knowledge search.

---

## 1. Bank Customer Churn Prediction

**Goal:** Predict which customers are likely to close their accounts, using a dataset of 10,000 client records with financial and demographic features.

**Approach**
- Built a preprocessing pipeline with `ColumnTransformer` — `StandardScaler` for continuous features (credit score, balance, engineered salary ratio) and `OneHotEncoder` for categorical ones.
- Used SMOTE inside an `imblearn` pipeline to correct class imbalance without leaking information between train and test folds.
- Tuned an XGBoost classifier with 3-fold cross-validated `GridSearchCV` (best parameters: `learning_rate=0.05`, `max_depth=5`, `n_estimators=150`).
- Used SHAP to explain predictions at both the individual and overall level.

**Results**
- ROC-AUC: 0.85
- Accuracy: 83%
- Recall on churned customers: 64%

**Key finding:** Older customers, customers based in Germany, and customers holding 3+ products showed the highest churn risk — giving a concrete basis for targeted retention campaigns.

**Stack:** Python, XGBoost, Scikit-learn, imbalanced-learn (SMOTE), SHAP

---

## 2. Multi-Touch Marketing Attribution

**Goal:** Compare how different attribution models credit marketing channels for conversions, using a dataset of 2,381 converting customer journeys.

**Approach**
- Reconstructed each customer's touchpoint sequence in chronological order.
- Calculated channel credit under three models:
  - **First-touch** — full credit to the first channel a customer interacted with
  - **Last-touch** — full credit to the final channel before conversion
  - **Linear** — credit split evenly across every touchpoint in the journey
- Built comparison visualizations in Seaborn to show how channel rankings shift depending on the model used.

**Key finding:** Display ads scored highest on first-touch (254), meaning they're strong at driving initial awareness. Referrals and email scored highest on last-touch (250 and 235), meaning they're strongest at closing conversions. Judging channels by a single attribution model alone would have misrepresented their actual contribution.

**Stack:** Python, Pandas, Seaborn, Matplotlib

---

## 3. Policy Search Engine (TF-IDF + Cosine Similarity)

**Goal:** Let users ask questions in plain language and retrieve the matching internal policy statement, without relying on an external LLM API.

**Approach**
- Vectorized a set of policy documents using `TfidfVectorizer` with English stop-word filtering.
- Matched incoming questions to policy vectors using cosine similarity, entirely locally — no data leaves the environment, and there's no API cost.

**Example**

| User question | Retrieved policy |
|---|---|
| "How do I cancel a fraudulent charge on my card?" | Customers can dispute credit card transactions within 60 days of the statement date by filing Form 404-B. |
| "What yield do I get on the premium savings option?" | The standard interest rate on a Premium Savings Account is 4.25% annually, with a $5,000 minimum deposit. |
| "How much cash can I pull out from the machine today?" | The daily ATM withdrawal limit across all standard debit cards is $1,000 per account. |

The system correctly matched informal, non-keyword phrasing to the right policy in each case.

**Stack:** Python, Scikit-learn (TF-IDF), NumPy

---

## Summary

| Project | Core skill demonstrated |
|---|---|
| Churn Prediction | Handling imbalanced data, model tuning, explainability |
| Attribution Dashboard | Turning raw logs into business-ready insight |
| Policy Search Engine | Lightweight, private NLP retrieval without external APIs |
