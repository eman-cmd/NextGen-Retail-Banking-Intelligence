# 🏦 NextGen Retail Banking: Digital Banking Analytics & AI Portfolio

A suite of three end-to-end data science, marketing analytics, and localized AI retrieval engines built to solve core problems in digital banking: customer retention, campaign ROI, and internal knowledge search.

---

## 📊 1. Bank Customer Churn Prediction Engine
**Stack:** `Python` | `XGBoost` | `Scikit-Learn` | `Imbalanced-Learn (SMOTE)` | `SHAP`

*   **Goal:** Predict which retail clients are likely to close their accounts using a dataset of 10,000 customer records.
*   **Approach:** 
    *   Built a robust preprocessing pipeline using `ColumnTransformer` (StandardScaler for continuous metrics like balance/salary and OneHotEncoder for categorical features).
    *   Handled severe class imbalance using SMOTE within a unified `ImbPipeline` framework to prevent data leakage between validation folds.
    *   Optimized an XGBoost classifier using 3-fold cross-validated `GridSearchCV` (`learning_rate=0.05`, `max_depth=5`, `n_estimators=150`).
    *   Deployed `SHAP TreeExplainer` to calculate and visualize game-theoretic feature contributions.
*   **Results:** Achieved a **0.85 ROC-AUC score**, **83% overall accuracy**, and a **64% recall rate** on the minority churn class.
*   **Business Impact:** Uncovered that mature demographics, specific regional segments (Germany), and accounts holding 3+ financial products represent the highest velocities of churn, providing a concrete basis for targeted retention campaigns.

---

## 📈 2. Multi-Touch Marketing Campaign Attribution Engine
**Stack:** `Python` | `Pandas` | `Seaborn` | `Matplotlib`

*   **Goal:** Reconstruct customer conversion journeys to analyze how single-touch attribution models distort marketing channel performance.
*   **Approach:** 
    *   Parsed raw conversion logs to chronologically map out interaction sequences for 2,381 successful buying pathways.
    *   Programmed mathematical allocation logic contrasting **First-Touch**, **Last-Touch**, and **Linear** multi-touch attribution models.
    *   Constructed comparative data visualizations to isolate exact customer channel entry and exit behaviors.
*   **Results:** Proved that judging channels by a single attribution model heavily misrepresents their financial value. 
*   **Business Impact:** Discovered that Display Ads dominate top-of-funnel discovery (scoring highest on first-touch), while Referrals and Email excel at closing final conversions (scoring highest on last-touch), allowing marketing teams to optimize overall Customer Acquisition Costs (CAC).

---

## 🔍 3. Privacy-First Policy Search Engine (Local RAG Prototype)
**Stack:** `Python` | `Scikit-Learn` | `NumPy`

*   **Goal:** Build a lightweight, local Retrieval-Augmented Generation (RAG) prototype to match plain-language inquiries to internal banking policies without data hallucination risks or third-party cloud API exposure.
*   **Approach:** 
    *   Vectorized unstructured institutional policy documentation using `TfidfVectorizer` with English stop-word filtering.
    *   Implemented geometric math via `Cosine Similarity` to calculate the distance between conversational questions and text chunks entirely locally.
*   **Sample Performance:**
    *   *User:* "How do I cancel a fraudulent charge on my card?" ➔ *Retrieved Clause:* "Customers can dispute credit card transactions within 60 days... by filing Form 404-B."
    *   *User:* "How much cash can I pull out from the machine today?" ➔ *Retrieved Clause:* "The daily ATM withdrawal limit across all standard debit cards is $1,000 per account."
*   **Results:** Successfully matched informal, non-keyword customer phrasings to corresponding compliance clauses with high mathematical confidence scores, with **zero latency or external API cost**.

---

## 🛠️ Summary Matrix

| Project | Core Skill Demonstrated | Primary Impact |
| :--- | :--- | :--- |
| **Churn Prediction** | Class imbalance, Hyperparameter tuning, Explainable AI | Targeted customer retention |
| **Attribution Engine** | Time-series data parsing, ROI modeling, Visualization | Marketing spend optimization |
| **Policy Search Engine** | Vector embedding math, Local NLP retrieval (RAG) | Low-cost, secure internal search |
