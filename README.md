# Titanic Dataset Preprocessing

## Project Overview
This project performs basic data preprocessing on the Titanic passenger dataset. The goal is to clean, normalize, and prepare the data for further analysis or machine learning modeling.

## Dataset
- **Source**: [Kaggle Titanic Competition](https://www.kaggle.com/c/titanic/data) or the `seaborn` library (`sns.load_dataset('titanic')`)
- **Description**: Contains information about Titanic passengers, including demographics, ticket class, fare, and survival status.

## Preprocessing Steps
The following operations are applied in the provided Python script:

1. **Load data** – Read the CSV file.
2. **Handle missing values**:
   - `Age` → filled with median.
   - `Embarked` → filled with mode.
   - `Cabin` → dropped due to excessive missing values.
   - `Fare` → filled with median (if missing).
3. **Remove duplicate rows** – Ensures each record is unique.
4. **Handle outliers** – Using the IQR (Interquartile Range) method, values beyond `Q1 - 1.5*IQR` and `Q3 + 1.5*IQR` are capped (winsorized) for numeric columns: `Age`, `Fare`, `SibSp`, `Parch`.
5. **Normalize features** – Applies MinMaxScaler to scale numeric features to a [0,1] range.
6. **Encode categorical variables** (optional but included):
   - `Sex` → mapped to 0 (male) and 1 (female).
   - `Embarked` → one-hot encoded (dummy variables).
7. **Save cleaned dataset** – Exports `titanic_cleaned.csv`.

## Requirements
Install the required Python packages:

```bash
pip install pandas numpy scikit-learn
