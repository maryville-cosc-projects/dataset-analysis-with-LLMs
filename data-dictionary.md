# sample-sales-data.csv — Data Dictionary

A synthetic weekly retail sales dataset: 4 regions × 4 product categories, weekly from Jan 2024 through Dec 2025.

| Column | Type | Description |
|---|---|---|
| `date` | date | Week start date (every Monday) |
| `region` | text | `North`, `South`, `East`, or `West` — note: a few rows use inconsistent casing on purpose |
| `category` | text | `Electronics`, `Apparel`, `Home & Garden`, or `Sporting Goods` |
| `units_sold` | integer | Units sold that week for that region/category |
| `marketing_spend` | number | Marketing budget spent that week for that region/category ($) |
| `revenue` | number | Total revenue that week for that region/category ($) |
| `customer_satisfaction` | number | Average satisfaction score, 1–5 scale (some rows are missing on purpose) |
| `promo_flag` | 0/1 | Whether a promotion ran that week for that region/category |

This dataset is intentionally a little messy — it's meant to be explored, cleaned, and questioned, not taken at face value. Some things worth looking for as you work through the tutorial: how revenue changes across the year, whether regions are growing at the same rate, whether marketing spend seems related to revenue, and whether anything in the data looks like it might be a data-entry error rather than a real sale.
