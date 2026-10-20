<div align="center">

# 🍫 Chocolate Factory Sales Analysis

### Sales performance analysis for a chocolate manufacturing business turning raw chocolate sales data into clear, actionable business insight

<br>

![Power BI](https://img.shields.io/badge/Power%20BI-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)
![DAX](https://img.shields.io/badge/DAX-Measures-0078D4?style=for-the-badge)
![Power Query](https://img.shields.io/badge/Power%20Query-ETL-217346?style=for-the-badge)
![GitHub](https://img.shields.io/badge/GitHub-Repository-181717?style=for-the-badge&logo=github&logoColor=white)

</div>

<br>

---

## 📖 Description

The **Chocolate Factory Sales Analysis** dashboard was built to evaluate sales performance across a chocolate manufacturing company. Using a dataset of **300 sales transactions** covering **22 products**, **6 countries**, and **10 sales representatives**, the report brings revenue, cost, and profit data together into a single, interactive view.

The dashboard is designed to answer the questions decision-makers care about most: which products generate the highest revenue, which countries perform best, which salespeople drive the most sales, and which products deliver the strongest profit margins. It also highlights loss-making transactions, helping stakeholders spot pricing or data issues and identify products that may need review.

Beyond its business value, this project demonstrates practical, end-to-end **Power BI skills for data analytics**, from cleaning and transforming raw data in Power Query, to building a star schema data model, to writing DAX measures and designing an intuitive, business-focused report.

<br>

---

## 📸 Dashboard Preview

<div align="center">

![Dashboard](https://github.com/user-attachments/assets/1062add2-d3b5-48be-858a-bcb4ec271116)

</div>

<br>

---

## 🗃️ Dataset Overview

| Column | Description |
|:--|:--|
| **Sales Person** | Sales representative responsible for the transaction |
| **Geography** | Country where the sale took place |
| **Product** | Chocolate product sold |
| **Amount** | Sales revenue for the transaction |
| **Units** | Quantity of units sold |
| **Cost Per Unit** | Production cost for one unit of the product |
| **Cost** | Total cost (Units × Cost Per Unit) |
| **Profit** | Amount minus Cost |

**Scope:** 300 transactions • 22 products • 6 countries • 10 salespeople

<div align="center">

![Excel Pivot Analysis](<img width="738" height="273" alt="Screenshot 2026-10-20 at 21 20 40" src="https://github.com/user-attachments/assets/ac714757-a988-4d0a-b8d0-d1a20a7f0b81" />)

*Initial exploration of the sales data in Excel using pivot tables*

</div>
<br>

---

## ⚙️ Installation

Follow these steps to explore the dashboard locally:

**1. Clone the repository**

```bash
git clone https://github.com/<your-username>/Chocolate-Sales-Analysis.git
```

**2. Open the report**

Open `Dashboard/Chocolate Sales Analysis.pbix` using **Microsoft Power BI Desktop** (free to download from Microsoft).

**3. Refresh the data (if required)**

If prompted, update the data source path to point to `Data/Chocolate Sales Dataset.xlsx`, then click **Refresh** on the Home ribbon.

<br>

---

## 🛠️ Tools Used

- **Microsoft Power BI** – report building and visualization
- **Power Query** – data cleaning and transformation (ETL)
- **DAX** – calculated measures, columns, and dynamic KPIs
- **Data Modeling** – star schema design and table relationships
- **Microsoft Excel** – source dataset and initial preparation

<br>

---
## 🔄 Data Preparation

The raw data was cleaned in **Power Query** before analysis:

- Removed unused columns and blank rows from the source sheet
- Trimmed text columns to remove stray spaces
- Set correct data types for text, whole number, and decimal columns
- Renamed columns for clarity (e.g. **Total Profit** → **Profit**) to avoid conflicts with DAX measure names
- Confirmed the final table contained all **300** transactions

<div align="center">

![Power Query Steps](PASTE-THE-LINK-HERE)

*Data cleaning steps applied in Power Query*

</div>

<br>

---

## 🧩 Data Model

The flat source table was restructured into a **star schema**:

- **Fact table:** `Sales`, containing every transaction with its amounts, units, cost, and profit
- **Dimension tables:** `Products`, `Salespeople`, and `Countries`, each built in Power Query by referencing the Sales table and removing duplicates

Each dimension has a **one-to-many** relationship with the Sales table. All slicers and chart categories use the dimension tables, so filters flow consistently across the whole report.

<div align="center">

![Star Schema Data Model](PASTE-THE-LINK-HERE)

*Star schema in Power BI Model view: Sales fact table with Products, Salespeople, and Countries dimensions*

</div>

<br>

---

## 🧮 DAX Measures

| Measure | Formula | Purpose |
|:--|:--|:--|
| **Total Revenue** | `SUM(Sales[Amount])` | Total sales value |
| **Total Cost** | `SUM(Sales[Cost])` | Total production cost of goods sold |
| **Total Profit** | `SUM(Sales[Profit])` | Revenue remaining after costs |
| **Profit Margin** | `DIVIDE([Total Profit], [Total Revenue])` | Profit as a share of revenue |
| **Units Sold** | `SUM(Sales[Units])` | Total sales volume |
| **Total Transactions** | `COUNTROWS(Sales)` | Number of sales |
| **Avg Transaction Value** | `DIVIDE([Total Revenue], [Total Transactions])` | Average value per sale |
| **Loss-Making Transactions** | `CALCULATE(COUNTROWS(Sales), Sales[Profit] < 0)` | Number of sales where cost exceeded revenue |

`DIVIDE` is used instead of `/` so that calculations return blank rather than an error when a filter leaves no revenue.

<br>

---
## ✨ Dashboard Features

| Feature | Description |
|:--|:--|
| **KPI Cards** | At-a-glance view of revenue, profit, margin, units, and transactions |
| **Slicers** | Filter the entire report by product, country, and salesperson |
| **Filters** | Page- and visual-level filters for focused analysis |
| **Interactive Charts** | Cross-highlighting visuals that respond to user selections |
| **Drill-through** | Navigate from summary views into detailed product or salesperson pages |
| **Tooltips** | Custom tooltips revealing extra context on hover |
| **Dynamic Measures** | KPIs that update instantly based on the selected filter context |
| **Maps** | Geographic view of sales performance across the six markets |
| **Loss Analysis** | Identification of transactions where cost exceeded revenue |

<br>

---

## ❓ Business Questions Answered

1. What are the **total sales** for the business?
2. What is the **total profit** generated?
3. Which **chocolate products** generate the most revenue?
4. Which **salesperson** generates the highest revenue?
5. Which **countries** contribute the most sales?
6. Which products have the **highest and lowest profit margins**?
7. Which **salesperson performs best in each country**?
8. Which transactions are **loss-making**, and why?

<br>

---

## 📌 Key KPIs

| KPI | Value |
|:--|:--|
| **Total Revenue** | 1,240,869 |
| **Total Profit** | 801,165 |
| **Profit Margin** | 64.6% |
| **Units Sold** | 45,660 |
| **Total Transactions** | 300 |
| **Average Transaction Value** | 4,136 |

<br>

---

## 💡 Key Insights

- **Top product by revenue:** *Caramel Stuffed Bars* generated the highest revenue (72,373), closely followed by *Choco Coated Almonds* and *Baker's Choco Chips*.
- **Most profitable product:** *Baker's Choco Chips* delivered the highest total profit (58,278), while *Eclairs* achieved the strongest margin at 88.6%.
- **Margin concern:** *Organic Choco Syrup* ranks 4th in revenue but has the lowest margin (28.2%), making it a candidate for pricing or cost review.
- **Top market:** *India* led all countries in revenue (252,469), with *Canada* close behind and achieving the highest margin (71.3%).
- **Volume vs. value:** The *USA* sold the most units (10,158) but had the lowest margin (43.4%), suggesting a lower-value product mix or pricing pressure.
- **Top salesperson:** *Gigi Bohling* generated the highest revenue (165,725) and the strongest margin (81.6%) of the sales team.
- **Loss-making sales:** 63 of 300 transactions (21%) recorded a negative profit, highlighting potential pricing, discounting, or data-entry issues worth investigating.

<br>

---
## 🔍 Data Quality Notes

During validation, some transactions appeared to contain data-entry errors:

- One sale recorded **150 units of 70% Dark Bites for a total of 42**, about 0.28 per unit against a production cost of 14.49 per unit. The same salesperson's other sales of this product were priced at roughly 38–44 per unit.
- One transaction recorded **0 units** while still showing a sales amount.

A **Price Per Unit** calculated column was added to compare pricing across transactions and identify outliers like these. Because the correct values could not be confirmed, these rows were kept in the analysis but flagged. Some of the loss-making transactions may therefore reflect data errors rather than genuine losses.

<br>

---
## 🧠 Project Learnings

- Built a fully **interactive Power BI dashboard** from raw sales data.
- **Cleaned and transformed** raw data using Power Query, handling data types and formatting issues.
- Created **relationships between multiple tables** to enable accurate cross-filtering.
- Designed a **star schema data model** with fact and dimension tables for performance and clarity.
- Wrote **DAX measures and calculated columns** for revenue, profit, margin, and cost analysis.
- Built **dynamic KPIs** that respond to user selections in real time.
- Implemented **slicers and drill-through pages** for flexible, layered analysis.
- Identified **data anomalies and loss-making transactions** to support data quality and pricing decisions.
- Designed a **business-focused dashboard layout** centered on stakeholder needs.
- Generated **insights to support data-driven business decisions**.

<br>

---

## 🎯 Skills Demonstrated

<div align="center">

| | | |
|:--:|:--:|:--:|
| Data Cleaning | Data Transformation | Data Modeling |
| DAX | Power BI | Business Intelligence |
| Dashboard Design | Data Visualization | Analytical Thinking |

</div>

<br>

---

## 📂 Repository Structure

```
Chocolate-Sales-Analysis/
│
├── Data/
│   └── Chocolate Sales Dataset.xlsx
│
├── Dashboard/
│   └── Chocolate Sales Analysis.pbix
│
├── Images/
│   └── dashboard.png
│
├── README.md
└── LICENSE
```

<br>

---

## 🚀 Future Improvements

- **Time-Based Analysis** – add transaction dates to unlock monthly trends and seasonality
- **Sales Forecasting** – predict future revenue once time-series data is available
- **Customer Segmentation** – incorporate customer data to identify high-value segments
- **Inventory Analysis** – connect stock data to track supply against demand
- **AI Insights** – use Key Influencers and Q&A visuals for automated analysis
- **Automated Refresh** – schedule refreshes through the Power BI Service

<br>

---

## 🏁 Conclusion

The **Chocolate Factory Sales Analysis** project demonstrates end-to-end business intelligence skills, from preparing and modeling raw data to delivering a polished, interactive report. By transforming 300 raw sales records into clear KPIs, product and market comparisons, and profitability insights, the dashboard gives stakeholders the actionable information they need to make confident, data-driven decisions about products, markets, and sales strategy.

<br>

---

## 📜 License

This project is licensed under the terms of the [LICENSE](LICENSE) file in this repository.

<br>

---

<div align="center">

### If you found this project useful, consider giving it a star!

**Built with Power BI**

[GitHub](https://github.com/aleeza1530) • [LinkedIn](https://www.linkedin.com/in/aleeza-tahir-tech)

</div>
