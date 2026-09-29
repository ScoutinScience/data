---
# ---- Navigation (Just the Docs) ----
layout: entry
title: Example data store
parent: Grants
grand_parent: Matchmaking
nav_order: 2

# ---- Catalog fields ----
entry_id: grants-example-store
group: Grants
kind: store
status: store
description: "What this table / topic / index holds."
location: "Postgres — table name"
serving: "Platform database"

# Columns and which entries write them.
# "Written by" / "Read by" under Interactions are filled in automatically
# from other entries' outputs.to and inputs.from.
fields:
  - name: "Column name"
    type: "Type"
    written_by: [grants-example-model]

open_questions: []
---
