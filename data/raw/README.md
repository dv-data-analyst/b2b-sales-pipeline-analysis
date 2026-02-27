# Data

## Source
Maven Analytics — CRM Sales Opportunities (Data Playground)
Dataset page: https://mavenanalytics.io/data-playground/crm-sales-opportunities

Original source listed on dataset page: data.world
License listed on dataset page: Public Domain
Downloaded: Feb 2026

## Files
| File | Description |
|------|-------------|
| sales_pipeline.csv | 8,800 CRM opportunities (core analysis file) |
| accounts.csv | Company-level account details |
| products.csv | Product catalog with `sales_price` |
| sales_teams.csv | Rep-to-manager-to-region mapping |
| data_dictionary.csv | Field definitions for all files |

## Key Fields Used in Analysis
| Field | Description |
|-------|-------------|
| deal_stage | Won / Lost / Engaging / Prospecting |
| product | Product name — note: "GTXPro" in pipeline vs "GTX Pro" in products. Name inconsistency handled in notebook via normalized join key. |
| sales_agent | Rep name, used to join with sales_teams.csv |
| close_value | Deal value in USD for Won deals (0 for Lost) |
| sales_price | List price proxy used to estimate lost revenue for Lost deals |
| engage_date | Date rep first engaged the opportunity |
| close_date | Date deal was marked Won or Lost |

## Data Quality Note
Product names differ between sales_pipeline.csv and products.csv. Handled
in notebook Section 1 by creating a normalized key before joining. Without
this fix, GTXPro ($2.0M estimated lost revenue) would be excluded from
product-level analysis.

Dataset license: Public Domain (per source). Code in this repository: MIT License.
