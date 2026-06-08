# DecodeLabs_Task2

# Data Analytics Project 2 – Exploratory Data Analysis (EDA)

[![Python 3.8+](https://img.shields.io/badge/python-3.8+-blue.svg)](https://www.python.org/downloads/)
[![Pandas](https://img.shields.io/badge/pandas-2.0+-green.svg)](https://pandas.pydata.org/)
[![License](https://img.shields.io/badge/license-MIT-blue.svg)](LICENSE)

**Industrial Training Kit** – Batch 2026 | Powered by DecodeLabs

# Overview

This project is the second milestone in the DecodeLabs data analytics track. It focuses on Exploratory Data Analysis (EDA) the forensic process of interrogating raw data to uncover hidden patterns, trends, outliers, and distributions before any predictive modeling or dashboarding.

The goal is to transform a static table of numbers into actionable business insights using only descriptive statistics and analytical logic.

# Key EDA Concepts Applied

- **IPO Framework**: Input (raw data) → Process (statistical transformation) → Output (insights)
- **Centre of Gravity**: Mean vs. Median and what they reveal about skewness
- **Five‑Number Summary**: Min, Q1, Median, Q3, Max
- **Outlier Detection**: IQR method (robust) and Z‑score method (normal distributions)
- **Correlation Analysis**: Pearson’s r (strength & direction of linear relationships)
- **The Golden Rule**: Correlation ≠ Causation; always check for confounders

# Dataset

The analysis uses a transactional sales dataset (`Dataset_for_Data_Analytics.xlsx`) with **1200 orders** and **14 columns**. No synthetic data real‑world like business records.

| Column Name        | Type          | Description                                      |
|--------------------|---------------|--------------------------------------------------|
| `OrderID`          | object (key)  | Unique order identifier                         |
| `CustomerID`       | object (key)  | Unique customer identifier                      |
| `Product`          | object        | Product name (10 unique categories)             |
| `Date`             | datetime      | Order date (range: 2023‑01‑04 to 2024‑08‑23)    |
| `Quantity`         | int64         | Number of units per order (1–7)                 |
| `UnitPrice`        | float64       | Price per unit (10.01 – 999.58)                 |
| `TotalPrice`       | float64       | Quantity × UnitPrice                            |
| `ItemsInCart`      | int64         | Total items added to cart (1–7)                 |
| `ShippingAddress`  | object        | Unique shipping address per order               |
| `PaymentMethod`    | object        | 5 methods (Credit Card most frequent)           |
| `OrderStatus`      | object        | 4 statuses (Delivered most frequent)            |
| `TrackingNumber`   | object (key)  | Unique shipment tracking code                   |
| `ReferralSource`   | object        | 5 sources (Social Media most frequent)          |
| `CouponCode`       | object        | 6 codes, **309 missing values (≈25.8%)**        |

 **Missing values** are only in `CouponCode`and all other columns are complete.

# Analysis Steps

The Google Colab script executes the following EDA pipeline:

1. **Load Data** :Read Excel into a pandas DataFrame.
2. **Initial Inspection**: `df.head()` to preview structure.
3. **Data Types & Memory**: `df.info()` to identify numeric vs. categorical columns and spot missing data.
4. **Descriptive Statistics**  
   - `df.describe()` for numerical columns (mean, std, min, max, quartiles).  
   - `df.describe(include='all')` for categorical columns (unique counts, top values, frequencies).
5. **Pattern Synthesis**: Summarise distributions, central tendencies, spread, and categorical dominance.

No external visualisation libraries are required for the core statistical summary. The Colab outputs clear tabular evidence.

# How to Run This Project

You can run the analysis either on **Google Colab** (recommended, no setup) or **locally** on your machine.

# Run on Google Colab

1. **Upload the notebook & dataset to your Google Drive**  
   - Place `DecodeLab_Task2.ipynb` (or your Colab script) and `Dataset for Data Analytics.xlsx` in the same folder inside Google Drive.

2. **Open with Colab**  
   - Right‑click the `.ipynb` file → “Open with Google Colab”.

3. **Mount Google Drive** (if your script uses drive paths)  
   ```python
   from google.colab import drive
   drive.mount('/content/drive')



**Author**

**Zulqarnain Talpur**

**Data Analytics Intern**

**DecodeLabs Industrial Training Program.**
