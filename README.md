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
