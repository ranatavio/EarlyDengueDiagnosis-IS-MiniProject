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
pip install pandas numpy scikit-learn 
```
---

## Files
adaboost_dengue_model.pkl
scaler.pkl

adaboost_dengue_model.pkl – Trained AdaBoost classifier

scaler.pkl – Feature standardization scaler used during training

Both files are required for prediction.

---

## Usage
Load the Model and Scaler
```
import pickle
with open("adaboost_dengue_model.pkl", "rb") as f:
    model = pickle.load(f)
with open("scaler.pkl", "rb") as f:
    scaler = pickle.load(f)
```
---

## Prepare Input Data
Input data must:
- Contain the same features and order as the training data
- Include only clinical and hematological variables
- Exclude any location-based information
Example:
```
import pandas as pd

X_new = pd.DataFrame([{
    "Platelet": 95000,
    "WBC": 4200,
    "Hematocrit": 38,
    "Hemoglobin": 13.2,
    "RBC": 4.5
}])
```

---

## Make a Prediction
```
X_new_scaled = scaler.transform(X_new)
prediction = model.predict(X_new_scaled)
print("Dengue Positive" if prediction[0] == 1 else "Dengue Negative")
```
---

## Notes
- SMOTE was applied only during training
- Do not re-fit the scaler on new data
- Pickle files should only be loaded from trusted sources
- This model is intended to support early screening and research purposes

---

## Disclaimer

This model is provided for research and educational use only and should not be used as a standalone diagnostic tool without clinical validation.
