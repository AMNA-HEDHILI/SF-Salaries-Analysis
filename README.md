# San Francisco Public Salaries Analysis

Exploratory data analysis of San Francisco public employee pay: how pay is structured, how it changed over the years, which job groups earn the most, and how unequal it is.

## Goal
Turn raw payroll records into clear answers about typical pay, pay mix, overtime, job categories and inequality, using group-level analysis only.

## Dataset
SF Salaries dataset (public employee pay records over several years), available on Kaggle. The raw file `Salaries.csv` is **not included** in this repository: download it and place it next to the notebook. Individual names are never displayed in the analysis.

## Tools
Python, pandas, NumPy, Matplotlib, Seaborn, SciPy, Jupyter Notebook

## What I did
- **Data quality:** converted "Not Provided" to missing values, checked duplicates, negative pay and zero pay, and missing benefits by year
- **Cleaning:** kept missing pay as missing instead of replacing it with 0, removed empty columns and rows with no pay
- **Job categories:** grouped job titles into broad categories (police, fire, health, transit, engineering and IT, management, other)
- **Pay analysis:** distribution of pay, median vs mean, trend by year, pay mix (base, overtime, other)
- **Overtime:** share of overtime by category, employees with overtime above 50% of base pay
- **Inequality:** share of pay received by the top 1% and top 10%, Gini coefficient
- **Statistical checks:** Spearman correlations and a Mann-Whitney test between the first and last year

## Key findings

- **Data quality:** 148,654 records, 24.3% missing benefits, 369 rows removed (total pay of 0 or less), leaving 148,285 clean records
- **Typical pay:** the median total pay is [see snippet], while the mean is [see snippet], because a small group of very high earners pulls the mean up (the mean is above the median in every year)
- **Over time:** median pay moved from 68,218 in 2011 to 72,414 in 2014 (+6.2%), a statistically significant change (p < 0.001)
- **Jobs:** the highest-paid category is ... and the lowest is ...; at title level, fire battalion chiefs earn the most (median about 220,000-257,000), while the most common titles include many part-time or seasonal roles (e.g. Recreation Leader, median 5,399)
- **Overtime:** Fire and Transit rely most on overtime (17% of their pay each), followed by Police (10%)
- **Inequality:** the top 1% receive 3.1% of all pay (Gini 0.38), and the top 10% receive 23.0%

## Limitations
- Pay records show earnings, not hours worked, seniority, or whether an employee worked part of the year, so low pay may reflect part-time or partial-year work.
- Job categories are built from keywords in job titles, and about 49% of records fall into "Other", so category comparisons cover only part of the workforce.
- Benefits are missing for all of 2011, so comparisons across years use total pay excluding benefits.
- There is no employee ID, so the same person may appear in several years.
- 369 records with total pay of 0 or less were removed; `Notes` and `Status` were too incomplete to use.

## How to run
1. Install the packages: `pip install pandas numpy matplotlib seaborn scipy`
2. Download `Salaries.csv` and put it in the same folder as the notebook
3. Open `SF_Salaries_Analysis.ipynb` and run all cells

## Author
Amna Hedhili: [LinkedIn](https://linkedin.com/in/amna-hedhili-07185a201) | [GitHub](https://github.com/AMNA-HEDHILI)
