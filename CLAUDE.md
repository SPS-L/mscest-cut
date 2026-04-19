# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Hugo static site for the joint **MSc in Electronics Science and Technology** program between Cyprus University of Technology (CUT) and Hangzhou Dianzi University (HDU). Built with the **Wowchemy Research Group theme** (v5.7.1, via Hugo modules). Bilingual: English + Simplified Chinese. Deployed on Netlify.

## Development Commands

```bash
# Local dev server (with drafts)
hugo server -D
# Served at http://localhost:1313

# Production build (matches Netlify)
hugo --gc --minify

# Fetch/update Hugo modules
hugo mod get

# Clean module cache
hugo mod clean
```

Hugo version pinned in `netlify.toml`: **0.97.3** (extended). Go 1.15+. This Hugo version is older than current stable — prefer installing it exactly rather than latest, or `hugo server` may reject theme templates.

## Architecture

### Bilingual Content

Two parallel trees under `content/`:

- `content/en/` — English (default language, served at root)
- `content/zh/` — Simplified Chinese (mirrors the English structure; accessed via language switcher)

When adding new content, create the English version under `content/en/...` first, then mirror the folder structure under `content/zh/...` with translated frontmatter and body. Folder names and filenames stay identical across languages — Hugo matches translations by path. The Chinese menu is defined inline in `config/_default/languages.yaml` (not `menus.yaml`).

### Content Types

- **`program/Semester N/`** — Course catalog. Each semester is a folder with course Markdown files named by course code (`G111001.md`, `Z104001.md`, etc.). `_index.md` at the semester level uses `type: book` and renders children via the custom `{{< list_children_cust >}}` shortcode. Courses reference their instructor via `{{< mention "AuthorFolderName" >}}`.
- **`authors/`** — Faculty/coordinator profiles. Each is a folder with `_index.md`. **Author slug = folder name in CamelCase** (e.g. `ChristakisDamianou`, `XiaoqinZhou`) — not the `first-initial.-lastname` style used by some Hugo Blox sites. The special folder `admin/` represents the site's primary user.
- **`publication/`** — Student theses (primarily). Folder naming convention: `YYYY_FirstName_LastName/` (e.g. `2025_Cheng-Yi_Feng/`). Uses **TOML frontmatter** (`+++` delimiters, not YAML). `publication_types` uses **numeric codes** (see below).
- **`post/`** — News items. Folder naming convention: `YY-MM-DD Short Description/` (e.g. `24-09-01 Welcome to Cyprus/`).
- **`people/index.md`** — Single landing page using the `people` block, filtered by `user_groups` (currently `Coordinator`, `Teaching`).
- **`tour/`, `contact/`, `admin/`** — Single landing pages. `admin/` generates the Wowchemy CMS config and is marked `private: true`.

### Publication Type Codes

Unlike newer Hugo Blox sites that use string codes, this site uses Wowchemy numeric codes. Mapping is documented at the top of `content/en/publication/_index.md`:

| Code | Meaning |
|---|---|
| 0 | Uncategorized |
| 1 | Journal article |
| 2 | Conference paper |
| 3 | Preprint |
| 4 | Report |
| 5 | Book |
| 6 | Book section |
| 7 | Thesis |
| 8 | Patent |

### Homepage (`content/en/_index.md`, `content/zh/_index.md`)

Single-page landing using Wowchemy `sections` blocks: hero, latest news (collection of `post`), latest publications (collection filtered by `publication_types 1–7`). The Chinese homepage is a translated mirror.

### Custom Layouts

- `layouts/shortcodes/list_children_cust.html` — Variant of the theme's `list_children` that shows a page summary under each child title. Used by `program/Semester N/_index.md`.
- `layouts/partials/li_card.html`, `li_citation.html`, `li_compact.html` — Custom list-item renderers overriding theme defaults.
- `layouts/partials/widgets/timeline.html` (and `timeline_bak.html`) — Custom timeline widget.
- `layouts/partials/blocks/pages.html` — Custom pages block override.

Theme templates should generally be overridden in `layouts/` rather than edited in the module cache.

### Configuration

