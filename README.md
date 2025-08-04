# A Hybrid Approach to Fraud Detection: Combining Anomaly Detection and Ensemble Learning

This project presents a hybrid fraud detection framework that combines anomaly detection with ensemble learning models (Random Forest and Gradient Boosting) to improve the accuracy and interpretability of financial fraud classification.

## 🔍 Problem Statement

Fraudulent financial transactions often exhibit rare, unpredictable behavior, making them difficult to detect with traditional models. This project integrates anomaly detection to flag abnormal behavior and ensemble learning to improve precision and reduce false positives.

## 📁 Dataset

- **Source:** [KDD Cup 1999 Data](http://kdd.ics.uci.edu/databases/kddcup99/kddcup99.html)
- **Size:** 4.9 million connection records
- **Attributes:** Protocol type, service, flag, duration, etc.
- **Target:** Classification of each record as legitimate or fraudulent.

## 🛠️ Methodology

1. **Preprocessing:**
   - Handled missing values with median/mode imputation
   - One-hot encoding for categorical features
   - Normalization for numerical features
   - Removed redundant or low-impact features

2. **Model Architecture:**
   - **Isolation Forest** for anomaly detection (adds anomaly scores as a feature)
   - **Random Forest Classifier**
   - **Gradient Boosting Classifier**
   - Combined predictions from both ensemble models

3. **Interpretability:**
   - **LIME (Local Interpretable Model-agnostic Explanations)** is used to visualize which features most influenced the classification of fraudulent activity.

## 📊 Visualization

LIME was used to explain individual predictions by identifying which features (like transaction duration, protocol type, etc.) contributed to a fraud classification.

![LIME Explanation](images/lime_explanation.png)

## 📈 Performance

| Model            | Accuracy |
|------------------|----------|
| Random Forest    | 99.97%   |
| Gradient Boosting| 99.78%   |

- Evaluated with Precision, Recall, F1-Score due to class imbalance
- AUC-ROC used to assess discriminatory performance
- LIME used for local model interpretability

## 📦 Files Included

- `fraud_detection_hybrid_model.ipynb` – Full code for preprocessing, modeling, evaluation
- `images/lime_explanation.png` – LIME visual output
- `README.md` – Project overview

## 📌 Key Takeaways

- The hybrid model significantly improved fraud detection accuracy
- Ensemble models enhanced robustness against noisy data
- LIME provided human-readable explanations, improving model transparency for compliance and auditing

---
