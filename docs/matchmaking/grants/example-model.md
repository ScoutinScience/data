---
# ---- Navigation (Just the Docs) ----
layout: entry
title: Example model              # must be unique across the site
parent: Grants
grand_parent: Matchmaking
nav_order: 1

# ---- Catalog fields ----
entry_id: grants-example-model   # unique id other entries use to link here
group: Grants                    # heading this entry sits under in the catalog
kind: model                      # model | service | library | store
status: todo                     # ok | warn | stop | todo  (see _data/catalog.yml)
description: "What this is and how it works, in one or two sentences."
location: "path/to/code"         # repo path
serving: "How it is served (endpoint, port, job) — or None"
version: ""                      # optional: env var / model version pin
owner: ""                        # optional

inputs:
  - name: "Input name"
    form: "Type / shape"
    from: [grants-example-store]  # entry_ids this input comes from (optional)

outputs:
  - name: "Output name"
    note: "Optional note"
    to: [grants-example-store]    # entry_ids this output is written to; leave empty if not persisted

open_questions:
  - level: open                   # open | blocker
    text: "An open question about this entry."
---

Free-form notes go here (Markdown). Delete this line if you don't need it.
