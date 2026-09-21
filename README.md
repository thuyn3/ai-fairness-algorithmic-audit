# ⚖️ AI Fairness & Algorithmic Accountability Audit

**Author:** Thu Thao Huynh

**Tools:** 
- Python
- pandas
- NumPy
- scikit-learn
- SHAP
- Matplotlib
- Seaborn
- 
---

## 🔍 Overview
How can machine learning models used in hiring and employment introduce or reproduce demographic disparities? This project audits the fairness and accountability of a machine learning classification model using the **UCI Adult Income dataset**. The model predicts whether an individual's income exceeds $50K based on demographic and socioeconomic characteristics. The project evaluates model performance across demographic groups, measures fairness using multiple fairness criteria and applies SHAP to improve model explainability.

**Core questions**

- How accurately does the model predict income above $50K?
- Does model performance differ across demographic groups?
- Does the model satisfy different fairness criteria?
- Which features have the greatest influence on model predictions?
- What responsible AI practices should be considered before deployment?

## 🗂 Project & Structure
```
├── AI_Fairness_Algorithmic_Audit_Code.ipynb                       # main analysis and model development
├── requirements.txt                                               # Python dependencies
├── Thu Thao Huynh_AI Fairness Algorithmic Audit Report.pdf        # report paper
└── README.md                                                      # project documentation
```

---

## 🛠 Methodology
1. **Data Preprocessing**
- Used the UCI Adult Income dataset to predict whether income exceeds $50K.
- Removed missing observations.
- Applied one-hot encoding to categorical variables.
- Split the data into training and testing sets using an 80/20 stratified split.
2. **Machine Learning Model**
A Random Forest classifier was developed for binary income classification.

Model evaluation included:

- Accuracy
- Precision
- Recall
- F1-score
- AUC-ROC

The model achieved approximately 85% accuracy and an AUC-ROC of 0.91.
3. **Dashboard Design (Tableau)**
   - **Shot Zone Analysis**: zone frequency for a selected **Team** and **Player**, side-by-side with **League** for the same season.
   - **FG Analysis**: KPI tiles (Team & Player) and horizontal bars of **FG% / eFG%** by zone; filters for **Season/Team/Player**.

4. **Validation (SQL → Tableau)**
   - Cross-check dashboard numbers against SQL rollups (e.g., league zone shares, team PPS/eFG by zone).
   - Refresh/export CSVs when data update; republish the workbook.

---

## 🔁 Reproducibility

**A) Use the curated CSVs (fastest)**
1. Open the Tableau workbook `Khoi Van - Tableau NBA Analysis Project.twbx`.
2. Ensure the data connections point to the CSVs in `data/`.
3. Interact with filters (Season, Team, Player) and view the two dashboards.

**B) Rebuild from raw source (end-to-end)**
1. Download seasons from **DomSamangy/NBA_Shots_04_25**: <https://github.com/DomSamangy/NBA_Shots_04_25>.  
2. Import the raw CSVs into SQL Server (one table or per-season tables).  
3. Run `SQLAnalysis.sql` to create the views/rollups.  
4. Export the aggregated views to CSV → place in `data/`.  
5. Open the `.twbx` and refresh data sources.

---

## 📈 Result

**General dashboard guidelines**
- Global filters: **Season**, **Team**, **Player**.  
- **Shot Zone Analysis** page: zone frequency breakdown for **Team / League / Player** (same season).  
- **FG Analysis** page: KPI tiles (Team FG%, Rim Rate, eFG%, PPS; Player FG%, PPS, Rim Rate, eFG%) and per-zone bars.

**Screenshots**

**FG Analysis**  
![FG Analysis](FG%20Analysis.png)

**Shot Zone Analysis**  
![Shot Zone Analysis](Shot%20Frequency%20Analysis.png)

---

## 📚 References
- **Raw data (shots, 2003–04 → 2024–25):** DomSamangy. _NBA Shots 04–25_. GitHub repository.  
  <https://github.com/DomSamangy/NBA_Shots_04_25>  
- Transformations and summaries (SQL views) in `SQLAnalysis.sql`; exported CSVs in `data/`.  
- Visualization: **Tableau Public** packaged workbook (`.twbx`).

---

## 📬 Contact
For inquiries, feedback, or collaboration, please contact:
- Khoi Van: van_k1@denison.edu
