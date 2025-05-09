# ⚖️ What is Skewed Data and How to Mitigate Its Effect?

## 📉 What is Skewed Data?

**Skewed data** (or **imbalanced data**) occurs when one class or category appears **much more frequently** than others in your dataset.

### 🔄 Example:
In a fraud detection dataset:
- 98% of transactions are **legit**
- 2% are **fraudulent**

This is **skewed** toward legitimate transactions. A model could predict "not fraud" for everything and still be 98% accurate — but it wouldn’t actually catch fraud.

---

## ⚠️ Why It's a Problem

- The model often **ignores the minority class**.
- It leads to **poor performance** on the important but rare class.
- **Accuracy** becomes misleading:
  - 98% accuracy might mean **0% fraud detection**.

---

## 🛠️ How to Mitigate Skewed Data

### 1. Resampling Techniques
- **Undersampling**: Reduce the number of majority class samples.
- **Oversampling**: Duplicate or generate synthetic samples for the minority class.
  - 🔧 **SMOTE** (Synthetic Minority Over-sampling Technique) is a popular method.

### 2. Use Better Evaluation Metrics
Accuracy isn't reliable. Use:
- **Precision**
- **Recall**
- **F1-score**
- **ROC-AUC**

### 3. Class Weights
- Assign higher weight to the minority class.
- In libraries like `scikit-learn`, use:  
  `class_weight='balanced'` in many classifiers.

### 4. Anomaly Detection
- If the minority class is **extremely rare**, treat it as an **anomaly detection** problem instead of classification.

### 5. Ensemble Methods
- Use models like:
  - **Random Forest**
  - **XGBoost**
- These can handle imbalance better, especially with class weighting.

---
