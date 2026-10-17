# Retail Sales Data Analytics Using Python

An individual data analytics portfolio project built as part of my journey toward becoming a Data Analyst.

## Project Overview

This project analyzes an online retail transaction dataset to understand sales performance across products, months, and countries. I used Python to explore and clean the data, calculate revenue, identify patterns, and present key findings in a Streamlit dashboard.

**Project type:** Individual portfolio project  
**Focus:** Data cleaning, exploratory data analysis (EDA), sales analysis, and visualization

## Objectives

- Inspect and understand a real-world retail transaction dataset.
- Clean duplicate and unsuitable transaction records using documented rules.
- Calculate revenue from quantity and unit price.
- Identify the highest-revenue products.
- Analyze monthly revenue trends.
- Compare revenue across countries.
- Present the findings through a Streamlit dashboard.

## Tools and Technologies

- **Python** — analysis workflow
- **Pandas** — data loading, cleaning, filtering, grouping, and aggregation
- **NumPy** — numerical operations where needed
- **Matplotlib** — charts and visualizations
- **Streamlit** — web dashboard
- **Jupyter Notebook** — analysis and documentation
- **Git and GitHub** — version control and project hosting

## Dataset

The project uses the **Online Retail** dataset from the UCI Machine Learning Repository.

- Dataset: https://archive.ics.uci.edu/dataset/352/online+retail
- Original data contains retail transactions from 1 December 2010 to 9 December 2011.
- Main columns include `InvoiceNo`, `StockCode`, `Description`, `Quantity`, `InvoiceDate`, `UnitPrice`, `CustomerID`, and `Country`.

Please refer to the original dataset source for its full description and terms of use.

## Analysis Workflow

1. **Load the data** from the Excel source file into a Pandas DataFrame.
2. **Explore the data** using shape, previews, data types, missing-value counts, and duplicate checks.
3. **Remove exact duplicate rows** to reduce double-counting risk.
4. **Apply cleaning rules**, including excluding invoice numbers beginning with `C`, selected `Adjust bad debt` records, rows without descriptions, and rows with non-positive unit prices.
5. **Calculate revenue** for each retained transaction row using:

   `Revenue = Quantity * UnitPrice`

6. **Analyze product revenue** by grouping transactions by description, summing revenue, and ranking the results.
7. **Analyze monthly revenue** by converting invoice dates into year-month periods and aggregating revenue by month.
8. **Analyze country revenue** by grouping transactions by country and comparing revenue totals.
9. **Visualize findings** using Matplotlib and present key metrics and charts in Streamlit.

## Key Findings

The following results were calculated after applying the project's cleaning rules:

- **Rows after cleaning:** 524,877
- **Total calculated revenue:** £10,631,048.74
- **Total units sold:** 5,572,419
- **Unique invoices:** 19,959
- **Unique product codes:** 3,921
- **Countries represented:** 38
- **Highest-revenue month in the recorded data:** November 2011, approximately £1.50 million
- **Highest-revenue country:** United Kingdom, approximately £8.99 million
- **Highest-revenue merchandise product in the selected ranking:** Regency Cakestand 3 Tier, £174,156.54

These are project-derived results, not independently verified official financial statements.

## Cleaning Decisions and Limitations

- Invoice numbers beginning with `C` were treated as cancelled transactions and excluded.
- Rows described as `Adjust bad debt` were excluded from the main sales analysis.
- Rows with missing descriptions or non-positive unit prices were excluded.
- The merchandise ranking excludes `DOTCOM POSTAGE`, `POSTAGE`, and `Manual` so that selected non-merchandise entries are not ranked alongside physical products. These entries may still be useful for a separate transaction-category analysis.
- Rows with missing `CustomerID` were retained because the main analysis focuses on products, months, countries, and revenue rather than customer-level behavior.
- December 2011 is incomplete because the dataset ends on 9 December 2011.
- Revenue is not profit. The dataset does not provide all costs needed to calculate profit.
- Results depend on the cleaning rules above and should be interpreted in that context.

## Run the Project Locally

### 1. Clone the repository

```bash
git clone <YOUR_REPOSITORY_URL>
cd Data_Analyst_project_1
```

Replace `<YOUR_REPOSITORY_URL>` with the URL of your GitHub repository.

### 2. Create and activate a virtual environment (recommended)

Windows:

```bash
python -m venv .venv
.venv\\Scripts\\activate
```

macOS/Linux:

```bash
python3 -m venv .venv
source .venv/bin/activate
```

### 3. Install dependencies

If the repository contains a `requirements.txt` file:

```bash
pip install -r requirements.txt
```

Typical packages used by this project include:

```bash
pip install pandas numpy matplotlib streamlit jupyter openpyxl
```

### 4. Run the notebook

Open `retail_sales_analysis.ipynb` in Jupyter Notebook or VS Code and run the cells in order. Ensure the source Excel dataset is available at the path expected by the notebook.

### 5. Run the dashboard

```bash
streamlit run app.py
```

Ensure `retail_sales_cleaned.csv` is available at the path expected by `app.py`.

## Repository Structure

A typical project structure is:

```text
Data_Analyst_project_1/
├── app.py
├── retail_sales_analysis.ipynb
├── retail_sales_cleaned.csv
├── requirements.txt
├── README.md
└── .gitignore
```

The exact files may vary depending on what is committed to the repository. Do not commit virtual environments, secrets, or large/raw files unless you have a clear reason and permission to share them.

## What I Learned

Through this project, I practiced:

- Exploring a real-world dataset before analysis.
- Cleaning data using explicit rules and Boolean masks.
- Using Pandas functions such as `groupby()`, `sum()`, `sort_values()`, and `head()`.
- Working with dates using `.dt.to_period("M")`.
- Creating and interpreting revenue visualizations.
- Building and testing a Streamlit dashboard.
- Explaining findings and limitations in business terms.

## Future Improvements

- Add interactive date, country, and product filters.
- Compare sales quantities and revenue side by side.
- Create a separate analysis of postage and other non-merchandise entries.
- Add tests and clearer validation checks for the cleaning workflow.
- Improve dashboard layout and deployment documentation.
- Explore customer-level analysis where appropriate, accounting for missing customer IDs.

## Author

**Vijay Yadav**  
Aspiring Data Analyst

This repository is part of my individual portfolio-building journey. I used learning resources and AI assistance during development; I reviewed and practiced the workflow so I could understand and explain the analysis. The project is intended to demonstrate my learning and ongoing improvement.
