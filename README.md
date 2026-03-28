# Capstone Project: Predicting 10-Year Heart Disease Risk

## Project Summary

This project explores whether basic health, lifestyle, and clinical information can be used to predict a person's risk of developing coronary heart disease (CHD) within the next 10 years.

The goal is not to replace a doctor. Instead, the goal is to show how data can help identify people who may need earlier attention, additional screening, or stronger prevention strategies.

## Why This Project Matters

Heart disease remains one of the leading causes of serious illness and death. Earlier identification of high-risk patients can support prevention through lifestyle changes, medication, monitoring, and follow-up care.

This project was also personally meaningful to me. After experiencing a Non-ST Elevation Myocardial Infarction (NSTEMI), I became much more aware of how important early risk detection can be. That experience motivated the focus of this capstone.

## Problem Statement

Can demographic, lifestyle, and clinical health data be used to predict whether a person is likely to develop coronary heart disease within 10 years?

## Findings

The main finding is that the model can identify useful patterns related to heart disease risk, but it is not accurate enough to be used alone for medical decision-making.

Among the models tested, **Logistic Regression** gave the best overall balance for this project because it was better at identifying higher-risk patients than several more complex models.

Important takeaway:

- A model with high accuracy is not always the most useful model in healthcare.
- Some models looked strong on overall accuracy but missed too many actual CHD cases.
- For this project, **recall** mattered more because missing a high-risk patient is more serious than flagging someone for further review.

## Key Results

Best base model:

- **Logistic Regression**
- Cross-validated ROC-AUC: about **0.73**
- Cross-validated Recall: about **0.69**

After GridSearchCV tuning:

- **Logistic Regression** remained the best-performing model overall
- Tuned cross-validated ROC-AUC: about **0.73**
- Tuned cross-validated Recall: about **0.68**

This means the tuned model was able to separate lower-risk and higher-risk patients better than the other models tested, while still catching a meaningful share of true CHD cases.

## Most Important Risk Factors Found

The analysis consistently showed that the following features were among the most influential:

- Age
- Systolic blood pressure
- Smoking-related behavior
- Hypertension history
- Diabetes

These findings align with well-known cardiovascular risk factors and support the credibility of the analysis.

## Technical Deliverables

This capstone includes:

- A Jupyter Notebook collection documenting the technical workflow:
  [Framingham_CHD_Prediction.ipynb](Framingham_CHD_Prediction.ipynb)
- A nontechnical report in this README summarizing the business/healthcare problem, results, findings, and next steps

## What the Notebook Covers

The notebook walks through the full technical analysis:

1. Data loading and exploration
2. Data cleaning and preprocessing
3. Feature engineering
4. Model training and evaluation
5. Cross-validation
6. Model improvement using GridSearchCV
7. Threshold tuning for medical recall
8. Permutation-based feature importance

## Dataset

This project uses the **Framingham Heart Study dataset** (Kaggle version), which contains **4,240 patient records**.

The data includes:

- Demographic information such as age, sex, and education
- Lifestyle information such as smoking status and cigarettes per day
- Medical history such as hypertension, diabetes, stroke history, and blood pressure medication
- Clinical measurements such as cholesterol, blood pressure, BMI, heart rate, and glucose

Target variable:

- `TenYearCHD`: whether the patient developed coronary heart disease within 10 years

## Methods Used

To keep the modeling process consistent and fair across models, the notebook uses a shared preprocessing pipeline and evaluates multiple machine learning approaches.

Models tested:

- Logistic Regression
- K-Nearest Neighbors
- Decision Tree
- Random Forest
- Gradient Boosting
- Support Vector Machine (RBF Kernel)
- Neural Network

Evaluation metrics:

- Accuracy
- Precision
- Recall
- F1 Score
- ROC-AUC

Because the dataset is imbalanced, recall and ROC-AUC were treated as especially important.

## Tools and Libraries

- Python
- pandas
- numpy
- matplotlib
- seaborn
- scikit-learn

## Important Limitations

This project has several important limitations:

- The dataset is relatively small
- The positive CHD class is imbalanced
- The data comes from one historical cohort, so generalizability may be limited
- A model with ROC-AUC around 0.70 can support screening insights, but it should not be used as a standalone clinical diagnosis tool

## Recommended Next Steps

If this project were extended, the next improvements I would recommend are:

1. Collect or use a larger and more recent cardiovascular dataset
2. Explore class imbalance strategies more deeply, such as resampling or calibrated threshold selection
3. Add model calibration analysis so predicted risks better reflect real-world probabilities
4. Compare against established clinical risk scoring tools
5. Validate the model on an external dataset before considering any real-world use

## Final Conclusion

This project shows that machine learning can help surface meaningful patterns related to long-term heart disease risk. In this dataset, Logistic Regression performed best because it balanced interpretability with stronger recall than many of the more complex models.

The broader lesson is that in healthcare problems, the "best" model is not simply the one with the highest accuracy. The more useful model is the one that better supports the real goal, which in this case is reducing missed high-risk patients.
