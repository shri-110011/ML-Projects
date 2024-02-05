## SegmentSculptor: Carving Clusters in Mall Data

**Dataset Overview:**
Mall Customers dataset from Kaggle. The dataset has 200 rows and 5 columns.

**Objective:**
To do clustering/grouping of the data points based on the input features. 

**Approach:**
1. Did feature selection by dropping irrelevant columns.
2. Checked for missing values.
3. Applied Label Encoding/One-Hot-Encoding to categorical columns.
4. Applied Feature Scaling.
5. Model Selection and model building: Since there is no output column/target label we have an Unsupervised ML problem and we have to do customer segmentation so I have used the **K-Means Clustering Algorithm**.
6. Used the **Inertia(Within Cluster Sum of Squared Errors(WCSS)) vs k(# of clusters) plot** to find the suitable value of k.
7. Evaluated the model performance using **WCSS** and **Silhouette score**.
8. Created **Voronoi Diagrams** for the partitions created.
9. Reported the insights obtained from the clustering using the visualization.