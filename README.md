# Capstone Project: Heart Attack Risk Prediction Using Machine Learning

## Project Overview

The objective of this capstone project is to develop a machine learning model that predicts an individual's risk of experiencing coronary heart disease (CHD) within ten years using clinical, demographic, and lifestyle health data.

This project was motivated by the importance of early detection of cardiovascular risk factors. Having recently experienced a Non-ST Elevation Myocardial Infarction (NSTEMI) myself, I developed a deeper understanding of how critical early detection can be. This experience motivated the focus of this project on predictive risk assessment for heart disease.

## Research Question

Can clinical, demographic, and lifestyle health data be used to predict an individual's risk of experiencing coronary heart disease, and which factors most strongly contribute to that risk?

## Dataset

This project uses the **Framingham Heart Study Dataset (Kaggle version)**.  
The dataset contains 4,240 patient records with demographic, lifestyle, medical history, and clinical measurement variables.

### Dataset Features

**Demographic:**
- Age
- Sex
- Education level

**Lifestyle:**
- Smoking status
- Cigarettes per day

**Medical History:**
- Hypertension
- Diabetes
- Stroke history
- Blood pressure medication

**Clinical Measurements:**
- Total cholesterol
- Systolic blood pressure
- Diastolic blood pressure
- BMI
- Heart rate
- Glucose level

**Target Variable:**
- `TenYearCHD` – Binary indicator of coronary heart disease within ten years.

## Data Preprocessing

Data cleaning steps included:
- Removing duplicate records
- Handling missing values using median or mode imputation
- Outlier detection using the Interquartile Range (IQR) method
- Feature engineering including blood pressure indicators and smoking categories

## Machine Learning Models

The following models were evaluated:

- Logistic Regression
- Random Forest
- Gradient Boosting
- Support Vector Machine (SVM)
- Decision Tree
- K-Nearest Neighbors

## Model Evaluation Metrics

Models were evaluated using:
- Accuracy
- Precision
- Recall
- F1 Score
- ROC-AUC

Due to class imbalance in the dataset (~15% positive CHD cases), **recall and ROC-AUC** were considered the most important metrics.

## Results

**Logistic Regression** achieved the best balance between predictive performance and medical usefulness.

**Key performance:**
- ROC-AUC ≈ 0.70
- Recall ≈ 0.59

Although some models achieved higher accuracy, they performed poorly at identifying actual CHD cases. In medical prediction tasks, detecting high-risk patients is more important than maximizing accuracy.

## Feature Importance

The most important predictors identified in the model include:

- Age
- Systolic blood pressure
- Smoking behavior
- Hypertension status
- Diabetes

These findings align with established clinical research on cardiovascular disease risk factors.

## Technologies Used

**Language:** Python

**Libraries:**
- pandas
- numpy
- matplotlib
- seaborn
- scikit-learn

## Conclusion

This project demonstrates that machine learning can assist in identifying individuals at elevated cardiovascular risk using clinical and lifestyle data. Early risk prediction can support preventative healthcare strategies and improve decision-making for clinicians and healthcare systems.