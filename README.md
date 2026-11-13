# Credit-Wise Loan Approval Prediction

## Project Overview

Credit-Wise is a Machine Learning project that predicts whether a loan application will be approved or rejected based on applicant information such as income, credit score, employment status, existing loans, savings, and other financial attributes.

The project explores different classification algorithms and compares their performance using multiple evaluation metrics.

## Problem Statement

Loan approval decisions involve evaluating several financial and personal attributes of applicants. This project uses historical loan application data to build classification models that predict loan approval outcomes.

## Dataset

- Total records: 1,000
- Total features: 19 input features + 1 target variable
- Target variable: `Loan_Approved`
- Problem type: Binary Classification

The dataset contains numerical and categorical features, including:

- Applicant Income
- Coapplicant Income
- Credit Score
- Age
- Employment Status
- Marital Status
- Existing Loans
- Debt-to-Income (DTI) Ratio
- Savings
- Loan Amount
- Loan Purpose
- Property Area

## Technologies Used

- Python
- Jupyter Notebook
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn

## Project Workflow

### 1. Data Exploration and Preprocessing

- Inspected dataset structure and statistical summaries.
- Identified missing values.
- Used Mean Imputation for numerical features.
- Used Most Frequent Imputation for categorical features.
- Removed the Applicant_ID column.

### 2. Exploratory Data Analysis (EDA)

Performed visual analysis to understand:
- Loan approval distribution.
- Distribution of categorical variables.
- Applicant income distribution.
- Relationship between financial attributes and loan approval.
- Potential outliers using boxplots.

### 3. Feature Encoding

- Label Encoding for Education_Level and Loan_Approved.
- One-Hot Encoding for nominal categorical variables.
- Dropped the first category to avoid redundant dummy variables.

### 4. Feature Scaling

Applied StandardScaler to standardize numerical input features before training the classification models.

### 5. Model Training

Implemented and compared three classification algorithms:

- Logistic Regression
- K-Nearest Neighbors (KNN)
- Gaussian Naive Bayes

Used an 80:20 train-test split with random_state=42.

### 6. Model Evaluation

Evaluated models using:

- Accuracy
- Precision
- Recall
- F1-score
- Confusion Matrix

### 7. Feature Engineering

Created additional features to explore whether feature transformations could improve model performance:

- DTI_Ratio_sq
- Credit_Score_sq
- Applicant_Income_log

Retrained Logistic Regression using the engineered features.

## Model Performance

| Model | Accuracy | Precision | Recall | F1-score |
|---|---:|---:|---:|---:|
| Logistic Regression | 86.5% | 78.33% | 77.05% | 77.69% |
| KNN | 76% | 62.75% | 52.46% | 57.14% |
| Gaussian Naive Bayes | 86.5% | 80.36% | 73.77% | 76.92% |
| Logistic Regression + Feature Engineering | **87%** | 77.78% | **80.33%** | **79.03%** |

## Key Findings

- Logistic Regression and Gaussian Naive Bayes achieved 86.5% accuracy.
- KNN achieved 76% accuracy.
- Feature engineering improved Logistic Regression accuracy to 87%.
- The feature-engineered Logistic Regression achieved the highest F1-score of approximately 79.03%.

## How to Run the Project

1. Clone this repository:

   ```bash
   git clone YOUR_GITHUB_REPOSITORY_URL
   ```

2. Navigate to the project directory:

   ```bash
   cd loan-approval-prediction
   ```

3. Install the required libraries:

   ```bash
   pip install pandas numpy matplotlib seaborn scikit-learn jupyter
   ```

4. Launch Jupyter Notebook:

   ```bash
   jupyter notebook
   ```

5. Open `credit_wise_loan_system.ipynb` and execute the cells.

## Project Structure

```text
loan-approval-prediction/
│
├── credit_wise_loan_system.ipynb
├── loan_approval_data.csv
├── README.md
└── .gitignore
```

## Future Improvements

- Perform hyperparameter tuning.
- Use cross-validation for more robust evaluation.
- Experiment with ensemble classification algorithms.
- Build an interactive loan prediction application.

---

**Disclaimer:** This project is for educational and machine learning practice purposes. Predictions should not be used as the sole basis for real-world financial decisions.