# Predictive Analytics for Ovarian Health Risk Factors

## 📌 Project Overview
This repository hosts an advanced end-to-end data science and business intelligence project focused on stratifying ovarian health risk profiles. By combining **Python (Machine Learning)** for the backend predictive pipeline and **Power BI (Custom UI via JSON)** for the interactive frontend dashboard, the project translates complex clinical data into actionable diagnostic insights.

*Note: This project is built strictly for data science portfolio and educational purposes. It utilizes de-identified, open-source research data and contains no Personally Identifiable Information (PII).*

---

## 🏗️ End-to-End Workflow & Architecture

```text
[Raw Clinical Data] ➡️ [Python: Wrangling & Random Forest] ➡️ [Processed Data + Risk Predictions] ➡️ [Power BI Frontend + Custom JSON Theme]
```

### 1. Backend Machine Learning Pipeline (Python)
Instead of relying on arbitrary rules, a predictive model was engineered using Python to classify patient profiles into risk tiers.

*   **Algorithm Selected:** **Random Forest Classifier**
*   **Target Feature:** `Risk_Level` (Multi-class: *Low Risk*, *Medium Risk*, *High Risk*)
*   **Why Random Forest?**
    *   **Handles Non-Linear Medical Relationships:** Clinical biomarkers (like CA-125) and patient age do not scale linearly with risk. Random Forest uses an ensemble of decision trees to capture complex feature interactions.
    *   **Resistance to Overfitting:** By averaging multiple randomized decision trees, the model generalizes exceptionally well to unseen patient profiles.
    *   **Robustness to Outliers & Missing Values:** Medical datasets frequently contain missing symptom logs or extreme biomarker outliers. Random Forest natively handles these variations without destabilizing.
    *   **Feature Importance Evaluation:** The algorithm outputs exact statistical weights for each clinical variable, providing transparent interpretability (Explainable AI) crucial for healthcare models.

### 2. Core Python Implementations Done
*   **Data Preprocessing:** Managed missing clinical values using median imputation and encoded categorical symptoms using One-Hot Encoding via `scikit-learn`.
*   **Feature Scaling:** Standardized volatile continuous biomarkers using `StandardScaler` to ensure uniform distance weightings.
*   **Model Training & Cross-Validation: ** Split the dataset (80/20 train/test) and utilized Stratified K-Fold cross-validation to maintain balanced class distributions during training.
*   **Inference Export:** Generated prediction probabilities and hard labels, exporting the structured dataset into a optimized `.csv` pipeline for Power BI ingestion.

### 3. UI/UX Optimization & Frontend Design (JSON)
*   To bypass standard generic templates, a **custom JSON theme file** was engineered to dictate the Power BI interface.
*   **Visual Architecture:** Configured a dark-mode, clinical-grade layout emphasizing strict visual hierarchy, custom canvas grid margins, explicit font scaling (`Segoe UI Semibold`), and accessible color palettes optimized for diagnostic readability.

### 4. Interactive Analytical Layer (Power BI)
*   **Risk Breakdown Matrices:** Dynamically filters clinical profiles by predicted risk thresholds.
*   **AI Integration:** Embedded Power BI's **Key Influencers** visual to dynamically validate the Random Forest model's feature importances, showing end-users exactly which biomarker thresholds trigger high-risk classifications in real-time.

---

## 🛠️ Tech Stack & Libraries Used
*   **Languages:** Python, DAX, JSON
*   **Data Wrangling:** `pandas`, `numpy`
*   **Machine Learning:** `scikit-learn`
*   **Visualization Platform:** Power BI Desktop

---

## 📁 Repository Structure
```text
├── dataset/
│   ├── Supplementary data 4.xlsx              # Raw clinical research records(Training)
	  Supplementary data 5.xlsx		# Test Clinical records(Testing)
│   └── Ovarian_Cancer_PowerBI_Input.csv    # Final processed data with ML prediction outputs to Power BI
├── scripts/
│   └── JupitorNotebookCode.py               # Python script (Preprocessing, Training, Inference) ML
├── theme/
│   └── PVC1.json.json        # Custom JSON design theme for Power BI UI
├── Predict Ovarian Cancer.pbix # Core Power BI dashboard file
└── README.md                             # Project documentation (This file)
```
## 🎯 Core Project Goal & Predictions

The core goal of the Python backend is to shift away from manual threshold calculations and instead utilize **supervised machine learning** to analyze complex interactions between biomarker metrics and demographic features.

### What the Code Predicts:
1.  **Risk Class Assignment (`Predicted_Risk_Level`):** Classifies patient files into exact diagnostic buckets (**Low Risk**, **Medium Risk**, **High Risk**).
2.  **Prediction Certainty (`Confidence_Score`):** Outputs a percentage value calculating how confident the Random Forest model is in its decision (ideal for creating data-driven sorting gauges inside Power BI).

### Key Algorithmic Milestones Met:
-   **Automated Pipeline:** Combines missing numerical imputation, feature encoding, scaling, and classification steps in a single end-to-end framework.
-   **Statistical Validation:** Evaluates model weights directly, mapping continuous variables like **CA-125** and **HE4** to quantify their predictive impact on early patient risk assessment.

---

## 💡 Disclaimer
This dashboard is a data analytics simulation and machine learning portfolio piece. It is **not** a clinical diagnostic tool and should not be used for medical decision-making or self-diagnosis.
