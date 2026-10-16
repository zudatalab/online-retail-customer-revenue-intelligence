<div align="center">
  
  # 🛍️ Online Retail Customer & Revenue Intelligence

  **A Pandas-Based Business Analytics Project**
</div>

Analyze retail transactions to understand revenue performance, customer purchasing behavior, product performance, country-level sales, and time-based business trends using Python and Pandas.
<div align="center">
  
  ![Python](https://img.shields.io/badge/Python-3.x-blue?logo=python)
  ![Pandas](https://img.shields.io/badge/Pandas-Data%20Analysis-150458?logo=pandas)
  ![Jupyter](https://img.shields.io/badge/Jupyter-Notebooks-orange?logo=jupyter)
  ![Status](https://img.shields.io/badge/Status-Completed-success)
</div>

## 📑 Table of Contents

1. [Project Overview](#1-project-overview)
2. [Business Problem](#2-business-problem)
3. [Project Objectives](#3-project-objectives)
4. [Dataset Description](#4-dataset-description)
5. [Project Structure](#5-project-structure)
6. [Tools and Technologies](#6-tools-and-technologies)
7. [Project Workflow](#7-project-workflow)
8. [Notebook-by-Notebook Breakdown](#8-notebook-by-notebook-breakdown)
9. [Data Cleaning and Quality Decisions](#9-data-cleaning-and-quality-decisions)
10. [Key Business Findings](#10-key-business-findings)
11. [Analytical Methodology](#11-analytical-methodology)
12. [How to Run the Project](#12-how-to-run-the-project)
13. [Data Limitations and Assumptions](#13-data-limitations-and-assumptions)
14. [Skills Demonstrated](#14-skills-demonstrated)
15. [Future Improvements](#15-future-improvements)
16. [Author](#16-author)

## 📌 Project Overview

Online Retail Customer & Revenue Intelligence is an exploratory data analysis project built using Python, Pandas, NumPy, and Jupyter Notebook.

The project uses the Online Retail dataset from the UCI Machine Learning Repository. It contains transactional records from a UK-based online retailer and provides information about invoices, products, quantities, unit prices, transaction dates, customers, and countries.

The objective is to transform raw transaction records into meaningful business insights through structured data understanding, data quality assessment, cleaning, aggregation, and business analysis.

The project is organized into seven Jupyter notebooks, progressing from initial dataset exploration to customer intelligence, product and country performance, and time-based analysis.

**Project scope:** Pandas-based data analysis and business intelligence. Machine learning model development is outside the scope of this project.

## 🎯 Business Problem

Retail businesses generate large amounts of transactional data, but raw records alone do not explain how the business is performing.

Business stakeholders need to understand questions such as:

- How much net revenue does the business generate?
- Which customers contribute the most revenue?
- Which customers purchase frequently?
- Which products generate the highest revenue?
- Which products have the highest net quantities sold?
- Which countries generate the most revenue?
- How does revenue change from month to month?
- Which weekdays have the highest invoice activity?
- What data quality issues must be considered before making business decisions?

This project addresses these questions using reproducible data analysis workflows.

## 🎯 Project Objectives

The main objectives are to:

- Understand the structure and characteristics of a real-world retail dataset.
- Identify missing values, duplicate records, and unusual transaction values.
- Clean the dataset while preserving meaningful transactional information.
- Calculate revenue, invoice, and transaction-level business metrics.
- Analyze customer purchasing behavior and customer contribution.
- Identify high-performing products using revenue and quantity.
- Compare revenue, invoice activity, and customer reach across countries.
- Investigate monthly revenue trends and weekday purchasing patterns.
- Communicate findings through clear business insights and conclusions.

## 📊 Dataset Description

**📂 Dataset:** Online Retail

**🔗 Source:** UCI Machine Learning Repository

**Official dataset page:** https://archive.ics.uci.edu/dataset/352/online+retail

**Original file:** `Online Retail.xlsx`

The dataset contains transactions from a UK-based online retailer between December 2010 and December 2011.

### Original dataset overview

| Attribute | Value |
|---|---:|
| Original records | 541,909 |
| Original columns | 8 |
| Final cleaned records | 536,641 |
| Final columns | 8 |
| Exact duplicate rows removed | 5,268 |
| Unique invoice numbers | 25,900 |
| Unique customers | 4,372 |
| Countries represented | 38 |

### Dataset columns

| Column | Description |
|---|---|
| `InvoiceNo` | Invoice identifier. Invoices beginning with `C` indicate cancellations in this dataset. |
| `StockCode` | Identifier or code associated with a product or transaction item. |
| `Description` | Product description. |
| `Quantity` | Quantity recorded for the transaction line; negative values can occur. |
| `InvoiceDate` | Date and time of the transaction. |
| `UnitPrice` | Unit price recorded for the transaction line. |
| `CustomerID` | Customer identifier, which may be missing. |
| `Country` | Country associated with the transaction. |

### Derived feature

The project creates a `Revenue` column:

`Revenue = Quantity × UnitPrice`

This represents the signed transaction-line amount based on the available quantity and unit price. Summing this field gives **net transaction revenue as calculated for this analysis**, including negative transaction amounts.

## 🗂️ Project Structure

The project contains seven Jupyter notebooks and a cleaned dataset.

```text
Online-Retail-Customer-Revenue-Intelligence/
│
├── 01_data_understanding.ipynb
├── 02_data_quality.ipynb
├── 03_data_cleaning.ipynb
├── 04_business_metrics.ipynb
├── 05_customer_intelligence.ipynb
├── 06_product_country_analysis.ipynb
├── 07_time_analysis.ipynb
│
├── online_retail_cleaned.xlsx
└── README.md
```

Keep the cleaned Excel file in the location expected by the notebooks. If you use a different folder structure, update the file paths accordingly.

## 🛠️ Tools and Technologies

- **Python:** General-purpose programming language used for data analysis.
- **Pandas:** Data loading, cleaning, grouping, aggregation, and analysis.
- **NumPy:** Numerical operations and numeric comparisons where required.
- **Jupyter Notebook:** Interactive environment for executing code and documenting analysis.
- **Excel:** Source and cleaned data storage in spreadsheet format.
- **Git and GitHub:** Recommended for version control and project sharing.

### Key Pandas functionality used

- `read_excel()`
- `head()`, `tail()`, `shape`, `columns`, `info()`, `describe()`
- `isnull()`, `sum()`, `duplicated()`, `drop_duplicates()`, `fillna()`
- `groupby()`, `agg()`, `sum()`, `mean()`, `nunique()`
- `sort_values()`, `reset_index()`
- `dt.year`, `dt.month`, `dt.to_period()`, `dt.day_name()`

## 🔄 Project Workflow

The analysis follows a structured workflow:

1. **Data Understanding:** Inspect the dataset's structure, columns, data types, and descriptive statistics.
2. **Data Quality Assessment:** Identify missing values, duplicate records, and unusual values.
3. **Data Cleaning:** Remove exact duplicates and handle missing descriptions while preserving important transaction details.
4. **Business Metrics:** Calculate revenue, invoice counts, average invoice value, and country-level revenue.
5. **Customer Intelligence:** Analyze customer revenue, invoice frequency, purchasing quantities, product variety, and purchase history.
6. **Product and Country Analysis:** Compare products by net revenue and quantity, and evaluate country performance.
7. **Time Analysis:** Analyze monthly revenue, monthly invoice activity, and weekday-level performance.

Each notebook builds on the concepts and outputs of the preceding analysis.

## 📓 Notebook-by-Notebook Breakdown

### Notebook 01 — 🔍 Data Understanding

**File:** `01_data_understanding.ipynb`

Purpose:
- Load the original dataset.
- Inspect rows, columns, and data types.
- Understand dataset dimensions.
- Review descriptive statistics and sample records.

**Outcome:** Initial understanding of the dataset and its structure.

### Notebook 02 — 🧪 Data Quality

**File:** `02_data_quality.ipynb`

Purpose:
- Check missing values.
- Identify exact duplicate rows.
- Inspect unusual quantity and unit-price values.
- Investigate cancellation-related invoice identifiers.
- Assess data quality issues before cleaning.

**Outcome:** A documented understanding of the dataset's quality issues.

### Notebook 03 — 🧹 Data Cleaning

**File:** `03_data_cleaning.ipynb`

Purpose:
- Preserve a copy of the original data.
- Remove exact duplicate rows.
- Handle missing product descriptions.
- Preserve missing customer identifiers for transparency.
- Validate the cleaned dataset.

**Outcome:** A cleaned dataset saved as `online_retail_cleaned.xlsx`.

### Notebook 04 — 💰 Business Metrics

**File:** `04_business_metrics.ipynb`

Purpose:
- Calculate transaction-line revenue.
- Calculate total net revenue.
- Count unique invoices and customers.
- Analyze cancellation-prefixed invoice rows.
- Compare revenue by month and country.
- Calculate invoice-level revenue and average invoice value.
- Validate revenue aggregation consistency.

**Outcome:** Core business performance metrics and initial revenue insights.

### Notebook 05 — 👥 Customer Intelligence

**File:** `05_customer_intelligence.ipynb`

Purpose:
- Identify top customers by total net revenue.
- Rank customers by unique invoice count.
- Calculate average invoice value per customer.
- Analyze net quantity by customer.
- Compare customers by unique products purchased.
- Identify customers with at least five unique invoices.
- Calculate first purchase date, last purchase date, and purchase-history duration.
- Build a consolidated customer summary table.

**Outcome:** A customer-level summary suitable for further segmentation and business analysis.

### Notebook 06 — 🛒 Product and 🌍 Country Analysis

**File:** `06_product_country_analysis.ipynb`

Purpose:
- Calculate net revenue by product code.
- Identify the top 10 products by net revenue.
- Identify the top 10 products by net quantity.
- Calculate country-level net revenue.
- Count unique invoices and unique customers by country.
- Compare country performance and document business observations.

**Outcome:** Product performance rankings and a country-level business summary.

### Notebook 07 — 📅 Time Analysis

**File:** `07_time_analysis.ipynb`

Purpose:
- Calculate monthly net revenue using year-month periods.
- Identify peak and slower revenue months.
- Calculate monthly unique invoice counts.
- Compare weekday-level revenue.
- Compare weekday-level invoice activity.
- Document time-based business insights.

**Outcome:** An overview of monthly and weekly business activity patterns.

## 🧹 Data Cleaning and Quality Decisions

Data cleaning decisions were made with the aim of preserving the meaning of the original transactions.

### 1 Exact duplicate rows

The original dataset contained 5,268 exact duplicate rows.

These rows were removed, resulting in a cleaned dataset of **536,641 rows and 8 columns**.

### 2 Missing product descriptions

Missing values in `Description` were filled with `"Unknown"`.

This allows product-related grouping and reporting to retain records whose descriptions are unavailable.

### 3 Missing customer identifiers

Missing `CustomerID` values were intentionally preserved.

Customer-level `groupby()` operations generally exclude rows with missing group keys, so customer summaries represent transactions associated with identified customers rather than all transactions.

### 4 Negative quantities and prices

Negative or zero values in `Quantity` and `UnitPrice` were not automatically removed.

Negative quantities can reflect returns or other adjustments. Special negative-price accounting records were also preserved because they may represent legitimate financial adjustments rather than ordinary product sales.

### 5 Cancellation-prefixed invoices

Invoice identifiers beginning with `C` were inspected as cancellation-related records.

A count of rows beginning with `C` is not the same as a count of unique cancellation invoices. Invoice-level and row-level metrics should be distinguished.

### 6 Revenue calculation

Revenue was calculated as:

`Quantity × UnitPrice`

Negative values were retained, meaning that the total is a signed net amount rather than a gross sales total that excludes returns and adjustments.

## 📈 Key Business Findings

The following findings were observed in the analysis. Monetary figures are presented in the dataset's reported units; no currency symbol is assumed here.

### 1 Overall revenue

- Total net transaction revenue was approximately **9,726,006.95**.
- The calculation includes negative transaction amounts.
- Revenue aggregation was checked against invoice-level revenue totals.

### 2 Country performance

The United Kingdom was the leading country by net revenue.

| Country | Total net revenue | Unique invoices | Unique customers |
|---|---:|---:|---:|
| United Kingdom | 8,167,128.184 | 23,494 | 3,950 |
| Netherlands | 284,661.540 | 101 | 9 |
| EIRE | 262,993.380 | 360 | 3 |
| Germany | 221,509.470 | 603 | 95 |
| France | 197,317.110 | 461 | 87 |
| Australia | 137,009.770 | 69 | 9 |
| Switzerland | 56,363.050 | 74 | 21 |
| Spain | 54,756.030 | 105 | 31 |
| Belgium | 40,910.960 | 119 | 25 |
| Sweden | 36,585.410 | 46 | 8 |

**Interpretation:** The United Kingdom generated substantially more net revenue and recorded substantially more unique invoices and customers than any other country in the reported top 10. This indicates a strong concentration of business activity in the UK.

### 3 Product performance

The top products by net revenue and net quantity were analyzed separately.

Selected findings:
- The `DOT` code ranked first by net revenue, at approximately **206,245.48**.
- Product code `22423` ranked second by net revenue, at approximately **164,459.49**.
- Product code `22197` ranked first by net quantity, with **56,427 units**.

**Interpretation:** High revenue and high quantity measure different aspects of product performance. Special codes such as `DOT` should be investigated before interpreting them as ordinary products.

### 4 Monthly revenue trend

| Year-month | Net revenue |
|---|---:|
| November 2011 | 1,456,145.800 |
| October 2011 | 1,069,368.230 |
| September 2011 | 1,017,596.682 |
| April 2011 | 492,367.841 |
| December 2011 | 432,701.060 |

**Interpretation:**
- November 2011 was the highest-revenue month in the observed results.
- September and October 2011 also recorded strong revenue.
- April 2011 was the lowest-revenue complete month in the reported results.
- December 2011 is incomplete because the dataset ends on 9 December 2011.

### 5 Monthly invoice activity

- November 2011 recorded **3,462 unique invoices**, the highest monthly count in the observed results.
- October 2011 recorded 2,637 unique invoices.
- September 2011 recorded 2,327 unique invoices.
- December 2011 recorded 1,015 unique invoices, but represents only a partial month.

**Interpretation:** The strong revenue period from September through November coincided with increased invoice activity. This suggests that transaction volume contributed to the observed revenue peak.

### 6 Day-of-week performance

| Weekday | Net revenue | Unique invoices |
|---|---:|---:|
| Thursday | 2,108,701.530 | 5,660 |
| Tuesday | 1,965,703.611 | 4,722 |
| Wednesday | 1,730,088.430 | 4,815 |
| Monday | 1,584,895.301 | 4,138 |
| Friday | 1,537,958.621 | 4,184 |
| Sunday | 798,659.461 | 2,381 |

**Interpretation:**
- Thursday had the highest observed net revenue and invoice activity.
- Tuesday was the second-highest day by net revenue.
- Sunday had the lowest observed net revenue and invoice count.
- Differences in operating schedules may contribute to these patterns, but the dataset alone does not establish the cause.

## ⚙️ Analytical Methodology

The project primarily uses descriptive analysis and group-based aggregation.

### Revenue calculation

Revenue is calculated at the transaction-line level:

`Revenue = Quantity × UnitPrice`

The sum of this column represents the signed net amount of the included transaction lines.

### Customer-level aggregation

Customer metrics are calculated by grouping transactions by `CustomerID`, including:
- Total net revenue
- Unique invoice count
- Total net quantity
- Unique product-code count
- First purchase date
- Last purchase date
- Purchase-history duration in days

Missing customer identifiers are excluded from customer-keyed summaries by default.

### Product-level aggregation

Product metrics are calculated using `StockCode` as the grouping key. This avoids treating inconsistent or missing descriptions as separate product identifiers when the same stock code is present.

### Country-level aggregation

Country summaries combine net revenue, unique invoice count, and unique customer count into one table.

### Time-based aggregation

Monthly analysis uses year-month periods rather than month numbers alone. This prevents January from different years being combined into a single category.

Weekday analysis uses the day name extracted from `InvoiceDate`.

### Validation

The project includes checks of dataset dimensions, missing values, revenue aggregation, and other outputs to support consistent analysis.

## 🚀 How to Run the Project

### Prerequisites

Install Python and Jupyter Notebook, then install the required libraries.

```bash
pip install pandas numpy openpyxl jupyter
```

### Step 1 — Obtain the dataset

Download the original Online Retail dataset from the [UCI Machine Learning Repository](https://archive.ics.uci.edu/dataset/352/online+retail).

Place the original Excel file where Notebook 01 expects it.

### Step 2 — Open the project

Open a terminal in the project directory and start Jupyter:

```bash
jupyter notebook
```

Alternatively, open the project folder in Visual Studio Code and use its Jupyter Notebook support.

### Step 3 — Execute the notebooks in order

Run the notebooks sequentially:

1. `01_data_understanding.ipynb`
2. `02_data_quality.ipynb`
3. `03_data_cleaning.ipynb`
4. `04_business_metrics.ipynb`
5. `05_customer_intelligence.ipynb`
6. `06_product_country_analysis.ipynb`
7. `07_time_analysis.ipynb`

### Step 4 — Confirm file paths

Notebooks that load the cleaned dataset use:

```python
import pandas as pd

df = pd.read_excel("online_retail_cleaned.xlsx")
```

If the `Revenue` column is not already present in the loaded file, recreate it:

```python
df["Revenue"] = df["Quantity"] * df["UnitPrice"]
```

Make sure the cleaned file exists at the expected path before running notebooks that depend on it.

### Step 5 — Verify execution

For a final validation:
- Restart the notebook kernel.
- Run all cells from top to bottom.
- Resolve any errors.
- Confirm that expected tables and outputs appear.
- Save the notebooks after successful execution.

## ⚠️ Data Limitations and Assumptions

The results should be interpreted in light of the following limitations.

1. **Historical data:** The dataset covers a limited historical period and should not be treated as a representation of current retail behavior.

2. **Incomplete December 2011:** The dataset ends on 9 December 2011, so December results are not comparable with complete months without accounting for the partial period.

3. **Missing customer identifiers:** Transactions without a `CustomerID` cannot be reliably assigned to a customer and are excluded from customer-level grouping.

4. **Negative transactions:** Revenue and quantity metrics include negative values. They represent net signed totals, not necessarily gross sales or units shipped.

5. **Special stock codes:** Codes such as `DOT` and other nonstandard identifiers may represent services, fees, or special transaction items. Their exact business meaning should be validated before product-level decisions are made.

6. **Country attribution:** The `Country` field is used as supplied by the dataset. It should not automatically be interpreted as the customer's permanent residence or shipping destination without checking the dataset documentation.

7. **Descriptive rather than causal analysis:** The project identifies patterns and associations. It does not prove why a revenue or invoice pattern occurred.

8. **No predictive modeling:** The project focuses on data analysis and business reporting. It does not build or evaluate machine learning models.

9. **Currency presentation:** Revenue values are reported in the dataset's units. Confirm the dataset's currency convention before adding currency symbols to published charts or reports.

10. **Data cleaning policy:** Exact duplicate removal and the treatment of missing descriptions affect the analytical dataset. These decisions should be documented when comparing results with other analyses.

## 🎓 Skills Demonstrated

This project demonstrates practical skills relevant to entry-level data analytics and ML engineering workflows:

- Loading and inspecting structured data with Pandas.
- Understanding data types and descriptive statistics.
- Identifying missing values and duplicate records.
- Making reasoned data cleaning decisions.
- Creating derived numerical features.
- Performing group-based aggregations.
- Calculating business metrics.
- Analyzing customers, products, and countries.
- Working with datetime columns and time periods.
- Validating results and preserving transaction semantics.
- Translating analytical results into business insights.
- Organizing reproducible notebook-based workflows.

## 🔮 Future Improvements

Possible future extensions include:

- Create charts for monthly revenue and weekday activity.
- Develop a reusable data validation report.
- Add customer segmentation using clearly defined business rules.
- Compare gross sales, returns, and net transaction amounts separately.
- Investigate special stock codes and nonstandard transactions.
- Build an interactive business dashboard.
- Add automated tests for key data quality and aggregation checks.
- Extend the analysis into forecasting or machine learning in a separate project.

These are proposed improvements and are not part of the completed scope unless implemented separately.

## 🙏 Acknowledgements

The dataset is provided by the UCI Machine Learning Repository.

**Dataset citation:** Chen, D. (2015). *Online Retail* [Dataset]. UCI Machine Learning Repository. https://doi.org/10.24432/C5BW33

---
## 👨‍💻 Author

<div align="center">

### ZUBAIR USMAN

Aspiring AI Engineer | ML Engineering | MLOps • LLMOps • AI Infrastructure

[![GitHub](https://img.shields.io/badge/GitHub-zudatalab-black?logo=github)](https://github.com/zudatalab)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-zudatalab-blue?logo=linkedin)](https://www.linkedin.com/in/zudatalab/)
[![X](https://img.shields.io/badge/X-zudatalab-black?logo=x)](https://x.com/zudatalab)

</div>
