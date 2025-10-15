Customer Segmentation with Unsupervised Learning

Goal. Segment retail customers into actionable groups to enable targeted marketing, personalized offers, and smarter campaign allocation.

Data. Kaggle’s Customer Personality Analysis (marketing_campaign.csv). The dataset includes demographics (e.g., age, education, family composition), income, product-level spend (wines, fruits, meat, fish, sweets, gold), purchase channels (web, catalog, store), web visits, and campaign responses.

What I built.

Data cleaning. Dropped missing rows and removed extreme outliers (e.g., capping very high income/age ranges) to stabilize clustering.

Feature engineering.

Age from Year_Birth

Spent = sum of category-level expenditures

Household indicators: Children, Family_Size, Is_Parent

Simplified socio-demographics: grouped Education; normalized Marital_Status into Living_With (Partner vs. Alone)

Customer tenure Customer_For from Dt_Customer

Campaign engagement: Total_Promos (sum of accepted campaigns)

Encoding & scaling. Label-encoded categorical features and standardized all numeric fields for fair distance calculations.

Dimensionality reduction. Applied PCA (3 components) to denoise correlated spending/behavioral features and to support stable clustering and visualization.

Clustering.

Explored K-Means with elbow analysis (Yellowbrick KElbowVisualizer) to select a reasonable k.

Final segmentation produced with Agglomerative Clustering (Ward linkage) into 4 clusters, balancing separation and interpretability.

Profiling & visualization. Built cluster profiles using:

Income vs. total spend scatter (segment positioning)

Promotion acceptance distribution (Total_Promos)

Channel behavior (web/catalog/store purchases, web visits)

Demographic overlays (age, family size, parenthood, living situation)

Typical segment narratives.
(Names illustrative; grounded in the engineered features and plots.)

High-Income Heavy Spenders: premium categories, higher promo acceptance.

Value-Focused Families: larger Family_Size/Is_Parent, moderate spend, selective on promos.

Digital-First Savers: higher web purchases/visits, lower average spend, promo-responsive.

Low-Engagement Prospects: minimal spend and engagement; nurturing required.

Business impact.

Tailor campaigns by segment (e.g., premium bundles vs. promo-led nudges).

Prioritize channels (web/catalog/store) per segment behavior.

Improve CAC/LTV by focusing offers where conversion likelihood is highest.

Stack. Python, pandas, NumPy, scikit-learn (StandardScaler, PCA, KMeans, AgglomerativeClustering), Yellowbrick (elbow), Matplotlib/Seaborn.

Repro steps.

Load marketing_campaign.csv and drop NAs/outliers.

Engineer features (Age, Spent, Family_Size, Is_Parent, Customer_For, Total_Promos; normalize categories).

Encode & scale; run PCA (3 comps).

Use elbow to narrow k; fit Agglomerative (Ward, 4 clusters).

Generate profiles/plots; map segment narratives to marketing actions.
