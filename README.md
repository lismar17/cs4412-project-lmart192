# cs4412-project-lmart192
Lisbeth Martinez

Project Title: Identifying Streaming Behavior Across Attributes of
Region and Genre

Description: 
Understanding patterns in music streaming plat-
forms allows labels and artists to visualize how their music is most
listened to. Clustering streams by genre and sorting by region
enables companies to establish a strategic domain impact. Using
data gathered by Atharva Soundankar, this research utilizes
association rules and text mining to discover possible connection
between location and genre of song streamed.

Data sourced from Kaggle - Global Music Streaming Listener Preferences dataset

Numerical: Age, Minutes Streamed, Songs Liked, Discover Weekly Engagement, Repeat Song Rate
Categorical: Country, Platform, Genre, Subscription Type, Listening Time

Update M2:
Using Jupyter Notebook (ACCESS THE dataM2(2) VERSION), data has been processed using preprocessing, displayed with EDA, and transformed for application of association rules.
Contents include:
1. Data loading and Overview
2. Exploratory Data Analysis with Visualizations
3. Data Transformation and Applying the Mining Technique
4. Preliminary Findings with Interpretation

Visualizations completed in M2
Genre-by-country pivot table to compare listening preferences geographically, 
Genre boxplot by country counts to identify regional outliers, 
Country vs genre countplot for comparative frequency patterns, 
Age vs genre countplot to inspect age skews, 
Top-6 genre line chart across age groups for simplified trend analysis

Key observations in M2
Germany showed a strong EDM spike (71 listeners), 
South Korea showed higher Hip-Hop and Rock concentration, 
Jazz and Rock varied across younger vs older age groups, 
Some genres showed regional skew that may influence age-based interpretation

M2 applies Apriori Association rule mining using mlxtend:

Parameters used
Minimum support: 0.05, 
Rule metric: lift, 
Minimum lift threshold: 1.0

Transactions included:

Country, 
Streaming Platform, 
Top Genre, 
Subscription Type, 
Listening Time, 
Binned engagement features

Important changes to code from M2 feedback:  
Threshold was changed from 1 to 0.6, 
Manual bins were replaced with quantile bins.

Update M3:
Building off of existing work in Jupyter notebook and reflecting off of feedback from M2, as previously mentioned, M3 includes the use of K-Means cluster averages, greater use of histograms, and cluster and heat  map visuals.
M3 improves on M2 by validating descriptive trends with clustering, PCA, decision trees, and refined rule mining. The findings now move beyond chart-level observations into explainable listener personas and platform behaviors, while still identifying open questions related to causality, regional influence, and external cultural factors with external academic articles.
K-Means Clustering created four clusters which were interpreted as the following categories: Loyal Repeat Listeners, Heavy Explorers, Casual Selective Users, and Light Replay Users. This allowed for easier identification of repeated user behavior.

The academic articles used for the Geographical Context section are cited below:

Matos, Michaelangelo. "electronic dance music". Encyclopedia Britannica, 1 Jan. 2026, https://www.britannica.com/art/electronic-dance-music. Accessed 2 April 2026.

Anderson, Crystal S, 'Global South Korea and the K-Pop Phenomenon' (28 Aug. 2018), in Diedre Shauna Lynch (ed.), Oxford Research Encyclopedia of Literature (New York, NY, online edn, Oxford Academic, 31 Aug. 2016 - ), https://doi.org/10.1093/acrefore/9780190201098.013.770, accessed 3 Apr. 2026.

Update M4:
Addressed feedback with association and apriori rules returning empty cells: Association rules were not loading because "lift" was changed to "confidence", so the code could not find waht it was referencing. As lift is what holds the values, mistakenly using confidence prevented the data from appearing. After M3, I could not find the issue until requesting help from the tutoring center in reviewing my code.

Addressed feedback with undefined x and y for decision trees: 
X = df[[
    "Minutes Streamed Per Day",
    "Number of Songs Liked",
    "Discover Weekly Engagement (%)",
    "Repeat Song Rate (%)"
]]

y = df["Behavior Cluster"]

Justifying K=4:
For the silhouette score, scores are low, and thus have a weak separation of clusters, remaining between ~0.17 and 0.22. While the highest score exists at k=8, the weak separation below 0.25 indicates that the dataset does not form strongly separated clusters. Along with this, higher k values risk over-segmentation, where clusters become too granular and lose meaningful interpretation. In comparison, a 4-cluster solution produces distinct and interpretable listener segments. It is optimal as it offers a balance between interpretation and clustering quality.

With the elbow plot, we see a sharp drop from 2 to 4, with the points after that dropping at a slower rate. Therefore, 4 can be further argued to be a clear transition point, with five as a reasonable alternative, as it is only diminishing returns afterward.

Cluster characterizations printed with the code in cell 165 so cluster characterizations are grounded in actual numbers.

Cross-tabulation inserted in Geographical Context section.
