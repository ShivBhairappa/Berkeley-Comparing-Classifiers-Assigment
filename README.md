# Berkeley-Comparing-Classifiers-Assigment

# Bank Marketing Campaign Classifier

This project applies machine learning techniques to predict the success of direct bank marketing campaigns based on telephonic outreach data. The analysis is conducted following the **CRISP-DM** methodology and compares four classification models to guide decision-making and campaign optimization.

## Dataset

- **Source**: [UCI Machine Learning Repository](https://archive.ics.uci.edu/ml/datasets/Bank+Marketing)
- **File used**: `bank-additional-full.csv`
- **Instances**: 41,188
- **Features**: 20 input features + 1 binary target variable (`y`: client subscribed to term deposit: `yes`/`no`)
- **Note**: The feature `duration` is removed due to its data leakage potential (only known after a call).

## Business Objective

Improve the efficiency of direct marketing campaigns by predicting whether a client will subscribe to a term deposit. This enables better targeting, reduces costs, and increases campaign effectiveness.

## Methodology: CRISP-DM

1. **Business Understanding**: Define the goal to reduce unnecessary outreach.
2. **Data Understanding**: Load and explore dataset characteristics.
3. **Data Preparation**:
   - Drop `duration` column
   - Handle `unknown` values
   - One-hot encode categorical features
   - Scale features and split into train/test sets
4. **Modeling**: Compare four classifiers:
   - Logistic Regression
   - k-Nearest Neighbors (k-NN)
   - Decision Tree
   - Support Vector Machine (SVM)
5. **Evaluation**:
   - Classification Report (Precision, Recall, F1-score)
   - ROC Curve & AUC
6. **Insights & Recommendations**:
   - Identify best model
   - Offer deployment strategies
   - Suggest campaign optimization steps

## Models Compared

| Model                | Evaluation Metric | Notes                          |
|---------------------|-------------------|--------------------------------|
| Logistic Regression | ROC-AUC, F1-score | Fast, interpretable            |
| k-NN                | ROC-AUC           | Requires scaling, sensitive to `k` |
| Decision Tree       | Accuracy, AUC     | Easy to interpret, prone to overfit |
| SVM                 | Highest ROC-AUC   | Best performance, but more complex |

## Results Summary

- **SVM** showed the highest ROC AUC, indicating strong predictive performance.
- Decision Tree and Logistic Regression also performed reasonably well and offer easier interpretability.
- Longer calls and specific months (e.g. March, June) showed higher success probabilities in past research.

## Recommendations

- Use SVM or Logistic Regression models for predicting likely subscribers.
- Focus marketing calls during high-success months.
- Integrate the model into CRM systems to prioritize outreach.
- Consider re-training periodically with updated data.

##  Technologies Used

- Python
- Scikit-learn
- Pandas, NumPy, Matplotlib
- Google Colab
