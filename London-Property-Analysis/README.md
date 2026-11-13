# Terraced Houses in Three Outer Boroughs Outperformed London's 5% Fall as Flats Dropped 9%

Between 2022 and 2026, terraced house prices rose in Waltham Forest (+9%) and Redbridge (+2%) and fell only slightly in Bromley (−1%), all outperforming London's 5% terraced fall.

![Power BI](https://img.shields.io/badge/Power%20BI-F2C811?style=for-the-badge&logo=powerbi&logoColor=black) ![DAX](https://img.shields.io/badge/DAX-Measures-0078D4?style=for-the-badge) ![Power Query](https://img.shields.io/badge/Power%20Query-ETL-217346?style=for-the-badge)

---

## Description

This project analyses London property sales for John, a property investor with a £400,000–£500,000 budget who wants to buy where values are rising.

- **Within budget, Redbridge led:** Redbridge had the largest increase within John's budget (+3.4%), while London's median price fell 5%.
- **Fastest growth, but over budget:** Waltham Forest's overall median price grew the most of the three boroughs (+7.2%, £485k → £520k), but its 2026 median is about £20k above John's budget.
- **Affordable, but falling:** in 2026, the median flat price was under £400k in all three boroughs, below John's budget, but flats fell in value in each of them, and by 9% across London.
- **Flats are almost all leasehold:** only about 1% of flats were sold freehold, compared with 94–98% of terraced houses. For John, who wants to avoid leasehold, that means choosing between an affordable leasehold flat and a freehold terraced house above his budget.
- **The analysis behind it:** 373,110 terraced house and flat sales across London's 33 boroughs from 2022 to 2026, combined from HM Land Registry yearly files, cleaned in Power Query, modelled as a star schema, and measured with DAX in an interactive Power BI dashboard.

---

## Dashboard Preview

PASTE DASHBOARD SCREENSHOT HERE

**Median Price by Year and District:** **Conclusion:** Waltham Forest had the strongest growth of the three boroughs (+7.2%), but its 2026 median of £520k is about £20k above John's £500k budget. Redbridge is the strongest option within budget (+3.4%, with a 2026 median of £450k), although its prices dipped in 2023 and 2024 before recovering. John needs to decide whether Waltham Forest's stronger growth is worth stretching his budget, or whether Redbridge's lower price outweighs its slower, less steady growth.

**% Freehold:** **Conclusion:** John would prefer a freehold property, and 94–98% of terraced houses in all three boroughs were sold freehold, compared with only about 1% of flats. But typical terraced houses are above his budget: even Bromley, the cheapest, has a 2026 terraced median of about £510k, and its terraced prices fell slightly (−1%). So John has to choose between a freehold terraced house above his budget, or an affordable flat that's almost certainly leasehold.

**% Increase by District and Property Type:** **Conclusion:** Terraced houses outperformed flats in all three boroughs. Waltham Forest's terraced prices grew the most (+9%), followed by Redbridge (+2%), while Bromley's fell slightly (−1%). Flats fell in all three. For John, terraced houses offer stronger growth, but Waltham Forest's typical terraced house is well above his budget, which makes Redbridge the more realistic choice.

---

## Dataset Overview

These are the 7 columns kept for analysis, out of 16 in the original data.

| Column | Description |
|:--|:--|
| **Transaction Unique Identifier** | A unique reference number for each sale |
| **Price** | The price the property sold for, as stated on the transfer deed |
| **Date of Transfer** | The date the sale was completed, as stated on the transfer deed |
| **Property Type** | T = Terraced, F = Flats/Maisonettes (filtered to terraced houses and flats only) |
| **Old/New** | Whether the property was newly built (Y) or an established building (N) |
| **Duration** | The property's tenure: F = Freehold, L = Leasehold. HM Land Registry does not record leases of 7 years or less. |
| **District** | The London borough where the property is located (33, including the City of London) |

**Scope:** 373,110 sales • 33 London boroughs • 2 property types • 2022–2026

**Source:** [HM Land Registry Price Paid Data](https://www.gov.uk/government/statistical-data-sets/price-paid-data-downloads), yearly files for 2022–2026. Released under the Open Government Licence v3.0.

Contains HM Land Registry data © Crown copyright and database right 2021. This data is licensed under the Open Government Licence v3.0.

The raw CSV files are not included in this repository due to their size (115–230 MB each). They can be downloaded from the link above.

---

## Installation

Follow these steps to explore the dashboard locally:

**1. Clone the repository**

```bash
git clone https://github.com/aleeza1530/Aleezasdataportfolio.git
```

**2. Open the report**

Open `London-Property-Analysis/London Property Analysis.pbix` using Microsoft Power BI Desktop (free to download from Microsoft).

**3. Refresh the data (if required)**

The raw data is not included in this repository. To refresh it, download the 2022–2026 yearly CSV files from the source link above, combine them into one CSV, then in Power BI go to **Transform data → Data source settings → Change Source**, select the combined file, and click **Refresh**.

---

## Tools Used

- **Microsoft Power BI** – report building and visualisation
- **Power Query** – data cleaning and transformation (ETL)
- **Windows Command Prompt** – combining the five yearly CSV files into one

## Analysis Used

- **DAX** – calculated measures, columns, and dynamic KPIs
- **Data Modelling** – star schema design and table relationships

---

## Data Preparation

I started with five yearly CSV files from HM Land Registry, covering every property sale in England and Wales from 2022 to 2026: 4,321,643 rows in total, across 16 columns, with no column headings. The data used letter codes for property type, tenure and sale category, included address details, and covered far more than John needed. I prepared it in two stages: combining the files with the Command Prompt, then cleaning them in Power Query.

- **Combined files:** I joined the five yearly CSVs into one file using the Command Prompt, so a single Power Query could load all five years, and my cleaning steps would apply to every year in the same way.
- **Renamed columns:** I renamed all 16 columns using the Land Registry's "About the Price Paid Data" guidance, because the files had no headings, so the columns couldn't be identified without it.
- **Changed the date type:** I set Date of Transfer to the Date type, so it could connect to my Date table and be grouped by year.
- **Filtered dates:** I kept sales from 1 January 2022 onwards, because the stamp duty holiday ended in October 2021, and the rush of sales it caused had pushed prices up, so starting in 2022 gives a fairer picture of the market.
- **Filtered to London:** I filtered County to GREATER LONDON rather than filtering Town/City to "London", because many London addresses use local town names, such as Croydon or Romford, so filtering by Town/City would have removed a large share of London's sales, mostly in the outer boroughs within John's budget.
- **Filtered property type, category and status:** I kept terraced houses and flats only (T and F), because those are the property types John is choosing between; standard sales only (PPD Category A), to exclude repossessions and other unusual sales that could distort typical prices; and removed records marked D, because the Land Registry had flagged them for deletion.
- **Removed columns:** I removed nine columns: Postcode, PAON, SAON, Street, Locality, Town/City, County, PPD Category and Record Status. None were needed for my questions, and County, PPD Category and Record Status had only one value left after filtering. This left seven columns: Transaction ID, Price, Date of Transfer, Property Type, Old/New, Duration and District.
- **Validation:** I confirmed the final Sales table held 373,110 sales, and checked that each year from 2022 to 2026 had its own sales count, so the data covered the full period and had loaded correctly.

PASTE POWER QUERY SCREENSHOT HERE

*Data cleaning steps applied in Power Query*

---

## Data Model

The combined Land Registry data was restructured into a star schema:

- **Fact table:** Sales, where each row is one sale, with its Price, Date of Transfer, Property Type, Old/New, Duration, District and Transaction Unique Identifier
- **Dimension tables:** Boroughs (33 rows), Property Type (2), Duration (2) and Old/New (2), each built in Power Query by referencing Sales and removing duplicates
- **Date table:** created with DAX (`CALENDAR`), with one row for every day from 2022 to 2026, plus a Year column, and marked as a date table

Each dimension has a **one-to-many** relationship with the Sales table, and the Date table connects to Sales through Date of Transfer. All slicers and chart categories use the dimension tables, so filters flow consistently across the whole report.

PASTE MODEL VIEW SCREENSHOT HERE

*Star schema in Power BI Model view*

---

## DAX Measures

| Measure | Formula | Purpose |
|:--|:--|:--|
| **Total Sales** | `COUNTROWS(Sales)` | Number of sales (each row is one sale) |
| **Median Price** | `MEDIAN(Sales[Price])` | Typical sale price, less affected by very expensive sales than an average |
| **Median Price 2022** | `CALCULATE([Median Price], 'Date'[Year] = 2022)` | Median price in 2022, the starting point for growth |
| **Median Price 2025** | `CALCULATE([Median Price], 'Date'[Year] = 2025)` | Median price in 2025, the latest complete year |
| **Median Price 2026** | `CALCULATE([Median Price], 'Date'[Year] = 2026)` | Median price in 2026, the end point for growth (partial year) |
| **% Increase** | `DIVIDE([Median Price 2026] - [Median Price 2022], [Median Price 2022])` | Percentage change in median price from 2022 to 2026 |
| **Freehold Sales** | `CALCULATE([Total Sales], 'Duration'[Duration] = "F")` | Number of sales that were freehold |
| **% Freehold** | `DIVIDE([Freehold Sales], [Total Sales])` | Share of sales that were freehold |
| **London Median Price** | `CALCULATE([Median Price], ALL(Boroughs[District]))` | Median price across all of London, ignoring the borough filter, used as a benchmark |
| **Vs London %** | `DIVIDE([Median Price] - [London Median Price], [London Median Price])` | Whether a borough is cheaper (negative) or more expensive (positive) than London's typical price, as a percentage |

`CALCULATE` changes the filter before calculating (e.g. to one year), `ALL` removes the borough filter so London's figure stays fixed, and `DIVIDE` is used instead of `/` so calculations return blank rather than an error when there are no sales.

---

## Dashboard Features

| Feature | Description |
|:--|:--|
| **KPI Cards** | At-a-glance view of median price 2022, median price 2026, London median price, London % change (2022–2026) and total sales |
| **Property Type Slicer** | Filters the report by flats or terraced houses. The % Increase by District and Property Type and % Freehold charts are set to always show both, so the comparison stays visible. |
| **Visual-Level Filters** | Key charts are focused on the three shortlisted boroughs: Waltham Forest, Redbridge and Bromley |
| **Trend Over Time** | A line chart showing each borough's median price by year, to check whether growth was steady |
| **London Benchmark** | Compares each borough's median price with London's, to show whether it's cheaper or more expensive than typical |
| **Interactive Charts** | Cross-highlighting visuals that respond to user selections |
| **Dynamic Measures** | KPIs and charts that update instantly when the slicer is used |

---

## Key KPIs

*All property types, 2022–2026.*

| KPI | Value |
|:--|:--|
| **Median Price 2022** | £480,000 |
| **Median Price 2026** | £456,000 |
| **London Median Price** | £475,000 |
| **London % Change, 2022–2026** | −5% |
| **Total Sales** | 373,110 |

---

## Total Findings

1. Which London boroughs, where the median price of terraced houses or flats is within £400,000–£500,000, saw the largest percentage increase in median price from 2022 to 2026?
2. How does the percentage increase in median price compare between flats and terraced houses in London's boroughs, from 2022 to 2026?
3. Which London boroughs saw the median price of terraced houses and flats rise every year from 2022 to 2026?
4. What percentage of terraced house and flat sales in each borough were freehold, from 2022 to 2026?
5. How does the median price of terraced houses and flats in each borough compare with the London-wide median price for the same property type?

---

## Data Quality Notes

- **No column headings:** the raw files had no headings, so I used the Land Registry's column descriptions to name each column, so the data could be understood.
- **Records flagged for deletion (D):** the Record Status column marked some records D, which the Land Registry uses for records that shouldn't count, such as duplicates or sales in the wrong category, so I removed them.
- **Town/City was inconsistent for London:** many London addresses use local town names, such as Croydon or Romford, rather than "London", so I filtered by County instead, to keep every London borough.
- **Unusual sales (Category B):** I only kept standard sales, because unusual ones, like repossessions, can be much cheaper or more expensive than typical, which would make the prices less accurate.
- **2026 is incomplete:** the Land Registry notes that recent months are still being added to, and 2026 had fewer sales than earlier years. I kept 2026, as it's needed to measure growth to the present, but treated its figures with caution.

---

## Future Analysis

- **Loaded the monthly update file:** I first loaded the September 2026 monthly update file, which only contains records added, changed or deleted that month: it's an update file, not a full record of sales. I noticed because London had only 31 sales in 2022, which was far too low, and the file contained C and D record codes, a sign it was an update file. Since my analysis compares 2022 with 2026, this would have made my results unreliable. I downloaded the yearly files for 2022–2026, combined them into one file with the Command Prompt, and changed the source of my existing query, so all my cleaning steps and dimension tables were kept. The final table held 373,110 sales. *Lesson: before analysing, check what a dataset actually contains, and whether the row counts make sense for each year.*
- **The Town/City filter:** the Town/City column doesn't always say "London" for London sales (some say Croydon or Romford instead), so filtering by Town/City would have left out many sales, mostly in the outer boroughs within John's budget. I filtered County to GREATER LONDON instead, which covers all 33 boroughs consistently. *Lesson: before filtering, check the column's values, as they may not be as consistent as they look.*
- **Partial year (2026):** 2026 isn't over yet, so the data only runs to around September, and October to December aren't included. Even the months that are included are incomplete, as some sales haven't been registered with the Land Registry yet. As a result, the 2026 figures are based on fewer sales, and may change once the full year is recorded.
- **Complete 2026 data** – re-run the analysis once 2026 is complete, so the 2026 medians and % increase are based on a full year of sales.
- **Inflation-adjusted prices** – add a real-terms price measure to the dashboard, so John can see whether prices actually grew once inflation is taken into account.

---

## Skills Demonstrated

| | | |
|:--|:--|:--|
| Data Cleaning | Data Transformation | Data Modelling |
| DAX | Power BI | Business Intelligence |
| Dashboard Design | Data Visualisation | Analytical Thinking |

---

## Repository Structure

```
London-Property-Analysis/
│
├── London Property Analysis.pbix
└── README.md
```

---

## Conclusion

The London Property Analysis project demonstrates end-to-end business intelligence skills, from preparing and modelling raw data to delivering a polished, interactive report. By transforming 373,110 property sales into clear KPIs, interactive charts and like-for-like comparisons by borough and property type, the dashboard gives a property investor the information he needs to decide where, and what type of property, to buy within his budget.

Flats are affordable: a typical flat costs under £400k in all three boroughs. However, flats fell in value across London (−9%), and are almost all leasehold. Terraced houses performed better and are almost all freehold, but they're above John's budget: about £20–40k over in Redbridge and Bromley, and far more in Waltham Forest. The most realistic option is a terraced house in Redbridge, which grew steadily (+2%) while London's terraced prices fell 5%.

John's decision is whether to stretch his budget by around £40k for a freehold terraced house, or stay within budget with a flat that has been losing value. However, no borough kept pace with inflation (18.4% from 2022 to September 2026, according to the Bank of England inflation calculator), so prices fell in real terms. This analysis also doesn't cover rental income, which may matter as much as price growth for John's investment.
