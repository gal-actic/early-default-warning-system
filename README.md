# early-default-warning-system
Credit risk modeling project to predict loan defaults using financial and demographic data. Developed and compared Logistic Regression, Random Forest, and XGBoost models, with calibrated risk segmentation (Low → Very High) for business deployment.


# Next-Gen Credit Risk & Early Default Warning System

## 📖 Overview
Banks and fintech companies face the challenge of balancing:
- ✅ Approving loans to safe borrowers (grow revenue).
- 🚨 Avoiding risky borrowers (minimize losses).

This project develops a *machine learning–based Early Default Warning System* to predict loan default probability and segment borrowers into *Low, Medium, and High risk buckets* for smarter lending decisions.

---

## 📂 Dataset
- *Source*: Loan Default Dataset (Kaggle)
- *Size*: ~150K rows (post-cleaning ~30K test set)
- *Features*:
  - Applicant profile → income, credit_score, age, region
  - Loan details → loan_amount, property_value, loan_purpose, term
  - Target → Status (0 = Non-default, 1 = Default)

---

## ⚙ Methodology
1. *Data Cleaning*
   - Imputed missing values (median → numerics, mode → categoricals).
   - One-hot encoded categorical features.
   - Standardized continuous variables.

2. *Modeling*
   - Logistic Regression (baseline, explainable).
   - Random Forest, XGBoost (advanced).
   - Metrics → Accuracy, Precision, Recall, F1-score, ROC-AUC.

3. *Threshold Tuning*
   - Default threshold = 0.5 → Recall = 71%.
   - Adjusted threshold = 0.40 → Recall improved to 80% (better at catching risky borrowers).

4. *Risk Segmentation*
   - *Low Risk (<25%)* → Auto-approve ✅
   - *Medium Risk (25–40%)* → Approve with stricter terms 🟠
   - *High Risk (>40%)* → Manual review / Reject 🚨

---

## 📊 Results
### Logistic Regression
- ROC-AUC: *0.867*
- Recall (Defaults): *0.80* at threshold 0.40
- Precision (Defaults): *0.54*

### Random Forest / XGBoost
- ROC-AUC: *~0.99*
- Excellent predictive power, useful for business adoption.

### Risk Bucket Summary
| Risk Bucket | Customers | Default Rate | Business Action |
|-------------|-----------|--------------|-----------------|
| Low Risk    | 11,203    | 6%           | Auto-approve ✅ |
| Medium Risk | 7,680     | 11%          | Stricter terms 🟠 |
| High Risk   | 10,851    | 54%          | Manual review 🚨 |

---

## 📈 Business Impact
- Reduces losses by avoiding high-risk loans.
- Improves approval rates for safe customers.
- Introduces a *Medium-risk segment* for flexible lending.
- Model is explainable & practical → similar to fintech leaders like *Navi, Paytm*.

---

## 🚀 Future Enhancements
- Add SHAP explainability for borrower-level insights.
- Deploy as a *Streamlit dashboard* or *Power BI app* for real-time monitoring.
- Integrate with APIs (Flask / FastAPI) for embedding into fintech workflows.

---

## 🛠 Tech Stack
- Python (Pandas, NumPy, Matplotlib, Seaborn)
- Scikit-learn (Logistic Regression, Random Forest, metrics)
- XGBoost
- Jupyter Notebook / Google Colab

---
