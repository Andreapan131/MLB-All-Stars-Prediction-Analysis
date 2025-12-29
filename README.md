# MLB All-Stars Prediction Analysis

## 📌 Project Purpose
This project aims to predict the **likelihood of MLB players being selected as All-Stars** using historical performance data. By applying **supervised ML models** to a highly imbalanced classification problem, the analysis focuses on identifying players with strong All-Star potential early. The results are designed to support **team decision-making** in areas such as **roster planning, salary forecasting, and marketing strategy**.

## 📊 Dataset Description
- Source: Public MLB batting statistics dataset (2021–2024 seasons)

- Size: 4,502 observations, 36 performance-related variables

**Key features:**
- Offensive metrics (e.g., BA, OBP, SLG, OPS, HR, RBI)
- Contextual information (team, league, season) --> Removed

- **Target variable: All-Star selection (AS = 1/0)**; highly imbalanced (~10% All-Stars)

## 🏷 Methodology
### 1️⃣ Data Preparation & Preprocessing
- Selected and Standardized the features
- Transformed categorical data to numeric data
- Split the dataset into training (70%) and test (30%) sets

### 2️⃣ Modeling approach
- **Model selection**
  - **Logistic Regression**: Estimated the probability of All-Star selection
  - **Decision Tree**: Identified key factors with the highest predictive power
  - **Random Forest**: Improved robustness through ensemble learning
  - **Naive Bayes**: 
  
- **Imbalance handling**
  - Tuned classification thresholds
  - Adjusted class weights
  - Applied SMOTE to oversample target class

- **Evaluation strategy**
  - Recall, Precision, and optimized **F-β score (β = 1.24)** to **minimize false negatives**
  - Used GridSearchCV with stratified cross-validation to ensure fair comparison
  - Accuracy is inappropriate to severe class imbalance
 
### 3️⃣ Data Visualization
- **ROC Curves** – Compared model discrimination across classifiers
- **F1 & Recall vs. Threshold Plots** – Demonstrated how threshold tuning improves F1 & recall
- **All-Star Probability Rankings** – Visualized player-level All-Star probabilities

## 📌 Performance Summary
Model selected based on business objective:
- Best-performing model: **Logistic Regression with SMOTE + threshold tuning**
- Final model performance (All-Star class):

  | Metric | Value |
  |--------------|-------------|
  | F-β score | 0.65 |
  | Recall | 0.81 |
  | Precision | 0.52 |

## 🔍 Key Findings & Insights
- **Performance metrics must reflect real-world decision costs**, as missing a true All-Star candidate is more costly identifying additional players
- Accuracy is misleading for predicting imbalanced class, because it's easy to predict non All-Star
- Handling class imbalance can significantly improve model performance
- Simpler models can outperform more complex approaches

## 🚀 Business Implications
- **Roster and salary planning**: Spot future All-Stars early and plan payroll ahead
- **Marketing and fan engagement**: Promote high-probability All-Star candidates sooner
- **Decision-making**: Use probabilities to make proactive, not reactive, decisions
