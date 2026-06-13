# Repository Guidelines

## Project Structure & Module Organization

This repository is a Jekyll-based academic website. Core configuration lives in `_config.yml`, with layouts in `_layouts/`, partials in `_includes/`, Sass in `_sass/`, and custom Ruby plugins in `_plugins/`. Site content is organized by collection: `_pages/` for main pages, `_posts/` for dated blog posts, `_projects/` for project entries, `_news/` for announcements, and `_bibliography/papers.bib` for publications. Static files, images, and scripts belong under `assets/`. Do not edit generated output in `_site/`.

## Build, Test, and Development Commands

- `bundle install`: install Ruby gems from `Gemfile.lock`.
- `bundle exec jekyll serve`: run the site locally, typically at `http://127.0.0.1:4000/`.
- `bundle exec jekyll build`: build the static site into `_site/`; this is the CI smoke test.
- `./bin/cibuild`: repository wrapper for the build command.
- `./bin/dockerhub_run.sh`: run the site using the published Docker image.
- `./bin/docker_build_image.sh` then `./bin/docker_run.sh`: rebuild and run the local Docker image.

## Coding Style & Naming Conventions

Use two-space indentation for YAML front matter, HTML/Liquid templates, and Markdown metadata. Keep filenames consistent with Jekyll conventions: blog posts use `YYYY-MM-DD-title.md`, while project and news entries should follow existing numbered or slug-based names. Prefer small Liquid includes over duplicated markup. Keep Sass changes in `_sass/` partials and reuse variables from `_sass/_variables.scss`.

## Testing Guidelines

There is no dedicated unit test suite. Treat `bundle exec jekyll build` as required validation before submitting changes. For content edits, also run `bundle exec jekyll serve` and inspect affected pages, especially publications, projects, navigation, and image paths. When changing diagrams or Mermaid content, verify generated pages locally when possible.

## Commit & Pull Request Guidelines

Recent commits use short, imperative summaries such as `update publication`, `change gemfile`, and `update dockerfile`. Keep commit subjects concise and focused on one logical change. Pull requests should include a brief description, linked issue when relevant, screenshots for visual changes, and confirmation that `bundle exec jekyll build` passed. Open or reference an issue for feature work or bug fixes.

## Agent-Specific Instructions

Do not edit generated files in `_site/`, cache directories, or vendored dependencies unless explicitly requested. Preserve existing front matter keys because collections and layouts depend on them.
