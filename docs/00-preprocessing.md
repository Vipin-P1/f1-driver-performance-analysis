## Preprocessing

Preprocessing the Formula 1 dataset involved several key steps, including data cleaning, handling outliers, proximity analysis, and transforming features to prepare the dataset for modelling. Exploratory Data Analysis (EDA) was also performed to uncover patterns and relationships within the data. These steps ensure that the dataset is structured, clean, and ready for subsequent clustering, classification, and regression tasks. The preprocessing and descriptive statistics steps were executed in detail in [this notebook](https://github.com/Vipin-P1/f1-driver-performance-analysis/blob/main/code/Descriptive%20Stats.ipynb).

### Exploratory Data Analysis (EDA)

EDA focused on both numerical and categorical features. For numerical variables, visualizations like pairplots and box plots helped identify distributions, relationships, and potential outliers. Descriptive statistics provided further insights into the data's spread and variability, while a correlation heatmap revealed linear relationships between features, aiding feature selection. Categorical features were analysed using bar graphs to examine frequency distributions across teams, drivers, and points.

#### Numerical Features

**Descriptive Statistics and Correlation**

![Descriptive Stats table](https://github.com/Vipin-P1/f1-driver-performance-analysis/blob/main/outputs/tables/Descriptive%20Statistics.jpg)

Descriptive statistics indicate that variables such as `AvgLapTimeSeconds` (-0.09) and `FastestLapTimeSeconds` (-0.23) are nearly symmetrical, whereas `AvgPitDuration` (1.43) and `FastestPitstop` (0.98) are slightly right-skewed. Kurtosis highlights sharper peaks for some features, suggesting concentration near the mean and possible outliers. Variance shows that `FastestLapSpeed` has high variability (330.99), while qualifying times increase in variance from `Qualyfing1Seconds` (178.32) to `Qualyfing3Seconds` (1757.88). These patterns are further visualized in the pairplot.

![Pair Plot](https://github.com/Vipin-P1/f1-driver-performance-analysis/blob/main/outputs/visuals/Pairplot-F1.png)  
![Correlation Heatmap](https://github.com/Vipin-P1/f1-driver-performance-analysis/blob/main/outputs/visuals/Correlation%20Heatmap.jpg)

The pairplot and correlation matrix show strong relationships, such as between `AvgLapTimeSeconds` and `FastestLapTimeSeconds` (0.98), and `AvgPitDuration` and `FastestPitstop` (0.93). Qualifying performance is also linked to race performance, with `Qualyfing1Seconds` correlating strongly with `AvgLapTimeSeconds` (0.90).

**Outlier Analysis**

Initial outlier analysis revealed extreme values primarily caused by drivers who did not finish races, missed qualifying, or were affected by unusual events (e.g., the 2021 Belgian Grand Prix halted on lap 3). These extreme outliers were removed to focus on typical race conditions.  

![Boxplot Avg Laptime & FastestLapTime](https://github.com/Vipin-P1/f1-driver-performance-analysis/blob/main/outputs/visuals/BoxPlot%20-%20Avg%20%26%20Fastest%20Lap%20TIme%20Seconds.jpg)  
![Boxplot Fastest Lapspeed & AvgPit Duration](https://github.com/Vipin-P1/f1-driver-performance-analysis/blob/main/outputs/visuals/BoxPlot%20-%20Fastest%20Lap%20Speed%20%26%20Avg%20Pit%20Duration.jpg)  
![BoxPlot - Fastest Pitstop & Qualifying 1 Seconds](https://github.com/Vipin-P1/f1-driver-performance-analysis/blob/main/outputs/visuals/BoxPlot%20-%20Fastest%20Pitstop%20%26%20Qualifying%201%20Seconds.jpg)  
![BoxPlot - Qualifying 2 & 3 Seconds](https://github.com/Vipin-P1/f1-driver-performance-analysis/blob/main/outputs/visuals/BoxPlot%20-%20Qualifying%202%20%26%203%20Seconds.jpg)

After removing extreme outliers, additional values in `FastestPitStop` and `AvgPitDuration` were retained as they reflect actual driver and pit crew performance. Outliers in qualifying data were also retained to reflect the elimination process, which naturally places bottom drivers in later positions.

#### Categorical Features

![Bar Graphs - Grid & Position Order](https://github.com/Vipin-P1/f1-driver-performance-analysis/blob/main/outputs/visuals/Bar%20Graphs%20-%20Grid%20%26%20Position%20Order.jpg)  
![Bar Graphs - Total Pitstops & Points](https://github.com/Vipin-P1/f1-driver-performance-analysis/blob/main/outputs/visuals/Bar%20Graphs%20-%20Total%20Pitstops%20%26%20Points.jpg)  
![Bar Graphs - Constructors & Drivers](https://github.com/Vipin-P1/f1-driver-performance-analysis/blob/main/outputs/visuals/Bar%20Graphs%20-%20Constructors%20%26%20Drivers.jpg)

Grid positions and starting orders follow expected patterns, with early positions being more frequent. A "0" in the grid indicates a pit lane start due to penalties. Points distribution is uneven, with Max Verstappen and Red Bull Racing leading both driver and constructor points across all races.

### Proximity Analysis

Cosine similarity was applied to numerical features to capture relative relationships between drivers, while Jaccard similarity was used for categorical features. This combination allows for assessing both quantitative and categorical differences without being overly sensitive to outliers.

![Dissimilarity Matrix](https://github.com/Vipin-P1/f1-driver-performance-analysis/blob/main/outputs/visuals/Dissimilarity%20Matrix%20Heatmap.png)

The dissimilarity matrix shows distinct patterns, for example, George Russell and Lance Stroll (0.90) exhibit similar performance patterns, whereas Max Verstappen and Pierre Gasly (1.51) display very different profiles.

### Preprocessing Summary

- **Data Cleaning:** Already addressed during data gathering; no further cleaning required.  
- **Data Integration:** Not required as the dataset comes from a single source.  
- **Data Reduction:** Outlier removal and feature selection reduce unnecessary data points.  
- **Data Transformation:** Lap times and pit stop durations were converted to seconds; normalization is handled during modelling. Label encoding was not needed since categorical features are numeric.  
- **Data Discretization:** Not applied, as continuous data was used for analysis.
