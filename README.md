# Rwanda School Attendance Capstone Project.

 ## The Overview Of project.
 Welcome to the Rwanda School Enrollment Capstone Project!This Initiative analyzes attendance trends and gender disparities in primary school education Rwanda from 2013 to 2023.The primary focus is on understanding how well children attend school (it is measured by the Net Attendance Rate,or NAR) and identifying disparities,especially accross provinces and clusters.This project stems from the need to address educational equity,using data collected from reputable sources that is statistics.gov.rw.The goal is to provide the actionale insights for policymakers and educators to improve attendance and , ultimately,enrollement outcomes.

 ### 1. Setting Up Python Environment
The process began by importing essential Python libraries in a Jupyter Notebook (`Primary_analysis.ipynb`):
- `pandas` and `numpy` for data manipulation.
- `matplotlib` and `seaborn` for visualizations.
- `scikit-learn` for machine learning (clustering and evaluation).
- Warnings were suppressed, and a whitegrid style was set for clear plots.
   [Library](importlibraries.PNG)
  
  ### 2. Loading and Exploring Data
The `primary.csv` dataset was loaded using a custom `load_data` function, 
skipping initial rows and renaming columns such as  `gar_both`, `nar_both`, `province_district`. 
Initial checks included column names, a preview of the data, and info on missing values and data types,
 confirming 35 entries with some missing NAR(Net_Attendance_Rate) and Gross_Attendance_Rate(GAR) values.

 [Load datset](loading.PNG)
 
 ### 3. Data Cleaning
The `clean_data` function handled missing values by dropping rows with `NaN`, 
converted numeric columns to appropriate types, and removed unrealistic outliers like (GAR > 200% or NAR > 100%). 
Post-cleaning, the dataset had 30 complete records, with statistics showing NAR ranging from 78.5% to 96% and GAR from 125% to 156.8%.[Data cleaning](cleaning.PNG)

### 4. Exploratory Data Analysis (EDA)
EDA involved preparing data with province and year assignments ( 2013–2018) and generating visualizations:
- A scatter plot clustered districts by GAR and NAR, revealing patterns such as cluster 2 with higher disparity.
- Summary statistics highlighted mean NAR at 89.75% and a gender parity index near 1.02.[cluster](cluster_codes.PNG)
  
### 5. Machine Learning Analysis
Unsupervised learning was applied using K-means clustering on scaled features (GAR and NAR for both sexes, males, and females). 
The model was evaluated with a silhouette score of 0.43, indicating moderate cluster separation.
 This helped identify district groups for targeted interventions.[Model evaluation](step7_model_evaluation.PNG)

### 6. Transition to Power BI
The processed data was exported as `processed_data.csv` using `df.to_csv()`. In Power BI, a dashboard was built with:
- A line chart tracking NAR from 88% to 92% (2013–2018).
- A scatter plot showing cluster 2’s ~15% higher disparity.
- A column chart for Northern province’s 92% NAR.
- A Max Disparity card at 20%.
A `year` slicer added interactivity.

## Tools and Technologies
- **Python**: For data processing and machine learning .
- **Power BI**: For dashboards .
- **GitHub**: For version control.

## Screenshots
[Line Chart](line_chart.png): Shows NAR trend.
[Scatter Chart](scatter_chart.png): Highlights cluster 2 disparity.
[Column Chart](column_chart.png): Notes Northern’s NAR.
[Max Disparity Card](Max_Disparity_Card.png): Displays max disparity.
[Slicer](slicer_province.png): Shows slicer province.

## Future recommendations
 Based on the analysis, here are my insights and recommendations:
- **Targeted Interventions for Cluster 2**: The scatter plot shows cluster 2 districts with a 15% higher attendance disparity, 
suggesting a need for focused programs to address gender or regional gaps, possibly through community engagement or resource allocation.
- **Expand Data Collection**: The current dataset ends at 2018, missing 2019–2023.
 Including recent data could reveal new trends, especially post-COVID impacts, to refine insights.
- **Policy Focus on Northern Province**: With a 92% NAR, Northern province could serve as a model,
 sharing best practices like teacher training or infrastructure investment with lower-performing areas.
- **Predictive Modeling**: The moderate silhouette score (0.43) indicates room for improvement in clustering.
 Integrating predictive models could forecast attendance drops, enabling proactive measures.
- **Mobile-Based Solutions**: Given Rwanda’s mobile penetration, a mobile app for real-time attendance tracking could enhance data accuracy and parental involvement.

