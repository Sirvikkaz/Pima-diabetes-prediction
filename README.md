This repository contains a **single Jupyter notebook** for predicting diabetes risk using the Pima Indians Diabetes Database. The project implements and compares various machine learning algorithms (Logistic Regression, Random Forest, XGBoost) to identify the most effective approach for diabetes classification.
            
## 📦 Project Structure
```

DIABETES PREDICTION/
├── Data/
│   └── diabetes.csv
├── main.ipynb                  # Single notebook with EDA, preprocessing, modeling, and evaluation
│   ├── Data loading / EDA
│   ├── Preprocessing (zero-replacement, scaling, SMOTE)
│   ├── Feature engineering
│   ├── Model training & hyperparameter tuning
│   ├── Evaluation (accuracy, precision, recall, F1, ROC/AUC)
│   └── Feature importances (barh plot)
├── README.md                 
└── requirements.txt
```

# 🩺 Pima Diabetes Prediction

*Early diabetes detection through machine learning - helping bridge healthcare gaps in underserved communities*

## 📋 Project Overview

This project develops machine learning models to predict diabetes risk using clinical measurements from the Pima Indians Diabetes dataset. By leveraging readily available health indicators, we aim to create an accessible screening tool that could support early diabetes detection, particularly in resource-limited settings where traditional screening might be challenging.

**Why this matters:** Diabetes affects millions worldwide, yet early detection can significantly improve outcomes and quality of life. This predictive model could serve as a preliminary screening tool to identify high-risk individuals who would benefit from further medical evaluation.

## 📊 Dataset

**Source:** [Pima Indians Diabetes Database](https://www.kaggle.com/datasets/uciml/pima-indians-diabetes-database)  
**Origin:** National Institute of Diabetes and Digestive and Kidney Diseases  
**Population:** Female patients of Pima Indian heritage, aged 21+  
**Size:** 768 records with 8 clinical features

### Features:
- **Pregnancies:** Number of pregnancies
- **Glucose:** Plasma glucose concentration (2-hour oral glucose tolerance test)
- **BloodPressure:** Diastolic blood pressure (mm Hg)
- **SkinThickness:** Triceps skin fold thickness (mm)
- **Insulin:** 2-hour serum insulin (mu U/ml)
- **BMI:** Body mass index (weight in kg/(height in m)²)
- **DiabetesPedigreeFunction:** Diabetes pedigree function (genetic predisposition)
- **Age:** Age in years

## 🔬 Methodology

### Data Preprocessing
- **Missing Value Treatment:** Replaced zero values in clinical measurements with mean values (affecting Glucose, BloodPressure, SkinThickness, Insulin, BMI, DiabetesPedigreeFunction, Age)
- **Feature Scaling:** Applied StandardScaler to normalize feature ranges
- **Feature Engineering:** Created additional relevant features to improve model performance
- **Class Imbalance:** Used SMOTE (Synthetic Minority Oversampling Technique)
  - Before SMOTE: {Non-diabetic: 381, Diabetic: 194}
  - After SMOTE: {Non-diabetic: 381, Diabetic: 381}

### Models Evaluated
1. **Logistic Regression** - Baseline linear model
2. **Random Forest** - Ensemble method with feature importance
3. **XGBoost** - Gradient boosting for complex patterns

## 📈 Results

| Model | Accuracy | Precision | Recall | F1-Score | AUC |
|-------|----------|-----------|---------|----------|-----|
| **Logistic Regression** | **79.9%** | **64.6%** | **87.5%** | **74.3%** | **0.89** |
| Random Forest | 75.7% | 60.0% | 81.2% | 69.0% | 0.86 |
| XGBoost | 77.1% | 61.2% | 85.4% | 71.3% | 0.83 |

### 🎯 Key Insights
**Top Predictive Features:** Glucose, Age, BMI, Insulin, Pregnancies
*(Order varies slightly across models)*

**Best Performing Model:** Logistic Regression achieved the highest overall performance with excellent recall (87.5%) - crucial for medical screening where missing positive cases has serious consequences.

## 💡 Discussion & Conclusions

### Clinical Significance
The strong performance of our models, particularly Logistic Regression with 89% AUC, demonstrates the potential for machine learning in diabetes risk assessment. The high recall rate (87.5%) is especially valuable in a medical context, as it minimizes false negatives - ensuring fewer diabetic cases go undetected.

### Feature Importance Findings
The consistent ranking of **Glucose** as the top predictor aligns with medical knowledge, as elevated glucose is a direct indicator of diabetes. The significance of **Age**, **BMI**, and **Insulin** also reflects established risk factors, validating our model's clinical relevance.

### Real-World Applications
- **Primary Care Screening:** Support healthcare providers in identifying high-risk patients
- **Resource Allocation:** Help prioritize patients for further diagnostic testing
- **Public Health:** Enable large-scale diabetes risk assessment in communities
- **Telemedicine:** Integrate into remote health monitoring systems

### Limitations & Future Work
- **Population Specificity:** Model trained on Pima Indian women; generalizability to other populations needs validation
- **Feature Enhancement:** Additional clinical markers (HbA1c, family history details) could improve accuracy
- **Temporal Validation:** Longitudinal studies needed to assess prediction stability over time
- **Integration Testing:** Real-world clinical workflow integration requires further evaluation

### Ethical Considerations
While this tool shows promise for diabetes screening, it should complement, not replace, professional medical judgment. Healthcare providers should use these predictions as one factor in comprehensive patient assessment.

## 🚀 Getting Started

### Prerequisites

### Installation
```bash
git clone https://github.com/Sirvikkaz/Pima-diabetes-prediction.git
cd DIABETES PREDICTION
pip install -r requirements.txt
```
### Launching
```bash
jupyter main.ipynb
```
## 🤝 Contributing
Contributions are welcome! Whether you're interested in improving model performance, adding new features, or enhancing documentation, please feel free to submit pull requests or open issues.


---
*"Every person deserves access to early health screening. This project is a small step toward making diabetes prediction more accessible worldwide."*