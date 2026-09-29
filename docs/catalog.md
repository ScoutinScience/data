---
title: Catalog
nav_order: 2
---

# Catalog
{: .fs-8 }

Every documented model, service and data store — what it runs on, what goes in, what it writes, and what reads that afterwards. Pick one to open its page, then follow the links.
{: .fs-5 .fw-300 }

{%- assign _all = site.pages | where_exp: "p", "p.entry_id != nil" -%}
{%- assign _stores = _all | where: "kind", "store" -%}
{%- assign _links = 0 -%}{%- assign _blockers = 0 -%}{%- assign _todo = 0 -%}
{%- for e in _all -%}
  {%- for o in e.outputs -%}{%- assign _links = _links | plus: o.to.size -%}{%- endfor -%}
  {%- for q in e.open_questions -%}{%- if q.level == "blocker" -%}{%- assign _blockers = _blockers | plus: 1 -%}{%- endif -%}{%- endfor -%}
  {%- if e.status == nil or e.status == "todo" -%}{%- assign _todo = _todo | plus: 1 -%}{%- endif -%}
{%- endfor %}

<div class="sis-tally">
  <span><b>{{ _all.size | minus: _stores.size }}</b> models &amp; services</span>
  <span><b>{{ _stores.size }}</b> stores</span>
  <span><b>{{ _links }}</b> recorded links</span>
  <span><b>{{ _todo }}</b> to document</span>
  <span class="bad"><b>{{ _blockers }}</b> blockers</span>
</div>

{% include entry_list.html filter=true %}
