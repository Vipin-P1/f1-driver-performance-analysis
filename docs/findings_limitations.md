## Overall Insights and Limitations

The clustering analysis identified three distinct performance groups: **Frontrunners**, **Midfielders**, and **Backmarkers**.  
- Frontrunners showed consistently fast lap times and short pit durations, with narrow IQRs reflecting strong reliability.  
- Backmarkers displayed higher lap times, longer pit stops, and wide IQRs, indicating weaker and less consistent performance.  
- Midfielders fell between these two extremes, showing moderate performance with some variability.  

![Clustering Results](https://github.com/Vipin-P1/f1-driver-performance-analysis/blob/main/outputs/tables/Clustering%20result%20tables%20(K-Medoids%20%26%20OPTICS).jpg)

Examining performance across the 2020–2023 seasons further highlighted consistency. Drivers such as **Lewis Hamilton** and **Max Verstappen** were consistently classified as frontrunners, while **Yuki Tsunoda** typically appeared as a midfielder, and **Mick Schumacher** was often categorized as a backmarker. This consistency across multiple races strengthens the validity of the clustering outcomes.  

Classification complemented clustering by evaluating the likelihood of podium finishes. Naive Bayes recorded **25% false negatives (50/200)** and **15.1% false positives (86/569)**, while SVM showed **33% false negatives (66/200)** and **8.1% false positives (46/569)**.  
In Formula 1, minimizing false negatives is crucial for accurately identifying podium finishers—critical for recruitment and sponsorship. Naive Bayes, with its lower false negative rate, proved more effective in reinforcing clustering insights and spotlighting top performers.

![Classification Accuracy](https://github.com/Vipin-P1/f1-driver-performance-analysis/blob/main/outputs/visuals/Classification%20Accuracy%20Result.jpg)

Regression supported both clustering and classification by identifying how factors such as qualifying times and pit stop durations influence outcomes. Linear and non-linear regression confirmed the significance of qualifying performance as a predictor, while also showing that certain variables (e.g., Qualifying2 and Qualifying3 times) added little explanatory power. Together, these methods provided a **comprehensive view of driver performance** by combining group-level patterns, predictive accuracy, and factor-level insights.

---

### Limitations and Recommendations

While the findings are valuable, several limitations must be acknowledged:  
- **Limited feature scope**: Only lap times, pit durations, and results were considered. Other factors like laps led, penalties, and weather conditions were excluded but could enhance model performance.  
- **Car and team effects**: This analysis overlooks technical specifications and engineering factors. Prior research highlights the importance of team knowledge, innovation, and technical discontinuities in shaping performance.  
- **Driver physiology**: Studies suggest traits like grip and leg strength can impact performance, but such variables were not available in this dataset.  
- **Race strategy**: Pit stop strategy, tire management, and in-race decisions can significantly affect outcomes, yet they were outside the scope of this analysis.  
- **External influences**: Track conditions, regulatory changes, and other environmental variables were not considered, despite evidence that they play a major role in competitive dynamics.  

### Future Work  
Future research should integrate these additional dimensions—technical, tactical, physiological, and external factors—to deliver a richer, more holistic view of driver and team performance. Doing so will not only improve predictive accuracy but also provide insights with greater strategic value for teams, drivers, and sponsors.
