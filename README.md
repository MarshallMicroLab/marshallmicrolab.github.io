# Marshall Micro Lab website

The source for [marshallmicrolab.github.io](https://marshallmicrolab.github.io), the Marshall Micro Lab website. It is a lightweight Jekyll site designed so **routine updates require only adding or editing Markdown files**—not HTML.

## Content map

| Content | Folder | Generated location |
|---|---|---|
| Lab members | `_people/` | `/people/name/` |
| Research projects | `_research/` | `/research/project/` |
| Publications | `_publications/` | `/publications/paper/` and the publication list |
| Software | `_software/` | `/software/tool/` |
| News | `_news/` | `/news/post/` |

Layouts live in `_layouts/`, reusable components in `_includes/`, and presentation files in `assets/`. Routine content editing should not require changes to those directories.

## Run locally

Jekyll uses Ruby. A current Ruby managed with Homebrew, `rbenv`, or `asdf` is recommended rather than macOS's system Ruby.

```sh
bundle install
bundle exec jekyll serve --livereload
```

Open <http://127.0.0.1:4000>. To perform a production build:

```sh
JEKYLL_ENV=production bundle exec jekyll build
```

## GitHub Pages deployment

The repository is configured for GitHub Pages' native Jekyll build. Push changes to `main`; GitHub Pages reads `_config.yml`, builds the site, and publishes it. No Node, React, database, CMS, or custom GitHub Action is needed.

In **Settings → Pages**, set **Source** to **Deploy from a branch**, choose `main`, and choose `/ (root)`. The organization-site URL and `baseurl: ""` make links resolve at `https://marshallmicrolab.github.io`.

## Add a lab member

Copy an existing file in `_people/` to `_people/firstname-lastname.md`, update the front matter and biography, and optionally add a portrait under `assets/images/people/`.

```yaml
---
name: Firstname Lastname
role: Graduate Student
category: graduate
photo: /assets/images/people/firstname-lastname.jpg
email:
github:
orcid:
google_scholar:
linkedin:
website:
order: 1
description: One-sentence description shown on the People page.
---

Write the full biography here in Markdown.
```

Valid categories are `pi`, `faculty`, `postdoc`, `graduate`, `undergraduate`, `staff`, `collaborator`, and `alumni`. Blank optional fields are hidden. Move someone to alumni by changing `category: alumni`; remove them by deleting the file.

## Add a publication

Copy a record in `_publications/` and use a filename such as `_publications/2026-short-paper-title.md`:

```yaml
---
title: "Paper title"
authors: "Author A, Author B, Marshall AG"
journal: "Journal Name"
year: 2026
doi:
pubmed:
article_url:
pdf:
image:
featured: false
---
```

Use the DOI value only (for example, `10.0000/example`) and a PubMed ID only. `article_url` accepts a full external article URL. Local PDFs can go in `assets/pdfs/`. Publications are grouped by year and sorted newest first automatically.

## Add a research project

Create `_research/project-slug.md`:

```yaml
---
title: Project title
short_title: Short title
summary: A concise card description.
image: /assets/images/research/project.jpg
image_alt: Description of the image
featured: true
order: 1
status: active
related_publications:
  - publication-file-slug
related_software:
  - software-file-slug
funding: Optional funding acknowledgement.
---

## Overview

Project overview in Markdown.

## Objectives

- Objective one
- Objective two

## Collaborators

Collaborator information.
```

`featured: true` places the project in the homepage pool. Related values are filenames without `.md`.

## Add software

Create `_software/tool-name.md`:

```yaml
---
title: Tool name
github:
documentation:
publication:
pypi:
conda:
doi:
description: Short card description.
language: Python
logo: /assets/images/software/tool-logo.png
screenshot: /assets/images/software/tool-screenshot.png
screenshot_alt: Description of the screenshot
featured: true
order: 1
---

Longer documentation and examples go here in Markdown.
```

All links and images are optional; empty values do not render.

## Add a news item

Create `_news/YYYY-MM-DD-short-title.md`:

```yaml
---
title: News title
date: 2026-08-31
image:
image_alt:
summary: A short summary for listing cards.
---

Write the update in Markdown.
```

News is sorted newest first, and the newest three entries appear on the homepage.

## Images and fallbacks

- People: `assets/images/people/`
- Research: `assets/images/research/`
- Software: `assets/images/software/`
- Lab logo: `assets/images/mml-logo.png`
- Optional social preview: `assets/images/social-preview.png`

Images are optional. Designed fallbacks appear when a path is blank. After adding a logo or social preview, uncomment its setting in `_config.yml`. Supply meaningful `image_alt` text for informative images.

## Site-wide settings

Edit `_config.yml` for the title, tagline, description, canonical URL, branding, UF affiliation URLs, organization links, collection URLs, and page defaults. Restart Jekyll after changing it. Main page introductions are in each section's `index.md`; homepage text is in the root `index.md`.

## Placeholder content

Initial people and publication examples are explicitly labeled. Replace or delete those Markdown files before launch. Software URLs are blank where canonical repositories were not confirmed.

## License

Site code is available under the [MIT License](LICENSE). Lab text, images, publications, and research content remain the property of their respective owners.
