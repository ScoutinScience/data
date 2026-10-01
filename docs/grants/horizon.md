---
# ---- Navigation (Just the Docs) ----
layout: entry
title: Horizon Europe
parent: Grants
nav_order: 2

# ---- Catalog fields ----
entry_id: horizon-europe
group: Grants
kind: intake
status: todo                     # change to active once ingestion runs
description: "The EU's key funding programme for research and innovation; we extract its open calls."
location: "https://research-and-innovation.ec.europa.eu/funding/funding-opportunities/funding-programmes-and-open-calls/horizon-europe_en"
serving: "Postgres — Grants table"

ingestion:
  method: Scraping
  service: scraping-service

projects: [matchmaking]
candidate_projects: []

# The three features every grant source must provide (see the Grants page).
fields:
  - name: "Project title / description"
    type: "Text"
  - name: "Deadline"
    type: "Date"
  - name: "Budget"
    type: "Amount"

open_questions: []
---

## Programme at a glance

Horizon Europe is the EU's main funding programme for research and innovation.

| Aim | In short |
|:--|:--|
| **Global challenges** | Tackles climate change and helps achieve the UN Sustainable Development Goals |
| **Competitiveness** | Boosts the EU's competitiveness, economic growth and industrial competitiveness |
| **EU policy** | Strengthens the impact of research and innovation in developing, supporting and implementing EU policies |
| **Knowledge** | Supports the creation and wider diffusion of excellent knowledge and technologies |
| **Talent and jobs** | Creates jobs and fully engages the EU's talent pool |
| **Investment** | Optimises investment impact within a strengthened European Research Area |
