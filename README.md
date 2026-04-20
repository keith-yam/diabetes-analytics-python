# Diabetes Risk Prediction & Health Indicator Analysis

## 📌 Project Overview
This project investigates the factors influencing diabetes in the United States using data from the [**2015 Behavioral Risk Factor Surveillance System (BRFSS)**](https://www.kaggle.com/datasets/alexteboul/diabetes-health-indicators-dataset) collected by the CDC. By analyzing survey responses from over 400,000 individuals, this project aims to build predictive models that can identify diabetes risk based on lifestyle and health indicators.

### 🔍 Key Research Questions
1. **Predictive Accuracy:** Can survey-based health data accurately predict if an individual has diabetes?
2. **Risk Identification:** Which specific health factors (e.g., BMI, physical activity, blood pressure) are the strongest predictors?
3. **Model Optimization:** Can we maintain high accuracy using only a subset of the most critical risk factors?
4. **Efficiency:** Can a "short-form" survey be developed for rapid clinical screening?

## 📊 Dataset Details
The analysis is based on the [2015 BRFSS dataset](https://www.kaggle.com/datasets/cdc/behavioral-risk-factor-surveillance-system).
* **Initial Size:** 441,455 records and 330 features.
* **Processed Data:** 253,680 records and 21 key health indicators.
* **Target Variable:** `Diabetes_012` (0 = No Diabetes, 1 = Pre-diabetes, 2 = Diabetes).
* **Features Include:** High Blood Pressure, High Cholesterol, BMI, Smoking status, Stroke history, Heart Disease, Physical Activity, Fruit/Veggie consumption, Heavy Alcohol use, General Health rating, and Demographic data (Age, Education, Income).

## 🛠️ Tech Stack
- **Language:** Python
- **Libraries:** - `Pandas` & `NumPy` (Data Manipulation)
  - `Scikit-learn` (Machine Learning Pipeline)
  - `Matplotlib` & `Seaborn` (Data Visualization)
  - `Imbalanced-learn` (SMOTE/ADASYN for class balancing)
  - `SHAP` (Interpretability)
 
## 🚀 Workflow

### 1. Data Cleaning & EDA
- Handled missing values and duplicates.
- Analyzed feature correlations and data distributions.
- Applied scaling to continuous variables like BMI.

### 2. Addressing Class Imbalance
Since the majority of participants do not have diabetes, the dataset is highly imbalanced. This project utilizes oversampling techniques (**SMOTE**) to ensure the model learns the characteristics of the minority "Diabetes" class effectively.

### 3. Model Development
Multiple classification algorithms were implemented and compared:
- **Logistic Regression**
- **Random Forest**
- **Gradient Boosting** (Top Performer)
- **K-Nearest Neighbors (KNN)**
- **Support Vector Machines (SVM)**

### 4. Hyperparameter Tuning
Used **GridSearchCV** and **RandomizedSearchCV** to optimize model parameters, focusing on maximizing the **F1-Score** and **Recall** to ensure diabetes cases aren't missed.

## 📈 Results & Findings
- **High Performance:** The Gradient Boosting model achieved the best balance between precision and recall.
- **Top Predictors:** BMI, Age, and General Health were identified as the most significant indicators of diabetes risk.
- **Feasibility:** The analysis confirms that a reduced set of features can predict diabetes with high reliability, supporting the creation of streamlined health screenings.

## 📂 Repository Structure
```text
├── diabetes.ipynb          # Full Jupyter Notebook with analysis and code
├── data/                   # (Optional) Folder for the raw/processed datasets
├── requirements.txt        # Python dependencies
└── README.md               # Project documentation
