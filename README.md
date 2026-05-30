# Heart Disease Dataset — Data Cleaning And Preprocessing

## Overview
This project performs exploratory data analysis (EDA) and data preprocessing on the Heart Disease dataset. The goal is to clean, transform, and prepare the data for machine learning model training.

---

## Dataset
- **File:** `heart.csv`
- **Target Column:** `HeartDisease` (0 = No, 1 = Yes)
- **Features include:** Age, Sex, ChestPainType, RestingBP, Cholesterol, FastingBS, RestingECG, MaxHR, ExerciseAngina, Oldpeak, ST_Slope

---

## Steps Performed

### 1. Importing the Dataset & Basic Exploration
- Loaded the dataset using `pandas`
- Explored the data using `df.shape`, `df.info()`, `df.describe()`, `df.columns`
- Checked for duplicate rows using `df.duplicated().sum()`
- Plotted the distribution of the target variable `HeartDisease`

### 2. Handling Missing Values
- Used `df.isnull().sum()` to check for NaN values
- Numerical columns filled with **median**
- Categorical columns filled with **mode**
- `Cholesterol` and `RestingBP` had medically impossible zero values — replaced with column **mean**

### 3. Categorical Encoding
- Applied One-Hot Encoding using `pd.get_dummies(df, drop_first=True)`
- Converted all encoded columns to `int` type

### 4. Normalizing / Standardizing Numerical Features
- Used `StandardScaler` from `sklearn.preprocessing`
- Applied `fit_transform` on training data and `transform` on test data

### 5. Outlier Detection & Removal
- Visualized outliers using `sns.boxplot()` before removal
- Applied **IQR method** on `Age`, `RestingBP`, `Cholesterol`, `MaxHR`, `Oldpeak`
- Plotted boxplots again after removal to confirm

---

## Libraries Used
| Library | Purpose |
|---------|---------|
| `pandas` | Data loading and manipulation |
| `numpy` | Numerical operations |
| `matplotlib` | Plotting and visualization |
| `seaborn` | Statistical visualizations |
| `sklearn` | Preprocessing and
