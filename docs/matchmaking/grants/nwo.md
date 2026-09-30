---
# ---- Navigation (Just the Docs) ----
layout: entry
title: NWO
parent: Grants
grand_parent: Matchmaking
nav_order: 2

# ---- Catalog fields ----
entry_id: nwo-grants-store
group: Grants
kind: intake                     # shown as "Data intake" (labels in _data/catalog.yml)
method: API                      # how we collect it: API, scraper, manual, ...
status: active
description: "NWO provides a limited palette of funding lines; we extract the calls for each of their distinct objectives."
location: "https://www.nwo.nl/en"
serving: "Postgres — Grants table"

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

## Funding lines at a glance

NWO harmonises its funding instruments so that researchers in every domain work under the same conditions as far as possible. It offers a small set of funding lines, each with one objective, built from modules that are combined per programme or call.

| # | Funding line | Objective | Programmes |
|:--|:--|:--|:--|
| 1 | **Open Competition** | Curiosity-driven research on a subject of the researcher's own choice, with no thematic conditions | [Science](https://www.nwo.nl/en/researchprogrammes/open-competition-enw) · [SSH](https://www.nwo.nl/en/researchprogrammes/open-competition-ssh) · [AES](https://www.nwo.nl/en/researchprogrammes/open-technology-programme) · [ZonMw](https://www.zonmw.nl/nl/onderzoek-resultaten/fundamenteel-onderzoek/programmas/programma-detail/zonmw-open-competitie/) |
| 2 | **Talent Programme** | Personal funding for individual researchers at different career stages | [Veni / Vidi / Vici](https://www.nwo.nl/en/researchprogrammes/nwo-talent-programme) · [Rubicon](https://www.nwo.nl/en/researchprogrammes/rubicon) |
| 3 | **Collaboration with knowledge users and society** | Thematic research and valorisation with public and/or private partners, to speed up economic or social impact; includes international and European thematic calls | [KIC](https://www.nwo.nl/en/researchprogrammes/knowledge-and-innovation-covenant) · [NWA](https://www.nwo.nl/en/researchprogrammes/dutch-research-agenda-nwa) · [NGF](https://www.nwo.nl/en/researchprogrammes/national-growth-fund) · [International](https://www.nwo.nl/en/researchprogrammes/international-programmes) |
| 4 | **Practice-oriented research** | Professionalisation and quality of practice-oriented research at universities of applied sciences | [Taskforce SIA](https://www.nwo.nl/en/taskforce-for-applied-research-sia) |
| 5 | **Infrastructure** | High-quality scientific infrastructure: specialised equipment, data collections and digital infrastructure | — |
| 6 | **Innovation Accelerator** | Turning research results into services and products, through grants, training and loans | — |
