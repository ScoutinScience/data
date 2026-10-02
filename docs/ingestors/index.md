---
title: Ingestors
nav_order: 6
has_children: true
has_toc: false
permalink: /ingestors/
---

# Ingestors

The services that bring data into the platform. Each data source links to its ingestor through its **method of ingestion**.

There are two kinds:

+ **[APIs](apis/)** — we call an official API and receive structured data.
+ **[Scrapers](scrapers/)** — we read the source's website and extract the data ourselves.

<div class="sis-tab">APIs</div>
<div class="sis-tab-rule"></div>

{% include entry_list.html group="APIs" %}

<div class="sis-tab">Scrapers</div>
<div class="sis-tab-rule"></div>

{% include entry_list.html group="Scrapers" %}
