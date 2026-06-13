# Website Update Tutorial

This site is built with Jekyll/al-folio. After edits, run:

```bash
bundle exec jekyll serve
```

Open `http://127.0.0.1:4000/` to preview. Before committing, run:

```bash
bundle exec jekyll build
```

## Update the Home/About Page

Edit `_pages/about.md`.

- The text below the front matter is the homepage bio.
- The profile photo is controlled by `profile.image`; images live in `assets/img/`.
- Set `news: true` to show recent news on the homepage.
- Set `selected_papers: true` to show publications whose BibTeX entry has `selected={true}`.

## Update News

News items live in `_news/`.

Use this format for short homepage news:

```markdown
---
layout: post
date: Jun 2026
inline: true
---

One <a href="https://example.com">paper</a> accepted at CVPR 2026!
```

Important: use `inline: true` for news that should show directly on the homepage. If `inline: false`, the homepage shows a link to the news post title instead.

## Update Publications

Add or edit BibTeX entries in `_bibliography/papers.bib`.

Common fields:

```bibtex
@inproceedings{key2026paper,
  title={Paper Title},
  author={Author One and Author Two},
  booktitle={Conference Name},
  abbr={CVPR},
  year={2026},
  html={https://paper-page.example.com},
  pdf={https://arxiv.org/pdf/...},
  code={https://github.com/...},
  selected={true},
  preview={my_preview.gif}
}
```

To make a paper appear on the homepage selected-publications section, add `selected={true}`.

To add a new publication year, edit the `years:` list in `_pages/publications.md`.

### Add Publication GIF/Image Previews

Publication previews are supported through the `preview` BibTeX field. Put files in:

```text
assets/img/publication_preview/
```

Then set:

```bibtex
preview={my_result.gif}
```

GIFs should work because the bibliography layout renders previews with a normal HTML `<img>` tag. You can also use a full external URL:

```bibtex
preview={https://example.com/my_result.gif}
```

## Update Projects

Project pages live in `_projects/`. Each file needs front matter:

```markdown
---
layout: page
title: Project Name
description: Short project summary
img: assets/img/project_thumbnail.png
importance: 1
category: work
---
```

The body supports Markdown, HTML, embedded videos, and `{% include figure.html ... %}` image blocks. Do not leave backup files like `*.backup` in `_projects/`; if you must keep one, add `published: false`.

## Update Code / Repositories

The Code page is `_pages/repositories.md`, but the repository list comes from `_data/repositories.yml`.

Example:

```yaml
github_users:
  - zeroAska

github_repos:
  - ToyotaResearchInstitute/gcvo
  - UMich-CURLY/unified_cvo
```

Each entry becomes a GitHub card on `/repositories/`.

## Can the Homepage Contain About, Selected Publications, Projects, and Code?

Yes, this website can support that, but only About, News, and Selected Publications are already built into `_layouts/about.html` as front matter toggles. Projects and Code are separate pages by default.

To combine everything on the homepage while keeping clickable jump links:

1. Keep `_pages/about.md` as `permalink: /`.
2. Add section anchors such as `<section id="about">`, `<section id="publications">`, `<section id="projects">`, and `<section id="code">`.
3. Include the selected-publications block with `selected_papers: true`, or directly include `_includes/selected_papers.html`.
4. Copy the project loop from `_pages/projects.md` into a homepage section, or make a reusable include for it.
5. Copy the repository loop from `_pages/repositories.md` into a homepage section, or make a reusable include for it.
6. Add navigation links like `<a href="/#projects">Projects</a>` and `<a href="/#code">Code</a>`.

So: it is possible with a small template/content refactor. It is not currently available as a single config switch.
