---
# ---- Navigation (Just the Docs) ----
layout: entry
title: KVF
parent: Grants
nav_order: 3

# ---- Catalog fields ----
entry_id: kvf
group: Grants
kind: intake
status: active
description: "The Koushal Vikas Foundation offers grants for skill development and empowerment."
location: ""                     # website of the source
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

## About the foundation

The Koushal Vikas Foundation (KVF) funds skill development for individuals and organisations. Its grants support:

+ **Industry skills** — building industry-specific skill sets.
+ **Students and youth** — upgrading latent skills, with programmes to build, upskill and reskill young people.
+ **Research** — academics and technical specialists doing qualitative research and publishing.
+ **Internships** — practical experience for students.
+ **Entrepreneurs** — mentoring for prospective founders.
