# Telco Churn Analysis & Data Cleaning

## Project Overview
This project focuses on the critical business challenge of customer retention in the telecommunications industry. Using raw customer data, the project involves a complete pipeline from uncleaned records to a usable format for meaningful analysis. The goal is to identify patterns associated with customer churn and prepare the data for predictive modeling.

### Key Objectives:
* **Data Preparation:** Convert raw CSV data into a clean, normalized format suitable for analysis.
* **Methodology Documentation:** Provide transparent, reproducible code detailing the exact steps taken to clean and transform the dataset.
* **Analysis & Reporting:** Generate actionable insights from key performance indicators like Monthly Charges, Tenure, and Active Service Count.

---

## Telco Churn Dataset

### Overview
This dataset captures demographic details, service usage, and account information for telecom customers. It explores the relationship between service types (Fiber optic vs. DSL), contract terms, and customer loyalty (Churn).

**[View Raw CSV Data](Telco_Churn_Project_Row_Dataset.csv)**

### Dataset Structure
* **Total Records:** 7,043
* **Total Features:** 27
* **Target Variable:** Churn (Yes/No)

### Feature Descriptions
| Column | Description |
| :--- | :--- |
| **customerID** | Unique identifier for each customer. |
| **tenure** | Number of months the customer has stayed with the company. |
| **InternetService** | Customer’s internet service provider (DSL, Fiber optic, No). |
| **Contract** | The contract term of the customer (Month-to-month, One year, Two year). |
| **MonthlyCharges** | The amount charged to the customer monthly. |
| **TotalCharges** | The total amount charged to the customer. |
| **ActiveServiceCount** | Engineered feature indicating the total number of services active for a customer. |
| **TenureGroup** | Categorical grouping of tenure (e.g., 0-1yr, 2-4yr). |
| **PriceSensitivity** | Engineered metric reflecting customer sensitivity to monthly cost changes. |

---

## Data Analysis & Technical Summary
This project utilizes a comprehensive data cleaning and exploratory data analysis (EDA) pipeline.

**[View Data Cleaning Code](Data_Cleaning_Code.ipynb)**

### 1. Data Cleaning & Preprocessing
* **Column Removal:** Dropped non-essential columns such as `customerID`, `CLV_proxy`, and `AvgChargesPerYear` to focus on predictive features.
* **Missing Value Management:** Identified null values in critical columns like `tenure` (644 missing), `MonthlyCharges` (415 missing), and `TotalCharges` (495 missing).
* **Data Types:** Standardized numerical columns to `float64` for calculations and handled categorical variables as `object` types.

### 2. Exploratory Data Analysis (EDA)
* **Descriptive Statistics:** Calculated mean monthly charges (~$64.65) and average tenure (~32 months) to establish baseline customer behavior.
* **Feature Correlation:** Explored the relationship between `MonthlyCharges` and `TotalCharges` to identify billing inconsistencies.
* **Service Impact:** Analyzed `ActiveServiceCount` to determine if multi-service customers have higher retention rates.

### 3. Libraries Used
* **Pandas & NumPy:** For data manipulation and cleanup.
* **Matplotlib & Seaborn:** For statistical visualizations.
* **Scikit-Learn:** For preprocessing and model preparation (StandardScaler, LabelEncoder).

---

## Cleaned Dataset Summary 

**[View Clean_Data](Telco_Churn_Clean_Dataset.xlsx)**

### 1. Data Integrity
* **Numerical Imputation:** Prepared strategies for handling missing values in `TotalCharges` and `tenure`.
* **Normalization:** Applied scaling techniques to ensure features like `MonthlyCharges` and `tenure` are comparable for modeling.

### 2. Key Observations
* **Customer Longevity:** The average customer tenure is 32.17 months, though 25% of customers have been with the provider for 8 months or less.
* **Billing Patterns:** Monthly charges range widely from $18.25 to $118.75, with a median of $70.27.
* **High Value Segments:** Approximately 47% of customers are classified as "High Value" based on the `HighValueCustomer` metric.

---

## Conclusion
Understanding customer churn is vital for sustainable growth in telecommunications. This project demonstrates how systematic data cleaning—from dropping redundant features to managing missing values—uncovers the underlying patterns that drive customer loyalty. By focusing on engineered features like `ActiveServiceCount` and `PriceSensitivity`, businesses can proactively target at-risk customers.
