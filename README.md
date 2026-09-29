# AdventureWorks Sales Performance Dashboard | Power BI

Interactive Power BI dashboard analyzing AdventureWorks' sales and profitability across its two sales channels (Internet vs. Reseller), FY2017–FY2019, to help management understand where revenue comes from and — more importantly — where it's actually profitable.

<img width="100%" alt="image" src="https://github.com/user-attachments/assets/a85514ab-fdd4-4483-b4cd-3bd3e75f0790" />

## Business Objective
This dashboard answers three questions for management:
- How did sales and profit trend across fiscal years?
- Which channel — Internet (direct-to-consumer) or Reseller (wholesale) — is actually more profitable?
- Which products, countries, and customers drive the business?

## Dataset
- **Source:** Microsoft AdventureWorksDW2020 sample data, via [pbi-tools/adventureworksdw2020-pbix](https://github.com/pbi-tools/adventureworksdw2020-pbix)
- **Period:** FY2017–FY2019 (fiscal year, where FY17 = Jul 2017–Jun 2018)
- **Scope:** 7 tables (Sales fact + Product, Customer, Reseller, Sales Territory, Sales Order, Date dimensions), 121.3K sales order lines, 31.5K distinct orders

## Headline Numbers
| Total Sales | Total Profit | Avg. Order Value | Total Orders |
|---|---|---|---|
| $109.8M | $12.6M | $3.5K | 31.5K |

## Key Insights

1. **Reseller drives volume, not profit.** The channel generates 73% of 
   revenue ($80.5M) but only 4% of total profit ($0.5M) — a 0.6% margin, 
   compared to 41.2% for Internet Sales. This isn't from an explicit 
   discount line (none exists in the fact table) — it's that product cost 
   runs close to the reseller sell price. This may be a deliberate trade-off: 
   sacrificing reseller margin to gain market reach, effectively subsidized 
   by the higher-margin Internet channel.

   | Channel | Sales | Profit | Margin |
   |---|---|---|---|
   | Reseller | $80.5M (73%) | $0.5M | 0.6% |
   | Internet | $29.4M (27%) | $12.1M | 41.2% |

2. **Steady, accelerating growth.** Sales grew from $23.9M (FY17) to 
   $34.1M (FY18, +43%) to $51.9M (FY19, +52%).

3. **Bikes dominate the portfolio.** 86% of sales come from a single 
   category, with Components a distant second (10.75%) — a concentration 
   that carries supply and pricing-sensitivity risk.

4. **The US is the core market**, generating $63.0M — over 4x Canada, 
   the next-largest market.

**Recommendation:** validate whether the Reseller margin trade-off is 
intentional (a market-reach strategy) or a pricing gap worth closing — 
and if it's the latter, revisit reseller pricing/cost allocation.

## Dashboard Features
- Date, country/region, and channel (Internet/Reseller) filters with cross-filtering across all visuals
- KPI cards, sales trend by fiscal year, category mix, channel performance comparison, country × category matrix, Top 10 customers (unified across both channels)

## Tools & Skills
- Power BI Desktop
- Power Query
- DAX (CALCULATE, RANKX, RELATED, DISTINCTCOUNT, custom fiscal year logic)
- Data modeling (star schema, relationship management)

## Technical Notes
- Three different "geography" paths exist in the model (Customer, Reseller, Sales Territory) — only Sales Territory covers all sales, so country totals are built from that table to reconcile with the $109.8M grand total.
- Order counts use distinct order number, not order line key, to avoid understating Average Order Value.
- Built a unified "Customer Name" column (Online Buyer + Reseller) so Top 10 Customers reflects the whole business, not just online buyers.

## Repository
`Adventure_Works_Sales_Dashboard.pbix`: open with Power BI Desktop

## Contact
Ms. Trinh (Duong) · Email: trinhduongngoc2301@gmail.com


