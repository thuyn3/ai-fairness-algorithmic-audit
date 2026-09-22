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
---

## 🔍 Overview
How can machine learning models used in hiring and employment introduce or reproduce demographic disparities? This project audits the fairness and accountability of a machine learning classification model using the UCI Adult Income dataset. The model predicts whether an individual's income exceeds $50K based on demographic and socioeconomic characteristics. The project assesses model performance for different demographic groups, measures fairness using multiple fairness criteria and applies SHAP to improve model explainability.

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
3. **Fairness Evaluation**
The model was analyzed for different demographic groups using three fairness criteria:

- Demographic Parity
- Equal Opportunity
- Predictive Parity

The analysis compared differences in prediction rates, recall, and precision between demographic groups.

4. **Explainability**

SHAP (SHapley Additive exPlanations) was applied to identify the features that contributed most strongly to model predictions.

Key features included:

- Marital status
- Age
- Capital gain
- Occupation
- Education level

5. **Responsible AI & Policy Analysis**

The findings were considered in relation to:

- GDPR
- Title VII
- NIST AI Risk Management Framework

The project also proposed recommendations for fairness evaluation, human review, explainability, recourse and documentation ahead of deployment.

---

## 📊 Model Performance

| Metric    | Result |
| --------- | -----: |
| Accuracy  |  ~0.85 |
| AUC-ROC   |  ~0.91 |
| Precision |  ~0.73 |
| Recall    |  ~0.64 |
| F1-score  |  ~0.68 |

---

## ⚖️ Fairness Analysis

The audit identified differences in model outcomes for different demographic groups.

For example:

- Demographic parity: approximately 27.04% for males vs. 7.98% for females
- Recall / Equal Opportunity: approximately 65% for males vs. 52% for females
- Precision / Predictive Parity: approximately 73.7% for males vs. 71.8% for females

These metrics were used to examine different dimensions of fairness rather than relying on a single fairness criterion.

---

## 🔍 Explainability

SHAP was used to analyze global feature importance and individual model predictions.

The analysis examined whether certain features could act as potential proxies for demographic characteristics and considered how model explanations could support transparency and accountability.

---

## 📋 Responsible AI Recommendations

Based on the audit, the project proposed a pre-deployment framework including:

- Calculate fairness metrics across relevant demographic groups
- Monitor gaps in recall and other performance measures
- Identify potential proxy variables
- Document fairness and explainability trade-offs
- Include human review for high-impact decisions
- Provide plain English explanations of model outputs
- Provide actionable recourse where appropriate
- Evaluate data balance before deployment

--- 

## 🔁 Reproducibility

**Quick view**

Open `AI_Fairness_Algorithmic_Audit_Code.ipynb` in GitHub to review the analysis and code.

**Run locally**
1. Clone the repository
2. Install the required Python packages:

```bash
pip install -r requirements.txt
```
3. Open the notebook:

```bash
jupyter notebook AI_Fairness_Algorithmic_Audit.ipynb
```
The notebook retrieves the UCI Adult dataset programmatically and performs the preprocessing, model development, fairness analysis and SHAP explainability steps.

---

## 📈 Key Findings

- The Random Forest model achieved approximately 85% accuracy and 0.91 AUC-ROC on the classification task.
- Model performance varied for different demographic groups, particularly in recall.
- The fairness analysis identified differences in demographic parity and equal opportunity for different gender groups.
- SHAP analysis identified several influential features, including marital status, age, capital gain, occupation and education level.
- The project highlights the importance of evaluating fairness, explainability, transparency and human oversight when applying machine learning to high impact domains such as hiring and employment.

*(See the report and notebook for detailed analysis, figures, and supporting results.)*

---

## 📚 References

1.	Becker, B. & Kohavi, R. (1996). Adult [Dataset]. UCI Machine Learning Repository. 
https://doi.org/10.24432/C5XW20. 
 
2.	European Union. (2016). General Data Protection Regulation (GDPR), https://eur-lex.europa.eu/eli/reg/2016/679/oj#enc_1 
 
3.	National Institute of Standards and Technology. (2023). Artificial Intelligence Risk Management Framework (AI RMF 1.0) (NIST AI 100-1). https://nvlpubs.nist.gov/nistpubs/ai/NIST.AI.100-1.pdf 
 
4.	U.S. Equal Employment Opportunity Commission. (n.d.). Title VII of the Civil Rights Act of 1964. 
https://www.eeoc.gov/statutes/title-vii-civil-rights-act-1964

*(See the References section in the PDF report for the complete list of sources.)*
 

