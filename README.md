# 🏥 New York State Hospital Inpatient Discharge – Machine Learning Capstone Project
This project analyzes New York State’s inpatient hospital discharge data to build machine-learning models that support **better healthcare planning**, **resource optimization**, and **patient risk assessment**.

Focuses on three core goals:

1. 🔢 Predict **Length of Stay (LOS)**
2. ⚠️ Classify **patient mortality risk**
3. 🔍 Use **clustering** to uncover patterns in diagnoses and demographics

This enables hospitals to improve care delivery, anticipate high-risk cases, and allocate resources efficiently.


---

## 🎯 Objectives

* 📈 Predict patient **Length of Stay** using supervised ML models
* ❤️ Predict **likelihood of mortality**
* 🧬 Identify **diagnostic patterns** across NY communities
* 🗺️ Help healthcare providers optimize service availability


---

## 🗂️ Dataset

* Source: **NY Dept. of Health (SPARCS De-Identified Discharge Data)**
* Total Rows: **2,101,588**
* Used Subset: **200,000 rows**
* Features: **33 columns**


### 🔧 Data Preprocessing

* ✔ Handled missing values
* ✔ Removed **757** duplicate rows
* ✔ Outlier treatment (Box-Cox)
* ✔ Encoded categorical variables
* ✔ Standardized values
* ✔ Replaced ambiguous entries (e.g., Unknown → Spanish/Hispanic)
* ✔ Applied **PCA** (70% variance retained)
* ✔ Class balancing via **SMOTE**


---

## 🔍 Exploratory Data Analysis

### 📊 Univariate Insights

* Most common diagnosis → **Liveborn**
* Majority patients → **Least likely to die**
* Highest patient volume → **New York City**
* Largest age group → **70+ years**


### 🔗 Bivariate Insights

* Lower mortality → shorter LOS
* Higher charges/costs → longer LOS
* Mortality risk increases with age


### 🧬 Multivariate Insights

* Males (17+) stay longer than females
* Females in Cancer/Children hospitals stay longer on similar prescriptions
* Total charges & LOS are positively correlated


---

## 🤖 Machine Learning Models

### **1️⃣ Regression — Predicting Length of Stay**

* Algorithms tested: **9**
* Best model: **XGBoost**
* **R² Score:** 0.85
* **RMSE:** 3.2
* Methods: GridSearchCV, parameter tuning


---

### **2️⃣ Classification — Predicting Mortality Risk**

* Algorithms tested: **7**
* Applied SMOTE for balancing
* Best Model: **XGBoost**
* **Accuracy:** 75%
* **Precision:** 70%
* **Recall:** 71%


---

### **3️⃣ Clustering — Patient Segmentation**

Techniques used:

* PCA → Selected 9 components
* Elbow Method → Optimal **K = 4**
* Silhouette Scores
* **K-Means** clustering


**Cluster Summaries:**

* **Cluster 0:** Livebirth (Non-Spanish/Hispanic)
* **Cluster 1:** Septicaemia group
* **Cluster 2:** COVID-19 patients
* **Cluster 3:** Livebirth (Spanish/Hispanic)


---

## 🧠 Key Insights

### 🏥 Length of Stay (LOS)

* Children (<18) → shortest stays
* Newborns → consistent 2-day stays
* Emergency admissions → longest LOS
* LOS model explains **84.5%** of variation


### ❤️ Mortality Risk

* Patients 70+ → highest risk
* Patients with **Medicare** → higher mortality
* Emergency admissions → higher mortality
* Classification model predicts **75% of unseen cases correctly**


### 🧪 Clustering

* Clear demographic-diagnosis clusters (Liveborn, Septicemia, COVID)
* Septicemia clusters require enhanced safety & infection control
* NYC & Manhattan hospitals need stronger collaboration