All Hugo config is in `config/_default/`:
- `config.yaml` — Core settings, taxonomies (`tags`, `categories`, `publication_types`, `authors`), permalink patterns (`/author/:slug/`, `/tag/:slug/`, etc.), Hugo module imports (wowchemy v5, netlify-cms plugin, netlify plugin).
- `languages.yaml` — English + Chinese setup; **the Chinese `main` menu is defined here inline**, not in `menus.yaml`.
- `menus.yaml` — English navigation only (News, Program, People, Publications).
- `params.yaml` — Theme appearance, analytics, CMS settings.

## Deployment

Netlify auto-deploys on push to `main`. Config in `netlify.toml`:
- Production: `hugo --gc --minify -b $URL`
- Deploy previews: `hugo --gc --minify --buildFuture -b $DEPLOY_PRIME_URL`
- Uses `netlify-plugin-hugo-cache-resources` to cache `resources/`.

No GitHub Pages or CI-based publication import workflow in this repo.

## Key Conventions

- Editor config: UTF-8, LF line endings, 2-space indent (`.editorconfig`).
- `enableEmoji: true`, `hasCJKLanguage: true` — emoji and Chinese rendering both active.
- `{{< mention "AuthorFolderName" >}}` links to `/author/<slug>/`. The slug is derived from the folder name (CamelCase preserved, not hyphenated).
- When mirroring content to `content/zh/`, keep filenames and folder names identical to the English tree so Hugo pairs translations correctly.
- **Pre-push verification**: Before every `git push`, run `hugo --gc --minify` locally and confirm the build succeeds. Do not push if the build fails.

## Workflow Guides

### How to Add a New Course to a Semester

1. Create `content/en/program/Semester N/<CODE>.md` using an existing course (e.g. `G111001.md`) as a template:
   ```yaml
   ---
   title: Course Full Name
   linkTitle: <CODE>
   date: '2021-01-01'
   type: book
   weight: 10
   tags:
     - Compulsory Courses   # or: Elective Courses
   ---
   ```
2. Body sections typically include: `## Course overview`, `## What you will learn`, `## Meet your instructor` (with `{{< mention "AuthorFolderName" >}}`), `## Course content`.
3. Mirror the file at `content/zh/program/Semester N/<CODE>.md` with translated content.

### How to Add a Faculty Profile

1. Create `content/en/authors/<CamelCaseName>/_index.md` using an existing profile (e.g. `ChristakisDamianou/_index.md`) as a template.
2. Frontmatter keys: `title` (display name), `first_name`, `last_name`, `authors` (list containing the same CamelCase slug), `superuser: false`, `role`, `organizations`, `bio`, `education.courses`, optional `social` icons.
3. Set `user_groups` to control which People-page section they appear in (currently filtered by `Coordinator`, `Teaching` in `content/en/people/index.md`).
4. Add `avatar.jpg` in the same folder.
5. Mirror under `content/zh/authors/<CamelCaseName>/_index.md` with translated `title`/`role`/`bio`.

### How to Add a Thesis/Publication

1. Create `content/en/publication/YYYY_FirstName_LastName/index.md` using TOML frontmatter (`+++` delimiters — matches the existing entries):
   ```toml
   +++
   title = "Thesis title"
   date = "2025-06-01"
   authors = ["First Last"]
   tags = ["keyword1", "keyword2"]
   publication_types = [7]   # 7 = Thesis; see code table above
   publication = "_Cyprus University of Technology_"
   abstract = ""
   summary = ""
   featured = false
   [image]
   image = ""
   caption = ""
   +++
   ```
2. Add body content in Markdown below the frontmatter.
3. Mirror under `content/zh/publication/...` if a Chinese version exists.

### How to Add a News Post

1. Create `content/en/post/YY-MM-DD Short Title/index.md`:
   ```yaml
   ---
   title: Post title
   date: 2024-09-01
   draft: false
   ---
   Short intro.
   <!--more-->
   Full body.
   ```
2. Optional: add a `featured.jpg`/`featured.png` in the same folder for card thumbnails.
3. Mirror under `content/zh/post/...` for the Chinese version.

### Cross-Referencing

- Mention a faculty member anywhere in Markdown: `{{< mention "ChristakisDamianou" >}}`.
- Link internally: `[text](/publication/2025_cheng-yi_feng/)` (slugs are lowercased by Hugo). The `removePathAccents: true` setting in `config.yaml` strips accents from URLs.
- Group related content via shared `tags` — each tag gets a page at `/tag/<slug>/`.
