## Bancassurance

### Overview
🏦 Project Title: Predicting Customer Propensity to Buy Insurance in a Bank<br/>
🎯 Goal: Use customer data from a bank to build a predictive model that identifies clients most likely to purchase insurance products (e.g., life insurance, credit protection, property insurance).<br/>

📊 Project Workflow: <br/>

1. Business Understanding<br/>
- Banks often offer insurance products to their existing clients.
- Goal: improve cross-selling by targeting the right customers.

2. Data Collection<br/>
- Bank transaction records
- Customer profiles (age, income, job type, loan history)
- Product purchase history (including insurance)
- Call center and marketing campaign logs

3. Data Cleaning & Preprocessing<br/>
- Handling missing values (e.g., unknown job type)
- Encoding categorical features (e.g., one-hot encoding for education level)
- Normalizing numeric features (e.g., income)
- Feature engineering:
-- Total balance trend
-- Number of products owned
-- Recent campaign responses

4. Exploratory Data Analysis (EDA)<br/>
- Compare insurance buyers vs. non-buyers
- Correlation heatmaps
- Analyze age/income groups with higher purchase rates

5. Modeling<br/>
Use classification algorithms:
- Logistic Regression
- Random Forest
- XGBoost

Target variable: Bought_Insurance (Yes/No)<br/>
Evaluate performance with metrics: AUC, F1-score, precision-recall<br/>

6. Model Interpretation<br/>
- Feature importance: e.g., age, prior campaign response, account balance
- SHAP values (if using tree models) to explain individual predictions

7. Deployment / Recommendation<br/>
- Use model output to rank customers for the next campaign
- Deliver list to marketing or sales teams
- Monitor real conversion rates vs. predicted scores

📈 Business Impact:<br/>
- Higher ROI on marketing campaigns
- Better customer targeting
- Improved customer experience (less spammy offers)



### Results

#### 1) Logistic Regression<br/>

Confusion Matrix
| (TN) 984 | (FP) 222 |
|----------|----------|
| (FN) 270 | (TP) 924 | 
  
Classification Report
|              | precision | recall  | f1-score | support |
|--------------|-----------|---------|----------|---------|
| 0            | 0.78      | 0.82    | 0.80     | 1206    |
| 1            | 0.81      | 0.77    | 0.79     | 1194    |
| accuracy     |           |         | 0.80     | 2400    |
| macro avg    | 0.80      | 0.79    | 0.79     | 2400    |
| weighted avg | 0.80      | 0.80    | 0.79     | 2400    |

ROC AUC Score: 0.8704606504051489


✅ Model Interpretation Summary (Logistic Regression)

1. Confusion Matrix<br/>
True Negatives (TN): 984 → Non-buyers correctly predicted<br/>
False Positives (FP): 222 → Non-buyers predicted as buyers<br/>
False Negatives (FN): 270 → Buyers predicted as non-buyers<br/>
True Positives (TP): 924 → Buyers correctly predicted<br/>

2. Classification Report<br/>
Precision (class 1): 0.81 → When the model predicts a customer will buy insurance, it’s right 81% of the time.<br/>
Recall (class 1): 0.77 → It captures 77% of actual insurance buyers.<br/>
F1-score (class 1): 0.79 → Good balance of precision and recall.<br/>
Accuracy: 80% overall correct predictions.<br/>

3. ROC AUC Score: 0.870<br/>
This is a very strong score — indicating the model is very capable of distinguishing between buyers and non-buyers.<br/>

🧠 What This Tells You<br/>
The logistic regression model is already performing quite well.<br/>
There's slight room to improve recall — especially if your goal is not to miss potential buyers (e.g., for marketing).<br/>
False positives (222) are acceptable if you're willing to market to some who won’t buy, but want to catch more potential buyers.


#### 2) Random Forest<br/>

Confusion Matrix
| (TN) 1139 | (FP) 67   |
|-----------|-----------|
| (FN) 0    | (TP) 1194 | 
  
Classification Report
|              | precision | recall  | f1-score | support |
|--------------|-----------|---------|----------|---------|
| 0            | 1.00      | 0.94    | 0.97     | 1206    |
| 1            | 0.95      | 1.00    | 0.97     | 1194    |
| accuracy     |           |         | 0.97     | 2400    |
| macro avg    | 0.97      | 0.97    | 0.97     | 2400    |
| weighted avg | 0.97      | 0.97    | 0.97     | 2400    |

ROC AUC Score: 0.999866316102347


✅ Random Forest Model Interpretation

📊 Confusion Matrix<br/>
True Negatives (TN): 1139 – Non-buyers correctly identified.<br/>
False Positives (FP): 67 – Predicted as buyers, but didn’t buy.<br/>
False Negatives (FN): 0 – Perfectly predicted all actual buyers.<br/>
True Positives (TP): 1194 – Buyers correctly identified.<br/>

📄 Classification Report<br/>
Accuracy: 97% — Extremely high.<br/>
F1-score: Balanced precision and recall for both classes.<br/>
Recall (class 1): 1.00 → Captures all buyers — excellent for a marketing model.<br/>

📈 ROC AUC Score: 0.9999<br/>
This is near perfect. The model very clearly separates the two classes.<br/>

💡 Should You Trust These Results?<br/>
Such strong results could suggest:<br/>
✅ The model generalizes well.<br/>
❗ Or it's overfitting (especially if your test set was small or resampled improperly).

