# EarlyDengueDiagnosis-IS-MiniProject
# Early Dengue Diagnosis Using AdaBoost and Clinical–Hematological Data

## 📌 Overview
This repository contains the implementation of an **AdaBoost-based machine learning model** for the **early diagnosis of dengue infection** using routinely available **clinical symptoms and hematological laboratory data**. The model was developed as part of an academic research study and focuses on **early-stage detection** without relying on meteorological or geographic features.

The approach emphasizes:
- Early detection using CBC-derived features
- Improved generalizability by excluding location-based variables
- Robust handling of class imbalance using SMOTE
- Clinically meaningful evaluation metrics

AdaBoost was selected as the **best-performing model** based on test set accuracy and generalization performance.

---

## 🧪 Dataset
**Structured Clinical and Hematological Dataset for Early Dengue Diagnosis in Bangladesh**

The dataset includes:
- Demographic features (e.g., age, gender)
- Clinical symptoms (e.g., fever, headache, muscle pain)
- Hematological parameters (e.g., platelet count, WBC)
- Binary outcome label (`Outcome`)
  - `1` → Dengue-positive
  - `0` → Dengue-negative

Location-specific columns (e.g., district, city, area) are automatically removed to improve global applicability.

---

## ⚙️ Requirements
- Python **3.8+**

Install dependencies:
```bash
pip install pandas numpy scikit-learn imbalanced-learn xgboost
