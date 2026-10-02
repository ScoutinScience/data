---
# ---- Navigation (Just the Docs) ----
layout: entry
title: ALS Association
parent: Grants
nav_order: 4

# ---- Catalog fields ----
entry_id: als
group: Grants
kind: intake
status: active
description: "Research funding across the stages of ALS research, from basic science to early-phase clinical trials."
location: "https://www.als.org"
storage: postgres-db
storage_table: Grants

ingestion:
  method: Scraping
  service: scraping-service

projects: [matchmaking]
candidate_projects: []

# Only for data that is missing but should be integrated:
# urgency: high                  # high | medium | low
# target_date: 2026-11-15

open_questions: []
---
