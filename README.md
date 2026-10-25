# 🍽️ Menu Engineering & Waste Reduction System

An offline, single-file restaurant analytics web app that tells an owner which menu items to push, reprice, bundle or remove — and where food waste is eating into profit.

**Live demo:** _add your Vercel URL here_ (Pro edition with sample data; imports disabled)

## Features

**Dashboard** — revenue, dishes sold, gross profit (CM), waste value and profit after waste for any date range, with change vs the previous period.

**Menu Engineering Matrix** — Kasavana & Smith method (70% popularity rule + sales-weighted average CM), switchable to a simple-average method; per-category view; bubble chart with quadrant thresholds.

**Action Plan** — ranks every menu by monthly money impact: reprice Plow Horses (with volume-loss assumption), promote/bundle Puzzles, remove or rework Dogs (with customer switch-rate assumption), cut avoidable waste. Includes the suggested price that hits a target food-cost %.

**Basket Pairing** — imports real POS bills (CSV, column mapping, Thai/English headers, Buddhist-era dates, remembered item-name matching) and computes support, confidence and lift; suggests combos anchored on popular items and shows the discount break-even.

**Prep Forecast** — same-weekday moving average over N weeks + service-level buffer (z·σ), 7-day prep sheet, back-tested WAPE vs a naive average, printable for the kitchen.

**Recipes & Costing** — ingredient price list and per-dish recipes; menu cost updates automatically, with a live preview of which menus are hit when an ingredient price changes.

**Waste Analysis** — waste by menu, reason, day and weekday; flags items above a configurable % of revenue.

**Scenario Simulator** — change price/cost/yield loss/expected volume, or simulate removing a menu.

**Data** — CRUD with validation, CSV import/export with templates, JSON backup/restore, settings for currency, categories, waste reasons and thresholds.

## Tech

- Single HTML file, vanilla JavaScript, no build step, no backend — works fully offline (Chart.js 4.4.1 embedded)
- Data stays in the browser (localStorage) with backup reminders
- Responsive (mobile off-canvas navigation), Thai / English UI, print stylesheet
- Sample data: 15 menus · 12 weeks · 7,580 bills · 26 ingredients with recipes

## Methodology

- Real cost = ingredient cost × (1 + prep/yield loss %); CM = price − real cost
- Popular if qty ≥ 70% × (total qty ÷ number of items); profitable if CM ≥ Σ(CM·qty) ÷ Σqty
- Pairs: support = P(A∧B), confidence = P(B|A), lift = P(A∧B) ÷ (P(A)·P(B))
- Forecast: mean of last N same weekdays + z·σ; accuracy = WAPE on the last 7 days

## Run locally

Open `index.html` in a browser. That's it.

---

Built by **Pongsatthon** — Data Analyst (Statistics, Chulalongkorn University).
