# 📊 Loan Delinquency Prediction

A machine learning project that predicts whether a borrower will become seriously delinquent on a loan (90+ days past due) within a 12-month period. The task is framed as a binary classification problem and focuses on estimating credit risk from borrower and credit-history features.

## 🎯 Project Objective

Build and validate a model that predicts the probability of a loan becoming 90+ days delinquent within the next 12 months. The target variable is `target`:

- `0` — no 90+ day delinquency;
- `1` — 90+ day delinquency.

## 🗂️ Dataset

The project uses the supplied training and validation datasets:

- `train_data.csv` — training data;
- `valid_data.csv` — validation data.

The original training dataset contains 55,712 rows and 38 columns; the original validation dataset contains 13,520 rows. The notebook applies data cleaning and removes duplicate records before model evaluation. The datasets are not included in this repository by default because they may contain sensitive financial information. Add them locally before running the notebook, if you are authorized to use them.

## ⚙️ Workflow

1. **Exploratory data analysis** — inspect dataset structure, descriptive statistics, missing values, target distribution, and feature correlations.
2. **Data preprocessing** — remove selected columns, handle missing values, remove duplicate records, and prepare numerical and categorical features.
3. **Feature engineering and selection** — create age groups, examine feature relationships, and remove selected low-correlation or redundant features.
4. **Outlier treatment and scaling** — cap selected numerical features at the 1st and 99th percentiles and standardize features.
5. **Model training and tuning** — train several classification algorithms and tune hyperparameters with `GridSearchCV` and stratified cross-validation.
6. **Model evaluation** — compare ROC-AUC and classification metrics on the validation data and visualize ROC curves.

## 🤖 Models

The notebook experiments with:

- Logistic Regression
- Decision Tree
- Random Forest
- XGBoost
- AdaBoost

Class imbalance is addressed using class weights or `scale_pos_weight`, depending on the model.

## 📁 Repository Structure

```text
.
├── loan_delequency_prediction.ipynb..ipynb   # EDA, preprocessing, model training and evaluation
├── train_data.csv                      # Training dataset (not committed)
├── valid_data.csv                      # Validation dataset (not committed)
└── README.md
```

## 🚀 How to Run

1. Clone this repository.
2. Create and activate a Python virtual environment.
3. Install the required packages:

   ```bash
   pip install pandas numpy matplotlib seaborn scikit-learn xgboost jupyter
   ```

4. Place `train_data.csv` and `valid_data.csv` in the project directory, if you have permission to access them.
5. Launch Jupyter Notebook and open `loan_delequency_prediction.ipynb.`.

   ```bash
   jupyter notebook
   ```
