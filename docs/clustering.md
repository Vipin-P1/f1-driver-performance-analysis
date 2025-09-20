## Clustering

Clustering is a technique for identifying patterns and grouping data based on shared characteristics, widely used across multiple domains for exploratory analysis (1). In this study, clustering is applied to analyze Formula One driver and constructor performance, focusing on metrics such as qualifying times, race results, and driver consistency. By organizing drivers into performance-based groups, clustering allows us to identify patterns that may not be immediately obvious, providing valuable insights for both performance evaluation and team strategy planning. For this analysis, two clustering techniques—**K-Medoids** and **OPTICS**—were selected for their ability to handle outliers and complex data structures.  

### K-Medoids

**K-Medoids** was chosen due to its robustness against outliers. Unlike K-Means, which calculates cluster centers as the mean of points, K-Medoids selects actual data points as cluster centers, ensuring that extreme values do not disproportionately affect cluster formation.  

![K-Medoids K-value iteration scores](https://github.com/Vipin-P1/f1-driver-performance-analysis/blob/main/outputs/tables/K-Medoids%20Proximity%20measure%20scores.jpg)  

To determine the optimal number of clusters, various proximity measures were tested, with **Cosine proximity** emerging as the most effective. The silhouette index confirms that Cosine consistently achieves higher cohesion and separation between clusters, while the elbow method validates that **K=3** provides the most meaningful grouping for the dataset.  

![Silhouette chart and Elbow chart](https://github.com/Vipin-P1/f1-driver-performance-analysis/blob/main/outputs/visuals/Silhouette%20Index%20chart%20%26%20Elbow%20Curve.jpg)  

Further evaluation of cluster quality using the Silhouette Index, Davies-Bouldin Index, and Inertia (WCSS) indicates that K=3 achieves a Silhouette score of 0.57 and a Davies-Bouldin Index of 1.13. These metrics demonstrate that the clusters are cohesive and well-separated, offering a reliable segmentation of driver performance.  

![Validity Indices](https://github.com/Vipin-P1/f1-driver-performance-analysis/blob/main/outputs/tables/Validity%20Indices.jpg)  

Overall, K-Medoids successfully groups drivers into **three performance categories**: Frontrunners, Midfielders, and Backmarkers, highlighting consistent differences in lap times and pit durations. For reproducibility, the clustering code can be accessed [here](https://github.com/Vipin-P1/f1-driver-performance-analysis/blob/main/code/Clustering%20-%20K-Medoids.ipynb).  

### OPTICS

**OPTICS** (Ordering Points To Identify the Clustering Structure) is a density-based clustering algorithm suitable for datasets with clusters of varying densities and irregular shapes. Unlike K-Medoids, OPTICS does not require specifying the number of clusters in advance and is robust to noise, making it ideal for real-world Formula One data.  

![OPTICS Proximity Index](https://github.com/Vipin-P1/f1-driver-performance-analysis/blob/main/outputs/tables/OPTICS%20Proximity%20based%20iterations.jpg)  

By experimenting with different **Minimum Points (MinPts)** and **Epsilon** values, the algorithm produced the most meaningful clustering with **MinPts=80** and **Epsilon=0.06**, again supporting the formation of three primary clusters. This configuration balances strong clustering validity with sufficient coverage of over 80% of the dataset.  

![Reachability Plot](https://github.com/Vipin-P1/f1-driver-performance-analysis/blob/main/outputs/visuals/Reachability%20Plot.jpg)  

The reachability plot illustrates cluster density: densely packed regions correspond to drivers with similar performance characteristics, while sparse points represent noise or outliers. These results corroborate the K-Medoids findings, confirming the existence of **three distinct and coherent performance groups**. For reference, the OPTICS code is available [here](https://github.com/Vipin-P1/f1-driver-performance-analysis/blob/main/code/Clustering%20-%20OPTICS.ipynb).  

**Interpretation:** Both clustering approaches reveal consistent patterns in driver performance. Frontrunners exhibit fast lap times and short pit stops, Midfielders show moderate consistency, and Backmarkers are slower with higher variability. By combining these clustering insights with classification and regression analyses, teams can better assess driver potential and inform recruitment or strategy decisions.  
