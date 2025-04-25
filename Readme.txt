COVID-19 Patient Segmentation using PCA and K-Means Clustering

📌 Project Overview
This project aims to perform unsupervised clustering on a COVID-19 patient dataset to uncover distinct patient phenotypes based on their clinical and demographic features. Using Principal Component Analysis (PCA) and K-Means clustering, we explore whether patients with similar health outcomes (e.g., pregnancy, intubation, fatality) group naturally in feature space — helping in early triage and treatment optimization.

🧠 Objectives
To reduce high-dimensional clinical data using PCA while retaining variance.

To apply K-Means clustering on transformed features to identify natural patient segments.

To evaluate cluster interpretability by overlaying medical outcomes such as:

PREGNANT

INTUBED

CLINICAL_DEATH

📊 Dataset Description
The dataset includes demographic, clinical, and outcome-related variables for COVID-19 patients.

Features include:

Age, gender, comorbidities

Medical interventions (e.g., ventilation, ICU)

Final outcomes (e.g., survived, deceased)

Each clustering stage used a preprocessed CSV with imputed missing values and encoded categorical variables.

🔧 Methodology
Data Preprocessing

Missing value imputation (mean/mode for numerical/categorical).

Label encoding and one-hot encoding for categorical features.

Feature scaling using MinMaxScaler.

Dimensionality Reduction

PCA was applied to transform features into uncorrelated components.

The first two principal components were retained (PC1, PC2) for visualization and clustering.

Clustering

K-Means clustering applied for k = 1 to 6.

Each k value generated a profiling report (using YData-profiling) to analyze intra-cluster feature patterns.

Visualization

PCA scatter plots overlaid with outcome labels (e.g., Pregnant, Intubated, Death) to assess separation.

Cluster-wise statistical summaries generated.

📈 Results & Insights
✅ PCA Outcome Mapping:
Pregnant patients clustered in the bottom-left (low PC1, low PC2).

Intubated patients appeared along positive PC1.

Deceased patients located in the top-left (low PC1, high PC2).

This confirms PC1 and PC2 effectively separate distinct clinical profiles.

✅ K-Means Clustering (Best at K=3 or K=4):
K=3 revealed three major groups:

Cluster 0: Pregnant/low-risk

Cluster 1: Intubated/high-intervention

Cluster 2: High-risk/fatalities

K=4–6 provided finer-grained insights like sub-stratification of middle-risk groups.

📊 Example Cluster Profile (K=3):

Cluster	 Size (%)     Mean Age	ICU Rate	Mortality Rate
0	 37%	       24.6	 1.2%	           0.1%
1	 42%	       56.8	 35.5%	           18.7%
2	 21%	       68.3	 48.9%	           65.3%
🧪 Tools & Technologies
Python, Pandas, NumPy

Scikit-learn (PCA, KMeans, preprocessing)

YData Profiling (Automated HTML Reports)

Matplotlib & Seaborn (Visualization)

Jupyter Notebook

🚀 Future Work
Integrate supervised models to predict cluster assignment.

Train models for survival prediction using cluster ID as a feature.

Build an interactive Streamlit dashboard for cluster exploration.

