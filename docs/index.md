---
title: Home
permalink: /
nav_order: 1
---

<div class="sis-hero">
<h1>ScoutinScience Data</h1>
<p>Where our data comes from, how it gets in, what it becomes, and which projects use it. Data categories are in the menu on the left; projects are in the tabs at the top.</p>
<a class="sis-btn" href="https://github.com/ScoutinScience/data/issues/new?template=new-data-source.yml">Propose a data source</a>
</div>

<div class="sis-tab">How the data connects</div>
{% include flow.html %}

<div class="sis-tab">All entries</div>
<div class="sis-tab-rule"></div>

{%- assign _all = site.pages | where_exp: "p", "p.entry_id != nil" -%}
{%- assign _stores = _all | where: "kind", "store" -%}
{%- assign _intakes = _all | where: "kind", "intake" -%}
{%- assign _urgent = 0 -%}{%- assign _blockers = 0 -%}{%- assign _todo = 0 -%}{%- assign _cand = 0 -%}
{%- for e in _all -%}
  {%- for q in e.open_questions -%}{%- if q.level == "blocker" -%}{%- assign _blockers = _blockers | plus: 1 -%}{%- endif -%}{%- endfor -%}
  {%- if e.status == nil or e.status == "todo" -%}{%- assign _todo = _todo | plus: 1 -%}{%- endif -%}
  {%- if e.status == "candidate" -%}{%- assign _cand = _cand | plus: 1 -%}{%- endif -%}
  {%- if e.urgency -%}{%- assign _urgent = _urgent | plus: 1 -%}{%- endif -%}
{%- endfor %}

<div class="sis-tally">
  <span><b>{{ _intakes.size }}</b> data sources</span>
  <span><b>{{ _all.size | minus: _stores.size | minus: _intakes.size }}</b> services</span>
  <span><b>{{ _stores.size }}</b> stores</span>
  <span><b>{{ _cand }}</b> candidates</span>
  <span><b>{{ _todo }}</b> to document</span>
  <span class="warnc"><b>{{ _urgent }}</b> waiting to be integrated</span>
  <span class="bad"><b>{{ _blockers }}</b> blockers</span>
</div>

{% include entry_list.html filter=true %}

---

To document something new, see [add a data source](pages/adding_entries/adding_entries.html). Stuck? See [help](pages/getting_help/getting_help.html).
