---
title: Adding an entry
nav_order: 8
---

# Adding an entry
{: .no_toc }

1. TOC
{:toc}

Every data source, service or store is **one Markdown file**. Its page, its row in the catalog, its project links and its connections to other entries are all generated from the front matter, so that one file is all you edit.

## 1. Pick the category folder

| Folder | Category |
|:--|:--|
| `docs/grants/` | Grants |
| `docs/publications/` | Publications |
| `docs/patents/` | Patents |
| `docs/theses/` | Theses |
| `docs/services/` | Pipeline services (scrapers, models, APIs that move or process data) |

The quickest start is to copy `docs/grants/nwo.md` and change it.

## 2. Fill in the front matter

| Field | Required | What it is |
|:--|:--|:--|
| `layout` | yes | Always `entry` |
| `title` | yes | Name shown in the menu and catalog — must be unique across the site |
| `parent` | yes | The category, e.g. `Grants` |
| `group` | yes | Same as `parent` |
| `entry_id` | yes | Short unique id other entries use to link here, e.g. `horizon-europe` |
| `kind` | yes | `intake` (a data source), `service`, `model`, `library` or `store` |
| `status` | yes | `active`, `candidate` (found, not in the pipeline yet), `todo`, `ok`, `warn`, `stop` or `store` — labels and colours in `_data/catalog.yml` |
| `description` | | One or two sentences |
| `location` | | Website for a source, repo path for a service, table name for a store |
| `serving` | | Where the data lands, or the endpoint a service runs on |
| `ingestion` | sources | `method` (Scraping, API, Manual, …) and `service` (the `entry_id` of the service that does it — becomes a link) |
| `projects` | | Projects that use this data, e.g. `[matchmaking]` |
| `candidate_projects` | | Projects it *could* feed but doesn't yet — shown dashed |
| `fields` | | What the source provides: list of `name` and `type` |
| `inputs` / `outputs` | services | List of `name`, `form`/`note`, and `from`/`to` (lists of `entry_id`s) |
| `open_questions` | | List of `level` (`open` or `blocker`) and `text` |

Anything below the closing `---` is free Markdown and appears under **Notes**.

## 3. Links are automatic

+ `ingestion.service: scraping-service` links the source to the Scraping service page.
+ `projects: [matchmaking]` puts the entry on the Matchmaking project page under **Data in the pipeline**; `candidate_projects` puts it under **Potential data**.
+ An input with `from: [x]` or an output with `to: [y]` shows the connection on both pages.

An `entry_id` that doesn't exist yet shows in red with a dashed border, so broken links are easy to spot.

## 4. Adding a project

1. Add it to `docs/_data/projects.yml` (`id`, `title`, `url`) — this adds the tab at the top.
2. Copy `docs/projects/matchmaking.md`, and change `title`, `project_id` and `permalink`.

## 5. Adding a category

Copy `docs/theses/index.md` into a new folder, change the title, `nav_order`, `permalink` and the `group` in the include, and add the name to `categories` in `docs/_data/catalog.yml`.

## 6. Preview locally (optional)

From the `docs` folder:

```bash
bundle install
bundle exec jekyll serve
```

Then open <http://localhost:4000/data/>.
