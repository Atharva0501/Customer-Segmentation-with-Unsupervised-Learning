# Customer Segmentation with Unsupervised Learning

Segment retail customers into actionable groups using PCA + clustering (K-Means & Agglomerative) on the **Customer Personality Analysis** dataset. The notebook walks through data cleaning, feature engineering, dimensionality reduction, clustering, and plain-English segment profiles to inform targeting, channel mix, and offers.

---

## ✨ Key Features
- **End-to-end pipeline:** EDA → cleaning/outliers → feature engineering → scaling → **PCA** → clustering → profiling
- **Modeling:** K-Means (elbow method) exploration, **Agglomerative (Ward linkage)** for final interpretable segments
- **Profiles & visuals:** income vs. spend positioning, promo engagement, channel behavior (web/catalog/store), demographics
- **Actionability:** segment narratives mapped to marketing levers (bundles, promo cadence, digital-first retention, nurturing)

---

## 📊 Dataset
- **Name:** Customer Personality Analysis (marketing_campaign.csv)
- **Signals:** demographics (age, education, family), income, product spend (wines, fruits, meat, fish, sweets, gold), channels (web/catalog/store), web visits, campaign responses, and join date.


---

## 🛠️ Methods & Engineering
- **Feature engineering:**
  - `Age` from `Year_Birth`
  - `Spent` = sum of category spends
  - Household: `Children`, `Family_Size`, `Is_Parent`
  - `Customer_For` from `Dt_Customer` (tenure)
  - Campaign engagement: `Total_Promos` (sum of accepted campaigns)
  - Normalized `Education`/`Marital_Status` (e.g., `Living_With`)
- **Preprocessing:** label/one-hot encoding as needed, **StandardScaler** for numeric features
- **Dimensionality reduction:** **PCA (≈3 comps)** to denoise and stabilize clustering
- **Clustering:** K-Means (elbow/score curves) → **Agglomerative (Ward)** finalized (e.g., **4 clusters**)
- **Evaluation:** separation/compactness (inertia silhouette via exploration), interpretability via profiles and plots

---

## 🧭 Segment Narratives (illustrative)
- **High-Income Heavy Spenders:** premium categories, higher promo acceptance  
- **Value-Focused Families:** larger family size, moderate spend, selective promos  
- **Digital-First Savers:** more web purchases/visits, lower average spend, promo-responsive  
- **Low-Engagement Prospects:** minimal spend/engagement; nurturing required

> Calibrate names and descriptions to your notebook’s charts and summary stats.

---


