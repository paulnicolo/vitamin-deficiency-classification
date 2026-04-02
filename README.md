# Predicting Vitamin Deficiency Diseases
 
A multiclass classification project examining whether patient demographics, lifestyle factors, symptoms, and laboratory measures can predict vitamin deficiency diagnoses.
 
## Dataset
 
Source: [Kaggle — Vitamin Deficiency Disease Prediction Dataset](https://www.kaggle.com/datasets/nudratabbas/vitamin-deficiency-disease-prediction-dataset)
 
The dataset contains patient-level records with features spanning demographic info, dietary intake relative to recommended daily allowances (RDAs), lab values, symptoms, and lifestyle factors. The target variable is `disease_diagnosis` with five classes: Anemia, Healthy, Night Blindness, Rickets Osteomalacia, and Scurvy.
 
> The CSV has been renamed to `vitamin_deficiency_data.csv` in this repo.
 
## Project Structure
 
```
├── predicting_vitamin_deficiency.ipynb   # Main analysis notebook
├── vitamin_deficiency_data.csv           # Dataset (rename from Kaggle download)
└── README.md
```
 
## Workflow
 
The notebook is organized into the following sections:
 
1. **Setup** — library imports
2. **Load the Data** — read and inspect the dataset
3. **Initial Data Inspection** — column types, missing values, and preprocessing decisions
4. **Outlier Review** — identification and retention of clinically plausible extreme values
5. **Exploratory Data Analysis** — demographic, dietary, and laboratory patterns across diagnoses
6. **Modeling**
   - 6.1 Multinomial Logistic Regression — linear baseline with confusion matrix, class metrics, and ROC curves
   - 6.2 Interpreting Logistic Regression Features — coefficients, odds ratios, and per-class top predictors
   - 6.3 Decision Tree Classifier — baseline tree with feature importances and classification report
   - 6.4 Hyperparameter Tuning — grid search over depth, leaf size, and pruning parameters
7. **Conclusion**
 
## Key Findings
 
Nutritional intake and lab values were the dominant predictors across both models, while broad demographics added little signal. Rickets Osteomalacia and Scurvy were the most interpretable classes — each anchored by a single strong feature (vitamin D and vitamin C RDA respectively). Anemia was the most difficult to isolate cleanly, appearing as the default prediction across multiple branches of the decision tree.
 
The tuned decision tree achieved 99.25% test accuracy. Given the synthetic nature of the dataset, this reflects highly deterministic feature-diagnosis relationships in the data rather than a claim about real-world generalizability.
 
## Requirements
 
```
pandas
numpy
matplotlib
seaborn
scikit-learn
```
 
