# Maryland Spending Analysis: FY2008–FY2026

## Project Overview

This project analyzes Maryland state vendor payment data from Fiscal Year 2008 through Fiscal Year 2026. The goal was to better understand how Maryland’s spending is distributed across agencies, vendors, states, and payment sizes.

Large government spending datasets can be difficult to understand in their raw form. Even though the data contains important information about public spending, it is not immediately clear where most payments go, how spending changes over time, or how much spending stays in-state compared to going out-of-state.

To address this, I cleaned and enriched the dataset using Python, added location data based on vendor ZIP codes, created new fields for analysis, and built an interactive Tableau dashboard.

## Dataset

The main dataset used was the State of Maryland Payments Data from Maryland Open Data.

Dataset summary:

- Fiscal years: 2008–2026
- Payment records: 394,817
- Original columns: 8
- Final columns after enrichment: 18
- Agencies: 145
- Vendors: 60,000+

Original fields included:

- Fiscal Year
- Agency Name
- Vendor Name
- Vendor ZIP
- Amount
- Fiscal Period
- Date
- Category

After cleaning and enrichment, I added fields such as:

- Vendor city
- Vendor state
- Vendor county
- Latitude and longitude
- In-state vs. out-of-state status
- Neighboring state status
- Contract amount bin

## Tools Used

- Python
- pandas
- matplotlib
- seaborn
- Tableau
- Jupyter Notebook
- GitHub

## Data Cleaning Process

The dataset was cleaned in Python using pandas. Main cleaning steps included:

- Standardized column names into snake_case
- Removed extra spaces from text fields
- Converted the amount column from text to numeric
- Converted the date column into datetime format
- Cleaned invalid, missing, and shortened ZIP code values
- Replaced unusable ZIP values with nulls when they could not be confidently corrected

## Data Enrichment

After cleaning the dataset, I merged the Maryland spending data with a ZIP code reference dataset to add geographic fields.

Added fields included:

- City
- State
- County
- Latitude
- Longitude


## Feature Engineering

I created several new fields to make the analysis easier:

### In-State vs. Out-of-State

Vendors were classified as either:

- In State
- Out of State

This made it possible to compare how much spending stayed in Maryland compared to how much went to vendors outside Maryland.

### Neighboring State Status

Vendors were grouped into:

- Maryland
- Neighboring State
- Non-Neighboring State

Neighboring states included Pennsylvania, Delaware, Virginia, West Virginia, and Washington, D.C.

### Contract Amount Bin

Payments were grouped into size ranges:

- Below 1k
- 1k to 10k
- 10k to 100k
- 100k+

This helped show whether most payments were small, medium, or large.


## Visualizations

This project includes visualizations for:

- Total spending by fiscal year
- In-state vs. out-of-state spending
- Top 10 states by total spending
- Top 10 states by number of contracts
- Share of contracts by size

## Tableau Dashboard

An interactive Tableau dashboard was created to make the analysis easier to explore.

The dashboard includes:

- Total spending from FY2008 to FY2026
- Average spending per fiscal year
- Average yearly percent change in spending
- Average transactions per year
- Spending trend over time
- Spending by Maryland county
- In-state vs. out-of-state spending
- Distribution of contract sizes
- Spending by agency

The Tableau packaged workbook file is included in this repository.

You can also view the dashboard on Tableau Public here:
[Maryland Spending Analysis Dashboard](https://public.tableau.com/views/Maryland_Budget_Analysis_Dashboard/Dashboard1?:language=en-US&publish=yes&:sid=&:redirect=auth&:display_count=n&:origin=viz_share_link)


## Files in This Repository

- `MD_spending_analysis.ipynb` — Python notebook used for data cleaning, enrichment, analysis, and chart creation
- `Maryland_Budget_Analysis_Dashboard.twbx` — Tableau packaged workbook for the interactive dashboard
- `Maryland Spending Analysis.pdf` — full written project report
- `Maryland Spending Analysis Presentation.pdf` — presentation slides
- `State_of_Maryland_Yearly_Spending_Overview.csv` — smaller yearly spending summary CSV
- `State_of_Maryland_Payments_Data__FY2008_to_FY2024_20260316.csv.zip` — compressed original Maryland payments dataset
- `State_of_Maryland_Payments_Data_With_Location__FY2008_to_FY2026.csv.zip` — compressed cleaned/enriched dataset with added location fields
- `zip_code_database.csv.zip` — compressed ZIP code reference dataset used for geographic enrichment

### Static Charts

The `Static Charts` folder contains exported PNG charts used in the report and presentation:

- `contract_size_distribution.png` — contract size distribution chart
- `In_vs_out_of_state_spending.png` — in-state vs. out-of-state spending chart
- `States_by_number_of_contracts.png` — top states by number of contracts chart
- `spending_by_year.png` — total spending by fiscal year chart
- `States_by_total_spending.png` — top states by total spending chart

## Data Source

State of Maryland Payments Data, Maryland Open Data.

https://opendata.maryland.gov/Budget/State-of-Maryland-Payments-Data-FY2008-to-FY2024/7syw-q4cy/about_data

ZIP code reference data was used to add location details such as city, state, county, latitude, and longitude.

https://www.unitedstateszipcodes.org/zip-code-database/

## Author

Ryan Eller
