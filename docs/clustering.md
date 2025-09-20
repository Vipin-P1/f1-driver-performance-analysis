## Clustering

Clustering, a method for identifying patterns and grouping data based on shared characteristics, has been widely applied in diverse fields (1). In this research, clustering is used to analyse driver and constructor performance in Formula One, focusing on metrics such as qualifying times, race results, and driver consistency. This approach enables comparisons across drivers and reveals insights that guide future performance assessments. K-Medoids and OPTICS were chosen for this study due to their suitability for handling outliers and complex data patterns.

### K-Medoids

K-Medoids is selected primarily for its resilience to outliers, which is crucial for this dataset. Unlike K-Means, which uses mean values to define cluster centres, K-Medoids uses actual data points, making it more reliable when outliers are present.

![K-Medoids K-value iteration scores](f1-driver-performance-analysis/outputs/tables/K-Medoids Proximity measure scores.jpg)  
![Silhouette chart and Elbow chart](outputs/visuals/Silhouette Index chart & Elbow Curve.jpg)

Based on pre-processing, Cosine proximity emerged as the most suitable measure. The silhouette index results show that Cosine consistently achieves higher scores, and the elbow chart validates that K=3 is the optimal clustering solution.  

![Validity Indices](outputs/tables/Validity Indices.jpg)

An ideal clustering outcome is characterized by a higher Silhouette score, a lower Davies-Bouldin Index, and reduced Inertia (WCSS). In this study, K=3 achieved a silhouette score of 0.57 and a Davies-Bouldin Index of 1.13. Unlike WCSS alone, which emphasizes compactness, these combined metrics ensure clusters are cohesive and well-separated, making them appropriate for analyzing Formula One driver performance.

### OPTICS

OPTICS is a density-based algorithm capable of handling clusters of varying densities and irregular shapes, common in Formula One data. It does not require predefined cluster numbers and is robust to noise and outliers, making it adaptable for real-world datasets.

![OPTICS Proximity Index](outputs/tables/OPTICS Proximity based iterations.jpg)

By testing different values of Minimum Points (MinPts) and Epsilon, the optimal clustering result was again K=3, with MinPts set to 80 and Epsilon at 0.06. This configuration balances strong clustering scores with coverage of at least 80% of the data.

![Reachability Plot](outputs/visuals/Reachability Plot.jpg)

The reachability plot for K=3 shows clusters based on data point density. Densely packed areas indicate strong performance groupings, while sparse points are considered noise or outliers. This confirms the presence of three distinct and coherent clusters in the dataset.
