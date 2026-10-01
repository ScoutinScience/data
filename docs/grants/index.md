---
title: Grants
nav_order: 3
has_children: true
has_toc: false
permalink: /grants/
---

# Grants

We collect open grant calls from funding bodies so that projects such as [Matchmaking]({{ "/projects/matchmaking/" | relative_url }}) can pair them with the right researchers and publications. Each funder is a **data intake**: one page per source, describing how we collect its calls and where they land.

## What every grant must have

Whatever the source, each grant we ingest must provide these three features. A source that can't supply all three isn't ready to be ingested.

| Feature | What we store | Why it matters |
|:--|:--|:--|
| **Project title / description** | The call's title and its description text | What the grant is about — the text we match on |
| **Deadline** | The submission deadline | Whether the call is still open, and how urgent it is |
| **Budget** | The funding available | Whether the grant fits the size of the project |

## Sources

{% include entry_list.html group="Grants" %}
