# PR2_Data_Cleanser

Project 2: Data Preprocessing & Feature Engineering

Patient Health Records — Missing Value Imputation & Outlier Treatment

Objective

Practice Data Preprocessing and Feature Engineering with a strong emphasis on
handling missing values and outlier detection/removal. The project applies
different imputation strategies and outlier treatment techniques to clean a
healthcare dataset and prepare it for machine learning (predicting heart disease risk).

Problem Statement

Working as a Data Analyst for a healthcare company, the dataset contains patient
health records with missing values and outliers caused by inconsistent reporting
and measurement errors. The task is to clean the dataset using various missing
data imputation methods and outlier handling techniques.

Dataset

A synthetic dataset of 1000 patients containing:


Patient demographic details: Age, Gender, Region
Medical attributes: BMI, Blood Pressure, Cholesterol, Glucose
Target variable: disease_risk (0 = Low Risk, 1 = High Risk)


Missing values and outliers were intentionally introduced into specific columns
to practice different cleaning techniques, as specified in the project brief.

Tasks Covered

Part A — Handling Missing Values


Missing value detection and summary report (% per column)
Simple Imputer (Numerical) — mean/median on BMI
Simple Imputer (Categorical) — most frequent for Region
Most Frequent Imputation — Gender
Missing Indicator + Random Sample Imputation
KNN Imputer (multivariate)
MICE Algorithm (chained equations)


Part B — Handling Outliers


Z-score method — Cholesterol & Glucose
IQR method — BMI
Percentile method — capping at 1st/99th percentile
Winsorization — capping extreme values instead of removing rows
Before vs after comparison of dataset shape and summary statistics


Part C — Final Clean Dataset


Combined the best-performing imputation and outlier treatment methods
into one final, machine-learning-ready dataset
Written report comparing methods and explaining improvements


Video Walkthrough

Watch the video here

Summary of Findings

Most effective imputation strategy: KNN / MICE, since both use relationships
between multiple columns to estimate missing values rather than filling every
gap with a single fixed number.
Best outlier handling method: Percentile capping / Winsorization, since
both preserve all 1000 patient records by capping extreme values instead of
deleting rows.
Outcome: A complete dataset with zero missing values and no extreme
outlier distortion, ready for downstream machine learning tasks such as
predicting disease_risk.


Author

Devanshi

