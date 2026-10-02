---
title: Add a data source
nav_order: 8
---

# Add a data source
{: .no_toc }

1. TOC
{:toc}

There are two ways to add something to the catalog. Most people should **propose** a source; the maintainer turns accepted proposals into pages.

## Propose a new data source

<a class="sis-btn" href="https://github.com/ScoutinScience/data/issues/new?template=new-data-source.yml">Propose a data source</a>

The button opens a short form on GitHub (you need a GitHub account). You don't need to touch any files.

### What qualifies as a data source

A source is added to the catalog when it meets all of these:

1. **It's new.** It isn't already in the catalog — check Home first.
2. **It fits a category.** It gives us grants, publications, patents or theses. Anything else needs a short explanation of which entity it would become.
3. **It provides the required attributes.** Every source in a category must supply that category's required attributes, highlighted on the category page — for grants: title, description, deadline and budget.
4. **We're allowed to collect it.** It's public, openly licensed, or available through an official API, and its terms of use don't forbid collecting it.
5. **It's useful to a project.** At least one project could use it, now or later.
6. **It's maintained.** It's updated over time rather than being a one-off file. (Preferred, not required.)

### What happens next

| Step | Who | Result on the site |
|:--|:--|:--|
| 1. Proposal submitted | Anyone | An issue labelled *data source proposal* |
| 2. Review against the criteria | Maintainer | Accepted, or a comment on what's missing |
| 3. Page added | Maintainer | The source appears as **Candidate**, with dashed links to its potential projects and, if given, an urgency marker and target date |
| 4. Ingestion built | Engineering | Status changes to **Active**; dashed links become solid |

## Editing pages directly

For the maintainer and anyone comfortable with Git: change the files and open a pull request — the PR template has a checklist. The rest of this page explains the format.

Every data source, service or store is **one Markdown file**. Its page, its row in the catalog, its project links and its connections to other entries are all generated from the front matter, so that one file is all you edit.

## 1. Pick the category folder

| Folder | Category |
|:--|:--|
| `docs/grants/` | Grants |
| `docs/publications/` | Publications |
| `docs/patents/` | Patents |
| `docs/theses/` | Theses |
| `docs/ingestors/apis/` | API ingestors |
| `docs/ingestors/scrapers/` | Scrapers |
| `docs/storage/` | Where data is stored |

The quickest start is to copy `docs/grants/nwo.md` and change it.

## 2. Fill in the front matter

| Field | Required | What it is |
|:--|:--|:--|
| `layout` | yes | Always `entry` |
| `title` | yes | Name shown in the menu and catalog — must be unique across the site |
| `parent` | yes | The section, e.g. `Grants` (for ingestors: `APIs` or `Scrapers`, plus `grand_parent: Ingestors`) |
| `group` | yes | Same as `parent` |
| `entry_id` | yes | Short unique id other entries use to link here, e.g. `horizon-europe` |
| `kind` | yes | `intake` (a data source), `service` (e.g. an ingestor), `model`, `library` or `store` |
| `status` | yes | `active`, `candidate` (found, not in the pipeline yet), `todo`, `ok`, `warn`, `stop` or `store` — labels in `_data/catalog.yml` |
| `urgency` | | For data that is missing but should be integrated: `high`, `medium` or `low`. Shows a yellow/orange marker in the top-right corner |
| `target_date` | | Intended date for integration, as `YYYY-MM-DD` — shown next to the urgency |
| `description` | | One or two sentences |
| `location` | | Website for a source, repo path for a service, table name for a store |
| `storage` | sources | `entry_id` of where the data is stored, e.g. `postgres-db` (becomes a link and the label on the diagram) |
| `storage_table` | | Table name, e.g. `Grants` |
| `serving` | services | The endpoint a service runs on |
| `ingestion` | sources | `method` (API, Scraping, Manual, …) and `service` (the `entry_id` of the ingestor that does it, e.g. `openalex-api` or `scraping-service` — becomes a link) |
| `projects` | | Projects that use this data, e.g. `[matchmaking]` |
| `candidate_projects` | | Projects it *could* feed but doesn't yet — shown dashed |
| `inputs` / `outputs` | services | List of `name`, `form`/`note`, and `from`/`to` (lists of `entry_id`s) |
| `open_questions` | | List of `level` (`open` or `blocker`) and `text` |

Anything below the closing `---` is free Markdown and appears under **Notes**.

## 3. Links are automatic

+ `ingestion.service: scraping-service` links the source to the Scraping service page.
+ `projects: [matchmaking]` puts the entry on the Matchmaking project page under **Data in the pipeline**; `candidate_projects` puts it under **Potential data**.
+ An input with `from: [x]` or an output with `to: [y]` shows the connection on both pages.

An `entry_id` that doesn't exist yet shows in red with a dashed border, so broken links are easy to spot.

## 4. Attributes of an entity

The attributes of each entity (Grant, Publication, …) live in `docs/_data/entities.yml`. Mark obligatory ones with `required: true`: they're highlighted in the table on the category page and listed on every source page of that category.

## 5. The diagram on Home

The diagram is built from the source pages — you never edit it directly. A source appears once it has `kind: intake`; its arrows come from `ingestion.service`, `storage`, `projects` and `candidate_projects`.

## 6. Adding a project

1. Add it to `docs/_data/projects.yml` (`id`, `title`, `url`) — this adds the tab at the top.
2. Copy `docs/projects/matchmaking.md`, and change `title`, `project_id` and `permalink`.

## 7. Adding a category

Copy `docs/theses/index.md` into a new folder, change the title, `nav_order`, `permalink` and the `group` in the include, add the name to `categories` in `docs/_data/catalog.yml`, and add its entity to `docs/_data/entities.yml`.

## 8. Preview locally (optional)

From the `docs` folder:

```bash
bundle install
bundle exec jekyll serve
```

Then open <http://localhost:4000/data/>.
