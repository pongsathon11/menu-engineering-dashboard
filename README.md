# 🍽️ Menu Engineering & Waste Reduction System

An interactive restaurant analytics web app that helps identify which menu items to push, rework, or remove — and where food waste is eating into profit.

**Live demo:** _add your Vercel URL here_

## Features

**Dashboard** — 30-day KPIs (revenue, dishes sold, gross profit/contribution margin, waste value) with daily trend, category breakdown, and best/worst sellers.

**Menu Engineering Matrix** — classifies every menu item by Popularity × Profitability into Star / Plow Horse / Puzzle / Dog with an actionable recommendation per item, visualized as an interactive bubble chart.

**Basket Pairing** — market-basket analysis (support, confidence, lift) to surface items frequently ordered together, with suggested combo sets and pricing. Bills are simulated from daily sales with a fixed seed since the demo dataset has no bill-level data; a production version would consume POS transactions directly.

**Waste Analysis** — waste value by menu, by cause, and by day; flags items whose waste exceeds 3% of their revenue.

**Scenario Simulator** — adjust price, raw cost, waste % or expected sales for any item and instantly see the impact on contribution margin, margin %, 30-day profit, and matrix classification.

**Web Database (CRUD)** — add, edit, and delete menus, sales logs and waste logs with search, sorting and pagination. Deleting a menu cascades to its logs. Data persists in the browser (localStorage) with JSON export/import and one-click demo reset.

## Tech

- Single-file HTML/CSS/JavaScript — no framework, no build step, no backend
- Chart.js for visualizations
- Bilingual UI (Thai / English toggle)
- Demo dataset: 15 menu items, 450 daily sales records, 78 waste records (30 days)

## Analytics methodology

- Real cost = raw cost × (1 + waste %); CM = price − real cost
- Popularity score = item qty ÷ average qty; Profitability score = item CM ÷ average CM (threshold 1.0)
- Pair metrics: support = P(A∧B), confidence = P(B|A), lift = P(A∧B) ÷ P(A)P(B)

## Run locally

Open `index.html` in a browser. That's it.

---

Built by **Pongsatthon** — Data Analyst (statistics background, Chulalongkorn University).
