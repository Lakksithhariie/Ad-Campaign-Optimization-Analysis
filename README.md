# Ad Campaign Optimization using Clustering Analysis
[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1pcNVIuy8h3476h0hp_9MgaBzdHj9CBbY?usp=sharing)

## What is this project?

This project uses clustering analysis to help optimize advertising campaigns. We analyze a dataset of ad campaign performance to identify different groups of users based on their behavior and characteristics. The goal is to understand these groups so that ad campaigns can be better targeted and more effective.

## Where did the data come from?

The data for this project is provided in the `Dataset_Ads.csv` file included in this repository. It contains simulated data related to online advertising campaigns, including user demographics, ad types, engagement metrics, and conversion rates.

## What did I do?

In this project, I took the following steps to analyze the ad campaign data and derive optimization strategies:

1.  **Explored the Dataset:** Loaded the `Dataset_Ads.csv` file using pandas and performed initial exploratory data analysis (EDA). This included:
    *   Displaying the first few rows of the dataset to understand its structure and features.
    *   Checking the dataset's shape, data types, and summary statistics to identify data characteristics and potential issues like missing values or outliers.
    *   Visualizing the distribution of key numerical features like 'Income' and 'Conversion Rate' using histograms to understand their spread and identify any patterns.

2.  **Preprocessed the Data for Clustering:** Prepared the data to be suitable for clustering algorithms. This involved:
    *   Selecting relevant features for clustering, including numerical features ('Income', 'Conversion Rate') and categorical features ('Ad Type', 'Ad Topic', 'Ad Placement').
    *   Using `MinMaxScaler` to scale numerical features to a range between 0 and 1, ensuring that features with larger values do not disproportionately influence the clustering process.
    *   Employing `OneHotEncoder` to convert categorical features into a numerical format that machine learning algorithms can process, effectively creating binary columns for each category.
    *   Combining the preprocessed numerical and categorical features into a single feature matrix, ready for clustering.

3.  **Applied K-Means Clustering:** Utilized the K-Means algorithm to group users into distinct clusters based on their preprocessed features. This included:
    *   Using the Elbow Method to determine the optimal number of clusters (`k`). By plotting the inertia (within-cluster sum of squares) against different values of `k` (from 1 to 10), the "elbow" point on the graph was visually identified to suggest a suitable `k`.
    *   Fitting the KMeans model to the preprocessed data with the chosen `k` value (in this case, `k=3`).
    *   Adding the cluster labels back to the original DataFrame as a new 'Cluster' column for further analysis and interpretation.

4.  **Analyzed and Visualized Clusters:** Interpreted the resulting clusters to understand the characteristics of each user segment. This involved:
    *   Examining the distribution of users across clusters to check for balanced or imbalanced clusters.
    *   Calculating and displaying the mean values of key numerical features (Age, Income, Conversion Rate, CTR, Clicks) for each cluster to identify differences in central tendencies.
    *   Visualizing the distribution of 'Income', 'Conversion Rate', and 'CTR' across clusters using boxplots to compare the spread and identify potential outliers within each segment.
    *   Visualizing the distribution of the categorical feature 'Gender' across clusters using countplots to understand demographic differences.

5.  **Generated Actionable Insights and Recommendations:** Based on the cluster analysis, I derived actionable insights and recommendations for optimizing ad campaigns.  This involved:
    *   Identifying high-performing clusters based on metrics like 'Conversion Rate' and 'CTR'.
    *   Analyzing the demographic and behavioral traits of these high-performing clusters to understand what makes them unique and successful.
    *   Formulating targeted marketing recommendations, suggesting how to tailor ad content, topics, and placements to better engage and convert users within each cluster.

## What are the main findings?

*   **Three Distinct Customer Segments:** The K-Means clustering analysis identified three distinct clusters of users within the dataset, each exhibiting different patterns of behavior and characteristics.
*   **Cluster 2 Shows High Performance:**  Cluster 2 consistently demonstrated the highest average Conversion Rate and CTR compared to other clusters, indicating it as a high-performing segment.
*   **Targeted Marketing Opportunities:** By analyzing the demographic and behavioral traits of Cluster 2, marketers can gain valuable insights into the preferences and characteristics of high-converting users. This knowledge can be used to tailor ad campaigns specifically for this segment, potentially leading to improved campaign performance and ROI.
*   **Data-Driven Optimization:** This project demonstrates how clustering analysis can be a powerful tool for data-driven ad campaign optimization, enabling marketers to move beyond broad targeting and towards more personalized and effective strategies.

## How can you run this code?

1.  **Open in Google Colab:** Click the badge at the top that says "Open In Colab". This will open the project in your web browser, allowing you to run the code without any local setup.
2.  **Run the code cells:** In Colab, step through the notebook sequentially, executing each code cell by clicking the "Play" button or pressing `Shift + Enter`. The notebook is designed to be run from top to bottom, with each cell building upon the previous ones.
