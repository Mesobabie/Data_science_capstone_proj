
# 🚀 Falcon 9 First Stage Landing Prediction

## 📘 Overview

This capstone project focuses on predicting whether the **Falcon 9 first stage** will successfully land after launch. Successful landings are critical to **SpaceX’s cost-effective** launch model — where a launch costs approximately **$62 million** compared to **$165+ million** by competitors, thanks to first-stage reuse.

Accurate prediction models can support decision-making for cost estimations and potentially help other providers **bid against SpaceX** for commercial launches.

---

## 🔧 Tools & Technologies Used

- Python (Pandas, NumPy, Scikit-learn, Seaborn, Matplotlib)
- Web scraping (requests, BeautifulSoup)
- API data retrieval (SpaceX API)
- Data visualization (Folium)
- Machine Learning (Logistic Regression, SVM, Decision Tree, KNN)
- GridSearchCV for hyperparameter tuning

---

## 📊 Data Collection & Preprocessing

1. **Retrieved SpaceX launch data** via a `GET` request to the SpaceX API.
2. **Parsed JSON responses** and normalized them into Pandas DataFrames.
3. **Scraped additional HTML table data** from Wikipedia using BeautifulSoup.
4. Extracted and cleaned tables, removing noise such as `[e]`, `N/A`, and footnotes.
5. **Structured cleaned data** into dictionaries and converted them into DataFrames.

---

## 📍 Geospatial Analysis

- Used **MousePosition** to record coordinates of:
  - Launch sites
  - Coastline points
  - Nearby infrastructure (cities, highways, railways)
- Calculated distances between launch sites and closest points.
- Visualized connections using **Folium PolyLines**.

---

## 📈 Feature Engineering & Labeling

- Created a classification label `landing_class`:
  - **1**: Successful landing
  - **0**: Failed landing (defined by a set of bad outcomes)
- Used `.value_counts()` to analyze landing outcomes and launch frequencies.

---

## 🧠 Model Training & Evaluation

1. **Data Standardization** using `StandardScaler`
2. **Train-test split** (80% train / 20% test) with `random_state=2`
3. Built and tuned the following models using `GridSearchCV (cv=10)`:
   - Logistic Regression
   - Support Vector Machine (SVM)
   - Decision Tree
   - K-Nearest Neighbors (KNN)
4. **Evaluated each model** on test data using:
   - `score()` method for accuracy
   - Confusion matrix for prediction performance

---

## 🏆 Model Performance

| Model               | Accuracy |  
|--------------------|----------|  
| Logistic Regression| ~92%     |  
| SVM                | ~93%     |  
| **Decision Tree**  | **94%**  |  
| KNN                | ~91%     |

📌 **Decision Tree** emerged as the best-performing model with **94% accuracy**.

---

## 📍 Visualization Examples

- Launch success/failure rates by site
- Distance markers from launch site to coast, cities, highways
- Confusion matrices for all models

---

## 📦 Outcome

This project demonstrates how predictive modeling and spatial analysis can support aerospace operations and competitive business decisions in the commercial space industry.


