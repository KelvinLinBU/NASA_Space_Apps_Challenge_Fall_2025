# Water-Sanitation Compass

A simple, reproducible workflow that turns country data on **water access**, **sanitation access**, **child mortality**, and **population** into **ranked priorities** and **costed 12-month action briefs**.

## What it does
- Scores countries with a transparent **Need Score (0–1)**.
- Uses **unsupervised clustering** to group similar contexts.
- Converts percentage gaps into **people reached** and into **asset counts** (standpipes, household connections, basic toilets, handwashing stations, desludging trips).
- Estimates **rough costs**, assigns owners, timelines, and KPIs.
- Auto-generates **CSV tables** and **markdown briefs** per country.

## How it works (short)
1. Load cleaned indicators (2010–2022): water, sanitation, child mortality.
2. Engineer features: latest, mean, trend, variability, percent change.
3. Pull **population and urban share** (OWID) to size improvements.
4. Cluster with **UMAP + DBSCAN** or **KMeans**; compute Need Score.
5. Translate gaps → people → assets → **12-month budgets**.
6. Write results to CSVs and one-page markdown briefs.

## Why it matters
This moves from **maps to delivery** by producing **realistic, fundable** actions that can improve access, protect health, and reduce child mortality in fast-growing cities.

## Key outputs (in `datasets/`)
- `wash_need_ranked.csv` – Countries ranked by Need Score and policy bucket.
- `wash_plan_12m_quantified.csv` – Counts and costs of assets to deliver in 12 months.
- `policy_book_WASH.csv` – Clean table for slides and dashboards.
- `briefs/*.md` – One-page country action briefs.

## Quick start
- pip install -r requirements.txt
- Run the notebook cells in order. Adjust parameters in the planning section if needed
  (targets, feasible annual gains, unit costs, delivery mix).

## Data sources
- **NASA SEDAC/CIESIN**: Natural Resource Protection and Child Health Indicators (2010–2022).
- **Our World in Data**: Population and urban share (latest available).

*Replace unit costs and service ratios with local values for best results.*
