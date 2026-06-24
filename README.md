# PR2_Data_Cleanser

Advanced Healthcare Data Cleaning & Preprocessing Pipeline

📖 Executive Summary

This project presents a robust data preprocessing pipeline designed to transform raw healthcare records into a high-fidelity dataset suitable for predictive modeling. By addressing data quality issues—specifically missing values and extreme outliers—this pipeline ensures the integrity of the disease_risk prediction model. The implementation utilizes pandas, scikit-learn, and scipy to maintain statistical consistency across 1,000 patient records.

📊 Dataset Overview

The dataset utilized in this analysis consists of 1,000 patient records containing the following key health metrics:

Demographics: patient_id, age, gender, region.

Clinical Metrics: bmi, blood_pressure, cholesterol, glucose.

Target Variable: disease_risk (binary classification).

The dataset was characterized by non-random missingness across various features and significant outliers in physiological indicators, requiring a multi-faceted cleaning approach.

🛠 Technical Methodology

1. Missing Value Imputation (Part A)

   
To mitigate the impact of missing clinical data without introducing bias, we implemented a hierarchical imputation strategy:

Simple Imputation: Used for baseline cleanup of categorical variables.

Missing Indicator & Random Sampling: Preserved data variance for age and bmi by flagging missing instances before stochastic filling.

Multivariate Imputation (KNN & MICE): Employed KNNImputer (k=5) and IterativeImputer to capture feature correlations, ensuring that imputed clinical values align with physiological patterns found in similar patient profiles.

2. Outlier Detection & Treatment (Part B)

   
Outlier handling was prioritized to maintain data volume while limiting the influence of extreme physiological measurement errors:

Statistical Filtering: Utilized Z-Score and IQR methods to quantify deviations from the norm.

Data Preservation: Implemented Winsorization (capping at the 1st and 99th percentiles) rather than row deletion, successfully preserving the integrity of the 1,000-record set.

Performance Comparison: Validated the effectiveness of the pipeline by contrasting dataset statistics and shape before and after treatment.

<img width="674" height="558" alt="image" src="https://github.com/user-attachments/assets/767266fa-a432-4808-ab2c-5b006e0f896f" />

<img width="683" height="554" alt="image" src="https://github.com/user-attachments/assets/49d460f2-c4c0-4e19-aa2e-508df65c0a64" />

📝 Part C: Final Dataset & Comparative Summary

Final Dataset Preparation
The final dataset is a consolidated, clean version of the original raw data. By shifting from aggressive removal methods (Z-Score/IQR) to capping/winsorization methods, we have ensured:

Zero Data Loss: All 1,000 original patient records were preserved.

Reduced Variance: Extreme noise that could cause overfitting in predictive models was successfully capped.

Final Conclusion
The cleaning process successfully transformed an "unclean" dataset into a model-ready format. The combination of MICE imputation for missing values and Winsorization for outliers provided the best balance between preserving data integrity and removing statistical noise. The resulting dataset is now optimized for supervised machine learning tasks, specifically predicting disease_risk.

Consistency: All missing values were imputed using context-aware algorithms (MICE/KNN).


