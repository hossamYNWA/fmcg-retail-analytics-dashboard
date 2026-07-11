# FMCG Retail Analytics Dashboard

An end-to-end Power BI solution for FMCG retail performance — inventory health, sales performance, and category management insights — built on a synthetic dataset modeled after realistic multi-region retail operations.

![Executive Summary](docs/screenshots/01_executive_summary.png)

## Overview

This dashboard simulates the analytics stack a category manager or inventory analyst would use to monitor a multi-region FMCG retail chain: sales trends, stockout risk, inventory turnover, and location performance across 6 UK-style regions and multiple retail channels (hypermarket, discount store, convenience, e-commerce, wholesale/cash & carry).

**Note:** Dataset is fully synthetic/dummy data, generated to reflect realistic FMCG retail patterns (seasonality, ABC classification, near-expiry risk, promotional lift). No real business or client data is used.

**A note on the .pbix file:** the working Power BI file isn't published in this repo to protect the DAX model and build. Full data model documentation, DAX formulas, and screenshots below give a complete picture of the build — happy to walk through the live file directly on request.

## Business Questions Answered

- Which categories and locations drive the most profit, and where is margin leaking?
- What's our inventory health — stockout rate, overstock %, near-expiry exposure?
- Which channels (hypermarket vs. wholesale vs. e-commerce) perform best by margin, not just revenue?
- Where should replenishment priority go, based on ABC classification and lead times?

## Data Model

Star schema with 1 fact table and 4 dimension tables:

![Data Model](docs/data_model.png)

| Table | Type | Grain |
|---|---|---|
| `Fact-bills` | Fact | One row per SKU per transaction/location |
| `Dim-product` | Dimension | Product, category, brand, ABC class, stock thresholds |
| `Dim-location` | Dimension | Store, region, channel, location type |
| `Dim-date` | Dimension | Standard date table (day/week/month/quarter/year) |
| `Dim-supplier` | Dimension | Supplier, payment terms |

## Key DAX Measures

30+ measures covering sales, inventory, and profitability. Highlights:

- `Inventory turnover`, `Inventory Health Summary`, `Overstock items %`, `Near Exp. stock`
- `Gross Margin %`, `Profit %`, `Sales Promo Lift`
- `Average Lead Time (days)`, `Fill Rate %`, `On Time Rate`
- `Best Selling Region`, `Highest Channel by Margin`, `Highest Stockout City`
- 

## Dashboard Pages

| Page | Purpose |
|---|---|
| **Executive Summary** | Top-line KPIs, YoY growth, key influencers on sales (AI visual), category ranking |
| **Inventory Health** | Stockout rate, fill rate, overstock/near-expiry %, ABC-class value distribution |
| **Sales Performance** | Weekly sales trend, channel-level profitability table, seasonal mix |
| **Locations** | Regional trends, channel mix by location type, top stockout cities |

<details>
<summary>Screenshots</summary>

**Inventory Health**
![Inventory Health](docs/screenshots/02_inventory_health.png)

**Sales Performance**
![Sales Performance](docs/screenshots/03_sales_performance.png)

**Locations**
![Locations](docs/screenshots/04_locations.png)

</details>

## Tools Used

- Power BI Desktop (data modeling, DAX, Power Query)
- Star schema design

## About Me

Retail operations professional (12+ years, multi-branch pharmacy chains, Saudi Arabia) transitioning into category management and analytics. Microsoft PL-300 certified. Background in inventory optimization, category performance, and retail KPI design gives this project its domain-specific logic (ABC classification, near-expiry tracking, fill rate) rather than generic template metrics.

[LinkedIn](https://www.linkedin.com/in/hossam-badawy/) · [Other projects](https://github.com/hossamYNWA)

## License

This project uses synthetic data and is shared for portfolio/demonstration purposes.
