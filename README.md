# Beyond Subsidies: Commercially Viable EV Charging Infrastructure Investment in Australia
Which Australian regions can support profitable EV charging investment without relying on government subsidies?

## Problem Statement
Australian EV subsidies are politically unstable — NSW and South Australia have already ended theirs. Existing infrastructure investment analysis largely assumes subsidy support continues, leaving investors and policymakers with no reliable way to distinguish regions with durable, self-sustaining EV demand from regions that only look viable because of a program that could end at any time.
This project builds that missing view: a region-by-region assessment of commercial viability for EV charging infrastructure, explicitly modelled both with and without ongoing subsidy support.

## Methodology
A two-layer analytical framework applied across 1,358 Australian Statistical Areas (SA2):

**1. Demand forecasting** — An XGBoost regression model forecasts regional EV adoption through 2030 from socioeconomic, geographic, infrastructure, and policy features (R² = 0.86). Two demand scenarios are produced:

- Layer 1 (As-Forecasted) — carries each region's current subsidy status forward
- Layer 2 (Organic-Only) — a counterfactual growth path built from the observed post-subsidy adoption behaviour of states where incentives have already ended (NSW, SA, VIC)

**2. Two-layer DCF with financial sensitivity** — Both demand layers are evaluated under three financial scenarios (optimistic / base / conservative — varying CapEx, discount rate, and utilisation targets), producing six NPV estimates per SA2. These are combined into a two-axis robustness classification that separates demand risk (does growth hold up without subsidy?) from cost risk (does it hold up under conservative financial assumptions?).

**3. Infrastructure gap analysis** — Each SA2's current charging capacity is benchmarked against IEA guidelines (15–25 BEVs per plug) to identify where commercial viability and unmet demand overlap.

## Headline Findings
- 376 of 1,358 SA2s (27.7%) are commercially viable without government subsidy support, across every financial scenario tested
- 152 of those are also currently underserved — the concrete, actionable private-investment target list
- $311.5M in national CapEx would be required to close the existing infrastructure gap to IEA benchmarks
- 711 SA2s (52.4%) are "Mixed" — viability depends on which cost assumptions hold. This is the majority of the dataset and is reported as a finding in its own right, not a minor residual category

## Limitations
This analysis excludes terminal value beyond 2030, applies a single national counterfactual growth path (Layer 2), does not model inflation or electricity price escalation, and uses a flat national revenue-per-vehicle assumption not adjusted for housing density (apartment dwellers rely more heavily on public charging than the model assumes). Full discussion in the notebook's Limitations section.

## Repository Structure

`notebooks/    — full analysis pipeline (data engineering → ML forecast → DCF → classification)`

`data/         — cleaned datasets used for modelling and the dashboard`

`dashboard/    — Power BI dashboard screenshots`

## Dashboard
[Link to interactive Power BI dashboard](https://github.com/Cong-N/EV/blob/main/dashboard/EV_visual%20FINAL.pbix)

## Tech Stack
Python (pandas, XGBoost, geopandas), SQL, Power BI (DAX)

## Author
Cong Nguyen — Bachelor of Business Analytics and Applied Finance, Macquarie University

Quang Nguyen - Bachelor of Commerce, Major in Business Analytics, Macquarie University
