# f1-driver-performance-analysis
Data-driven analysis of Formula 1 driver performance (2020–2023) using clustering, classification, and regression techniques.

## Project Overview

Formula One (F1) is a highly technical and financially-driven motorsport, valued at over $12 billion (Mourão, 2017), where teams rely on financial backing from sponsorships, prize money, and other revenue sources. With constant innovation in performance, safety, and efficiency, teams incur significant costs in research and development (Jenkins & Floyd, 2001). In 2023, F1 generated over $3.2 billion in revenue, with about 50% distributed to teams through the Concorde Agreement (Formula One Management Limited, 2021). The increasing valuation of teams (Ozanian & Knight, 2023) and the sport’s data-driven nature present opportunities to improve performance analytics, which can also impact sports betting and team decision-making through predictive insights from data such as lap times, pit stops, and tire strategies.

## Problem Background

Even with top-tier resources and competitive cars, teams cannot achieve optimal results if drivers lack skill or consistency. Aston Martin's F1 journey highlights this balance: Lawrence Stroll’s $135 million investment (Garrahan, 2023) enabled Fernando Alonso to achieve fourth in the 2023 Drivers' Championship (Formula One World Championship Limited, 2023), while Lance Stroll finished over 100 points behind Alonso despite driving the same car. This demonstrates that driver performance is critical to translating resources into results.

Sponsorship revenue is heavily dependent on team performance, representing 18% of total income in 2023 (Liberty Media Corporation, 2023) and skewed toward successful teams due to media exposure. Historical examples, such as Renault in 2006 securing US$136 million in sponsorships versus Midland F1's US$43.5 million (Judde et al., 2013), show that performance directly impacts financial stability. Underperforming teams, including Prost, Arrows, and Super Aguri, struggled to secure sponsorships, which restricted car development and ultimately led to their closure (Sanderson, 2002; Edworthy, 2002; Jake, 2016).

Given these dynamics, analyzing driver performance through data-driven methods becomes essential. Understanding which drivers are likely to perform consistently allows teams to make informed decisions on recruitment, strategy, and investment.

## Research Questions

Based on exploratory analysis and preprocessing, the key research questions for this study are:

1. **Driver Performance Clustering:** What categories of drivers emerge based on performance data such as lap times and pit stop durations?  
2. **Podium Finish Classification:** Which drivers are most likely to achieve a podium finish based on their qualifying performance?  
3. **Regression on Average Lap Time:** Which factors significantly influence a driver’s average lap time and overall race performance?

## Dataset

The analysis uses a dataset that includes lap times, pit stop durations, qualifying results, and race outcomes.  

- [Raw Dataset](https://github.com/Vipin-P1/f1-driver-performance-analysis/tree/main/data/raw)  
- [Cleaned Dataset](https://github.com/Vipin-P1/f1-driver-performance-analysis/blob/main/data/DatasetModified.xlsx)  
- [Original Kaggle Source](https://www.kaggle.com/datasets/rohanrao/formula-1-world-championship-1950-2020)  

## Features Used for Analysis

![Feature Selection](https://github.com/Vipin-P1/f1-driver-performance-analysis/blob/main/outputs/tables/Feature%20Selection.jpg)

## Analytical Framework

The analytical framework for this project combines **CRISP-DM** and **SEMMA**, creating a structured approach that integrates strategic planning with technical rigor. CRISP-DM provides a high-level roadmap, emphasizing business understanding and ensuring alignment with the objectives of identifying high-performing drivers and predicting podium finishes. SEMMA complements this by detailing iterative processes for data exploration, preparation, and modelling, ensuring robust evaluation at each stage.

![Framework](https://github.com/Vipin-P1/f1-driver-performance-analysis/blob/main/outputs/visuals/Framework.jpg)

Clustering, classification, and regression models are core steps within the workflow, allowing for iterative refinement based on performance metrics such as silhouette scores, F1 scores, AUC, and regression statistics. This approach ensures that technical analysis is directly linked to actionable insights, providing a comprehensive understanding of driver performance and team dynamics.

## Project Documentation

The project analysis is structured into the following sections:

- [Preprocessing & EDA](https://github.com/Vipin-P1/f1-driver-performance-analysis/blob/main/docs/00-preprocessing.md) – Data cleaning, outlier handling, feature transformation, and exploratory analysis.
- [Clustering](https://github.com/Vipin-P1/f1-driver-performance-analysis/blob/main/docs/01-clustering.md) – K-Medoids and OPTICS clustering results, validation metrics, and interpretations.
- [Classification](https://github.com/Vipin-P1/f1-driver-performance-analysis/blob/main/docs/02-classification.md) – Naive Bayes and SVM for podium finish prediction, ROC curves, and confusion matrices.
- [Regression](https://github.com/Vipin-P1/f1-driver-performance-analysis/blob/main/docs/03-regression.md) – Linear and non-linear regression models predicting average lap times and key performance factors.
- [Performance Insights & Limitations](https://github.com/Vipin-P1/f1-driver-performance-analysis/blob/main/docs/04-findings_limitations.md) – Combined interpretation of clustering, classification, and regression, including driver groupings and podium potential, along with limitations and recommendations.

---

## Tools & Libraries

The following tools and software were used for analysis:

```text
- Python (Preprocessing and Clustering)
- SPSS (Linear and Non-linear Regression)
- Orange (Classification Workflows)
- GitHub (Version Control)
