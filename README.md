# 🛒 ShopSmart Analytics Dashboard

An interactive, single-file **Business Intelligence Dashboard** for e-commerce analytics — built with pure HTML, CSS, and JavaScript. No framework, no build step, no dependencies beyond one CDN script.

---

## 📸 Preview

> **5 tab pages** — Business Overview · Product Analytics · Customers · A/B Test · SQL Queries  
> Dataset: Jan–Dec 2023 · 5,000 transactions · 10,000 customers · $7.06M total revenue

---

## 🗂️ Project Structure

```
shopsmart_analytics_dashboard.html   ← entire project in one file
README.md
```

---

## 🛠️ Technologies Used

| Technology | Version | Purpose |
|---|---|---|
| **HTML5** | — | Semantic structure, `<canvas>` elements, accessible `aria-label` attributes |
| **CSS3** | — | Layout (Grid, Flexbox), CSS custom properties (design tokens), responsive media queries |
| **Vanilla JavaScript** | ES6+ | DOM manipulation, tab routing, dynamic chart initialization, SQL card rendering |
| **Chart.js** | 4.4.1 (CDN) | All data visualizations — line, bar, doughnut, horizontal bar charts |

> No npm, no bundler, no React, no backend. Just open the `.html` file in any browser.

---

## 📊 Charts & Visualizations — 7 Total

All charts are rendered via **Chart.js 4.4.1** loaded from `cdnjs.cloudflare.com`. Charts are lazy-initialized — they only render when their tab is first visited, for performance.

| # | Chart ID | Type | Page | What It Shows |
|---|---|---|---|---|
| 1 | `revenueChart` | Line (filled) | Business Overview | Monthly revenue trend Jan–Dec 2023 |
| 2 | `categoryChart` | Doughnut | Business Overview | Revenue share by product category |
| 3 | `ordersChart` | Bar | Business Overview | Order volume per month |
| 4 | `catBarChart` | Horizontal Bar | Product Analytics | Revenue by category (side-by-side) |
| 5 | `segmentChart` | Doughnut | Customers | Customer segments (Occasional / Regular / VIP) |
| 6 | `distChart` | Bar | Customers | Order value distribution in $ brackets |
| 7 | `abChart` | Bar | A/B Test | Conversion rate: Control vs Variant |

---

## 📑 Dashboard Pages (5 Tabs)

### 1. Business Overview
- **6 KPI cards** — Total Revenue, Total Orders, Avg Order Value, Active Customers, Cancellations, Returns
- Monthly revenue line chart (Jan–Dec 2023)
- Revenue by category donut chart + revenue by region horizontal bar
- Monthly orders bar chart
- Insight box: linear regression formula (R² = 0.978)

### 2. Product Analytics
- **4 KPI cards** — Product count, Top category, Price range, Price-quantity correlation
- Revenue by category horizontal bar chart
- Top 10 products by revenue table (with gold/silver/bronze rank badges)
- Category profit margin comparison bars

### 3. Customers
- **4 KPI cards** — Registered, Active, Churn risk, Avg lifetime value
- Customer segment donut chart (Occasional / Regular / VIP)
- RFM analysis cards (Recency, Frequency, Monetary)
- Order value distribution bar chart with percentile stats

### 4. A/B Test
- **4 KPI cards** — Users tested, Conversion lift (+68%), p-value (<0.0001), Revenue lift (+83%)
- Side-by-side Control vs Variant cards (winner highlighted)
- Conversion rate bar chart
- Full statistical test details (two-proportion z-test, z = 5.89)

### 5. SQL Queries
- Database schema overview (4 tables: `customers`, `products`, `orders`, `order_items`)
- **10 annotated SQL queries** dynamically rendered via JavaScript:
  1. SELECT with WHERE + ORDER BY
  2. Aggregations — SUM, AVG, COUNT by category
  3. GROUP BY — monthly revenue trend
  4. INNER JOIN — orders with product details
  5. Subquery — top 10 customers by lifetime value
  6. CASE — customer segmentation by spend
  7. Window function — ROW_NUMBER for product ranking
  8. Churn identification — customers inactive 60+ days
  9. A/B test analysis — conversion rate by variant
  10. RFM analysis — recency, frequency, monetary per customer

---

## 🎨 Design System

The dashboard uses **CSS custom properties (design tokens)** inherited from the host environment:

| Token | Usage |
|---|---|
| `--color-text-primary / secondary` | Typography |
| `--color-background-primary / secondary` | Surface colors (supports dark mode) |
| `--color-border-tertiary / secondary` | Dividers and card borders |
| `--color-background-info / border-info / text-info` | Insight callout boxes |
| `--font-sans / --font-mono` | Body and code typography |
| `--border-radius-md / lg` | Consistent corner rounding |

Dark mode is auto-detected via `matchMedia('(prefers-color-scheme: dark)')` and adjusts chart grid/text colors accordingly.

---

## 🚀 Getting Started

```bash
# Clone the repo
git clone https://github.com/your-username/shopsmart-analytics-dashboard.git

# Open directly in browser — no install needed
open shopsmart_analytics_dashboard.html
```

Or simply **download the HTML file** and double-click it. That's it.

---

## 📋 Dataset Summary

| Metric | Value |
|---|---|
| Period | Jan – Dec 2023 |
| Total Customers | 10,000 |
| Total Transactions | 5,000 |
| Completed Orders | 4,765 (95.3%) |
| Total Revenue | $7,061,887 |
| Avg Order Value | $1,415 |
| Products | 200 (5 categories × 40 SKUs) |

---

## 📁 External Dependency

```html
<script src="https://cdnjs.cloudflare.com/ajax/libs/Chart.js/4.4.1/chart.umd.js"></script>
```

This is the **only external resource**. For fully offline use, download `chart.umd.js` locally and update the `src` path.

---

## ♿ Accessibility

- `aria-label` attributes on all `<canvas>` elements with text fallbacks
- `<h2 class="sr-only">` page title for screen readers
- Semantic HTML throughout

---

## 📄 License

MIT — free to use, modify, and distribute.
