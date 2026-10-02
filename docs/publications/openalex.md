---
# ---- Navigation (Just the Docs) ----
layout: entry
title: OpenAlex
parent: Publications
nav_order: 1

# ---- Catalog fields ----
entry_id: openalex
group: Publications
kind: intake
status: active
description: "Open catalogue of scholarly works; the source of our publications."
location: "https://openalex.org"
storage: postgres-db
storage_table: EvaluationProxies

ingestion:
  method: API
  service: openalex-api

projects: [matchmaking]
candidate_projects: []

# Only for data that is missing but should be integrated:
# urgency: high                  # high | medium | low
# target_date: 2026-11-15

open_questions: []
---
