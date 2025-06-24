# E-commerce-Performance-Dashboard
Power BI dashboard that tracks daily revenue, purchase behavior and user efficiency for an online store.

![Overview](img/overview.gif)

---

## 1. Business Question  
> *“How is revenue trending, what is driving spikes, and are we getting more value from each user?”*

## 2. Data
| File | Rows | Refresh | Notes |
|------|------|---------|-------|
| `ecommerce_sales.csv` | 90 | Manual (demo) | Date, users, purchases, revenue |

### Data transformation
* Removed `$` and `,` from `total_revenue`, cast to decimal.  
* Added **Conversion Rate**, **AOV**, **ARPU**, rolling 30-day average.  
* Created Date dimension for proper YTD / MTD logic.

## 3. Key Metrics
| Metric | Definition |
|--------|------------|
| **Revenue** | Sum of `total_revenue` |
| **Purchases** | Sum of `purchase_events` |
| **Conversion Rate** | Purchases ÷ Unique Users |
| **Average Order Value** | Revenue ÷ Purchases |
| **Revenue Δ vs Prior 7 d** | Week-over-week change |

## 4. Report Pages
1. **Overview** – KPI strip, period buttons, revenue trend (raw & 30-day MA), purchases bars.  
2. **Details** – Ranked revenue days, weekday/month heat-map, scatter (CR × AOV, bubble = users).

## 5. Insights
* Revenue down **\$812** vs prior 7 days, driven by lower traffic (-33 users) more than basket size.  
* Highest single-day revenue: **24 Nov 2020** – Conversion Rate spike to **2.1 %** (+0.9 pp).  
* Fridays drive 35 % of monthly revenue; Sunday is consistently lowest.

## 6. How to Use
* Click **Last 7 D / MTD / YTD** buttons to shift time horizon.  
* Hover the revenue line to read raw vs 30-day-avg values.  
* Drill-through any bar in “Total Revenue by Date” to view raw order table (hidden page).

## 7. Future Work
* Merge marketing-spend to calculate **ROAS**.  
* Prophet forecast for next 30 days revenue (Python notebook included).  
* Anomaly alert in Power BI Service using data-driven alert + Teams webhook.

## 8. Setup
1. Clone repo, open `powerbi/ecommerce_dashboard.pbix`.  
2. Change data source to your local path or set parameter **DATA_DIR**.  
3. Refresh → Publish to your workspace.

---

*Author — [Your Name](https://www.linkedin.com/in/<handle>)*  •  MIT-License
