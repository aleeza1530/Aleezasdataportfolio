<div align="center">

# 🍫 Chocolate Factory Sales Analysis

### Sales performance analysis for a chocolate manufacturing business turning raw chocolate sales data into clear, actionable business insight

<br>

![Power BI](https://img.shields.io/badge/Power%20BI-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)
![DAX](https://img.shields.io/badge/DAX-Measures-0078D4?style=for-the-badge)
![Power Query](https://img.shields.io/badge/Power%20Query-ETL-217346?style=for-the-badge)
![GitHub](https://img.shields.io/badge/GitHub-Repository-181717?style=for-the-badge&logo=github&logoColor=white)
![Markdown](https://img.shields.io/badge/Markdown-Docs-000000?style=for-the-badge&logo=markdown&logoColor=white)

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

![Dashboard](Images/dashboard.png)

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
| **Total Profit** | Amount minus Cost |

**Scope:** 300 transactions • 22 products • 6 countries • 10 salespeople

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
- **Microsoft Excel** – source dataset storage and preparation

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

[GitHub](https://github.com/<your-username>) • [LinkedIn](https://linkedin.com/in/<your-profile>)

</div>
