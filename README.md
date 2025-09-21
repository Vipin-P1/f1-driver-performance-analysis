# F1 Driver Performance Analysis
Data-driven analysis of Formula 1 driver performance (2020–2023) using clustering, classification, and regression techniques.

## Project Overview

Formula One (F1) is a highly technical and financially-driven motorsport, where teams rely on financial backing from sponsorships, prize money, and other revenue sources. With constant innovation in performance, safety, and efficiency, teams incur significant costs in research and development. F1 generates billions in revenue annually, with a significant portion distributed to teams. The sport’s data-driven nature presents opportunities to improve performance analytics, which can impact team decision-making through predictive insights from data such as lap times, pit stops, and tire strategies.

## Problem Background

Even with top-tier resources and competitive cars, teams cannot achieve optimal results if drivers lack skill or consistency. Driver performance directly affects race outcomes and overall team success. Sponsorship revenue is heavily dependent on team performance, and underperforming teams often struggle to secure funding, which restricts car development and competitiveness.  

Analyzing driver performance through data-driven methods enables teams to make informed decisions on recruitment, race strategy, and resource allocation.

## Research Questions

The key questions for this project are:

1. **Driver Performance Clustering:** What categories of drivers emerge based on performance data such as lap times and pit stop durations?  
2. **Podium Finish Classification:** Which drivers are most likely to achieve a podium finish based on their qualifying performance?  
3. **Regression on Average Lap Time:** Which factors significantly influence a driver’s average lap time and overall race performance?

## Dataset

The analysis uses a dataset containing lap times, pit stop durations, qualifying results, and race outcomes:  

- [Raw Dataset](https://github.com/Vipin-P1/f1-driver-performance-analysis/tree/main/data/raw)  
- [Cleaned Dataset](https://github.com/Vipin-P1/f1-driver-performance-analysis/blob/main/data/DatasetModified.xlsx)  
- [Original Kaggle Source](https://www.kaggle.com/datasets/rohanrao/formula-1-world-championship-1950-2020)  

## Features Used for Analysis

![Feature Selection](https://github.com/Vipin-P1/f1-driver-performance-analysis/blob/main/outputs/tables/Feature%20Selection.jpg)

## Analytical Framework

The project follows a structured analytical framework combining **CRISP-DM** and **SEMMA**, ensuring a balance of strategic planning and technical rigor. CRISP-DM provides a high-level roadmap for understanding the business problem and aligning analysis goals with project objectives. SEMMA complements this by detailing iterative steps for data exploration, preparation, and modeling, allowing for robust evaluation at each stage.

![Framework](https://github.com/Vipin-P1/f1-driver-performance-analysis/blob/main/outputs/visuals/Framework.jpg)

Clustering, classification, and regression are the core modeling steps, refined iteratively using metrics such as silhouette scores, F1 scores, AUC, and regression statistics. This approach links technical analysis directly to actionable insights, providing a comprehensive view of driver performance and team dynamics.

## Project Documentation

The project is organized into the following sections:

- [Preprocessing & EDA](https://github.com/Vipin-P1/f1-driver-performance-analysis/blob/main/docs/00-preprocessing.md) – Data cleaning, outlier handling, feature transformation, and exploratory analysis.  
- [Clustering](https://github.com/Vipin-P1/f1-driver-performance-analysis/blob/main/docs/01-clustering.md) – K-Medoids and OPTICS clustering results, validation metrics, and interpretations.  
- [Classification](https://github.com/Vipin-P1/f1-driver-performance-analysis/blob/main/docs/02-classification.md) – Naive Bayes and SVM for podium finish prediction, ROC curves, and confusion matrices.  
- [Regression](https://github.com/Vipin-P1/f1-driver-performance-analysis/blob/main/docs/03-regression.md) – Linear and non-linear regression models predicting average lap times and key performance factors.  
- [Performance Insights & Limitations](https://github.com/Vipin-P1/f1-driver-performance-analysis/blob/main/docs/04-findings_limitations.md) – Combined interpretation of clustering, classification, and regression, including driver groupings and podium potential, along with limitations and recommendations.

---

## Tools & Libraries

```text
- Python (Preprocessing and Clustering)
- SPSS (Linear and Non-linear Regression)
- Orange (Classification Workflows)
- GitHub (Version Control)
