# 🤖 Machine Learning Fundamentals

## 1. Data Preprocessing (The Pipeline)

Garbage In = Garbage Out. We must clean data before training.

1.  **Data Loading:** Reading CSV/Excel files (usually via Pandas).
2.  **Data Cleaning:**
    * Handling **Missing Values** (Impute with Mean/Median or Drop rows).
    * Removing **Outliers** and useless columns (IDs, Names).
3.  **Encoding:** Converting text to numbers.
    * **Label Encoding:** For ordinal data (Low=0, Med=1, High=2).
    * **One-Hot Encoding:** For nominal data (Red=[1,0], Blue=[0,1]).
4.  **Data Balancing:** Fixing skewed classes (e.g., 99% 'No', 1% 'Yes').
    * **SMOTE:** Synthetic Minority Over-sampling Technique.
5.  **Scaling (Normalization):**
    * **StandardScaler:** Transforms data to mean=0, std=1.
    * **MinMaxScaler:** Transforms data to range [0, 1].
    * *Crucial for:* Neural Networks, KNN, SVM.
    * *Not needed for:* Decision Trees, Random Forests.

---
