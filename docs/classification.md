## Classification

Classification is a **supervised learning** technique that assigns data points to predefined categories based on input features. It is widely used to uncover patterns and predict outcomes in various domains, including loan approval systems and medical diagnosis. In this study, classification was performed using **Orange Data Mining**, a visual programming platform that allows for building workflows with prebuilt widgets for data preprocessing, model training, and evaluation. The classification task focused on **predicting a driver’s likelihood of earning a podium finish** based on historical performance metrics such as qualifying lap times, race results, and pit stop durations. By creating a predictive model, this approach can help teams anticipate potential race outcomes and identify high-performing drivers.

![Classification Validity Scores](https://github.com/Vipin-P1/f1-driver-performance-analysis/blob/main/outputs/tables/Classification%20Methods%20-%20Validity%20Scores.jpg)

From the test results summarized in Table 8, **Naïve Bayes** and **Support Vector Machines (SVM)** emerged as the most effective classifiers. SVM achieved the highest **F1 score of 0.71**, balancing precision (0.74) and recall (0.67), indicating strong positive prediction accuracy with fewer false positives. Naïve Bayes, slightly lower in F1 score (0.69) and precision (0.64), excels in **recall (0.75)**, making it well-suited for scenarios prioritizing the identification of true positives.  

### Naïve Bayes & SVM

**Naïve Bayes** is valued for its ability to handle both categorical and continuous variables, assuming feature independence while providing interpretable confidence scores. It is particularly effective when sensitivity is crucial, as it minimizes false negatives.  

**Support Vector Machines (SVM)**, with a **Radial Basis Function (RBF) kernel**, are capable of capturing complex, nonlinear patterns in the data. This helps differentiate drivers based on subtle performance metrics like qualifying times, lap consistency, and race outcomes, ensuring robust classification even with overlapping feature distributions.

![ROC Curve](https://github.com/Vipin-P1/f1-driver-performance-analysis/blob/main/outputs/visuals/ROC%20Curve.jpg)  

![Performance Curve (AUC)](https://github.com/Vipin-P1/f1-driver-performance-analysis/blob/main/outputs/visuals/Performance%20Curves%20(AUC).jpg)

The **ROC curve** illustrates the trade-off between the true positive rate and false positive rate across thresholds, while the **Area Under the Curve (AUC)** quantifies overall classification performance. Here, SVM achieved an AUC of 0.767, reflecting strong class discrimination. Naïve Bayes, with an AUC of 0.69, still performs reliably in distinguishing between podium and non-podium finishes.  

![Confusion Matrices](https://github.com/Vipin-P1/f1-driver-performance-analysis/blob/main/outputs/tables/Confusion%20Matrices.jpg)

The **confusion matrices** provide a detailed view of prediction accuracy. Naïve Bayes correctly identified **150 out of 200 podium finishes**, while SVM correctly identified 134. For non-podium finishes, Naïve Bayes predicted 483 correctly compared to SVM’s 523. Naïve Bayes recorded fewer false negatives (50 vs. 66 for SVM), demonstrating its effectiveness in scenarios where minimizing missed podium predictions is critical.  

**Interpretation:** Both classifiers offer insights into driver performance prediction. SVM is slightly more balanced across precision and recall, whereas Naïve Bayes prioritizes sensitivity, effectively identifying high-performing drivers. Depending on whether teams want to **minimize false positives or false negatives**, either model could be applied strategically for performance analysis and race planning.  
