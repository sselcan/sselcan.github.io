# sselcan.github.io

Personal academic website for Şeyma Selcan Mağara — live at <https://sselcan.github.io>.

Built with [Jekyll](https://jekyllrb.com) using the
[Academic Pages](https://academicpages.github.io/) template. This README is the
practical guide for running and updating the site; template documentation lives
upstream at <https://github.com/academicpages/academicpages.github.io>.

---

## Running it locally

### In the devcontainer (the normal case)

**A Jekyll server is already running.** The container starts it as PID 1:

```
jekyll serve -H 0.0.0.0 -w --config _config.yml,_config_docker.yml
```

Just open <http://localhost:4000>. The `-w` flag watches the source files, so
saving any page, publication, or stylesheet triggers a rebuild in a few seconds —
you only need to **refresh the browser**. Do not start a second server; port 4000
is taken and you will get `Address already in use - bind(2) for 0.0.0.0:4000`.

If VS Code doesn't open the page, check the **Ports** panel and make sure 4000 is
forwarded, then click the globe icon there.

### Starting it yourself

Only needed if the running server died (`ps -p 1` to check):

```sh
bundle exec jekyll serve -H 0.0.0.0 -w --config _config.yml,_config_docker.yml
```

Use `bundle exec` so the gem versions pinned in [Gemfile](Gemfile) are the ones
that run. (`ruby jekyll` is not a valid command — `ruby` expects a file path.)
The second config file, `_config_docker.yml`, only sets `url: ""` so local links
don't point at the production domain. Always include it when serving locally.

### With Docker, outside the devcontainer

```sh
docker compose up
```

Same result — see [docker-compose.yaml](docker-compose.yaml).

### Gotchas

| Symptom | Cause |
| --- | --- |
| Edits don't appear | Browser cache. Hard refresh: <kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>R</kbd> (<kbd>Cmd</kbd>+<kbd>Shift</kbd>+<kbd>R</kbd> on Mac), or use a private window. PDFs are cached especially aggressively. |
| `_config.yml` edits don't appear | **The watcher does not reload `_config.yml`.** Restart the server. |
| `Address already in use` | A server is already running. Use it instead of starting another. |
| Changes missing on the live site | Not pushed yet, or the new files were never `git add`ed. See [Publishing](#publishing). |

---

## Where everything lives

| What | File / folder |
| --- | --- |
| **Homepage text** | [_pages/about.md](_pages/about.md) — `permalink: /` |
| Site title, description, sidebar profile, social links | [_config.yml](_config.yml) |
| Header menu | [_data/navigation.yml](_data/navigation.yml) |
| Publications | [_publications/](_publications/) — one file per paper |
| Teaching entries | [_teaching/](_teaching/) — one file per course |
| Talks | [_talks/](_talks/) *(currently hidden from the menu)* |
| Portfolio | [_portfolio/](_portfolio/) *(currently hidden from the menu)* |
| CV page | [_pages/cv.md](_pages/cv.md) |
| PDFs and downloads | [files/](files/) → served at `/files/<name>.pdf` |
| Images | [images/](images/) |
| Page templates | [_layouts/](_layouts/), [_includes/](_includes/) |
| Styles | [_sass/](_sass/), [assets/css/](assets/css/) |

`_site/` is the generated output. It is gitignored — never edit or commit it.

---

## How to make common changes

### Edit the homepage

[_pages/about.md](_pages/about.md). Plain Markdown below the front matter.

### Add a publication

Create `_publications/YYYY-MM-DD-short-name.md`:

```yaml
---
title: "Full paper title"
collection: publications
category: manuscripts
permalink: /publication/short-name
excerpt: 'One or two sentences shown in the listing.'
date: 2026-09-03
authors: "Şeyma Selcan Mağara, Co Author, Another Author"
venue: 'Conference or journal name'
paperurl: 'https://arxiv.org/abs/...'
citation: 'Full formatted citation.'
---

Longer description shown on the publication's own page.
```

Notes:
- `category` must be a key from `publication_category` in [_config.yml](_config.yml)
  (currently `manuscripts` and `books`). An unknown value means the entry silently
  **does not appear** on the publications page.
- `permalink` is the page URL and is independent of the filename — keep it unique.
- The listing is sorted by `date`, newest first.

### Add a teaching entry

Create a file in [_teaching/](_teaching/), matching the existing ones:

```yaml
---
title: "Teaching Assistant – Course Name"
collection: teaching
type: "Teaching Assistant"
venue: "University name"
date: 2020-09-15
dates: ["Fall 2020–2021"]
excerpt: "Short summary."
---
```

`date` controls ordering; `dates` is the human-readable label that gets displayed.

### Show or hide a menu item

Uncomment or comment the entry in [_data/navigation.yml](_data/navigation.yml).
Removing it from the menu does **not** remove the page — it stays reachable at its
URL. Talks, Portfolio, and Blog Posts are currently commented out.

### Update the CV

Replace `files/Seyma_Selcan_Magara_CV.pdf` with the new PDF, keeping the same
filename so the download button and inline viewer in [_pages/cv.md](_pages/cv.md)
keep working. If you rename it, update both references in that file.

### Change the sidebar (photo, bio, email, links)

The `author:` block in [_config.yml](_config.yml). The avatar path is relative to
[images/](images/). Blank fields hide their icon. **Restart the server** afterwards.

---

## Publishing

The repo is `sselcan/sselcan.github.io` and uses GitHub's classic
"deploy from a branch" Pages build — there is no deploy workflow in
[.github/workflows/](.github/workflows/), GitHub runs Jekyll server-side.

**Pushing to `master` is all it takes.** The live site updates about a minute
later; progress shows as a `pages-build-deployment` run in the repo's Actions tab.

One thing to watch: `git commit -a` only picks up files git already tracks. New
publications, new PDFs, and new images must be added explicitly:

```sh
git status              # look for "Untracked files"
git add _publications/new-paper.md files/new.pdf
git commit -m "Add new paper"
git push
```

A new file that was never `git add`ed will work perfectly on localhost and 404 on
the live site — that is the most common cause of "it worked locally".

Always preview at <http://localhost:4000> before pushing; the live build gives no
useful error messages when a page fails to render.
