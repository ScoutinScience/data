---
title: Adding an entry
nav_order: 4
---

# Adding an entry
{: .no_toc }

1. TOC
{:toc}

Every model, service, library or data store is **one Markdown file**. The page, the catalog row, and the links between entries are all generated from its front matter, so you only ever edit that one file.

## 1. Pick the folder

Entries live under their project and section, e.g. `docs/matchmaking/grants/`. The quickest start is to copy one of the examples there:

+ `example-model.md` — for a model, service or library
+ `example-store.md` — for a table, topic, index or other data store

## 2. Fill in the front matter

| Field | Required | What it is |
|:--|:--|:--|
| `layout` | yes | Always `entry` |
| `title` | yes | Name shown in the menu and catalog — must be unique across the site |
| `parent`, `grand_parent` | yes | Where it sits in the menu, e.g. `Grants` / `Matchmaking` |
| `entry_id` | yes | Short unique id other entries use to link here, e.g. `grants-matcher` |
| `group` | yes | Heading it sits under in the catalog, usually the section name |
| `kind` | yes | `model`, `service`, `library` or `store` |
| `status` | yes | `ok`, `warn`, `stop`, `store` or `todo` — labels and colours in `_data/catalog.yml` |
| `description` | | One or two sentences |
| `location` | | Repo path, or table / topic name for a store |
| `serving` | | Endpoint, port or job — or "None" |
| `version`, `owner` | | Optional |
| `inputs` | | List of `name`, `form`, and `from` (list of `entry_id`s) |
| `outputs` | | List of `name`, `note`, and `to` (list of `entry_id`s) |
| `fields` | stores | List of `name`, `type`, and `written_by` (list of `entry_id`s) |
| `open_questions` | | List of `level` (`open` or `blocker`) and `text` |

## 3. Links are automatic

You only record each connection once:

+ An **input** with `from: [x]` makes *x* appear under **Depends on** here, and this entry appear under **Feeds** / **Read by** on *x*.
+ An **output** with `to: [y]` makes *y* appear under **Feeds** here, and this entry appear under **Written by** on *y*.

An `entry_id` that doesn't exist yet shows up in red with a dashed border, so broken links are easy to spot.

## 4. Adding a new project or section

Create a folder with an `index.md`, like `docs/matchmaking/index.md` (a project) and `docs/matchmaking/grants/index.md` (a section inside it). Give the index `has_children: true`, and give its entries `parent:` (and `grand_parent:` for a section inside a project).

## 5. Preview locally (optional)

From the `docs` folder:

```bash
bundle install
bundle exec jekyll serve
```

Then open <http://localhost:4000/data/>.
