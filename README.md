# atnafuatx.github.io

Personal academic website of Atnafu Lambebo Tonja, built with Jekyll and
served by GitHub Pages at <https://atnafuatx.github.io>.

## Where things live

| To change…                         | Edit                          |
| ---------------------------------- | ----------------------------- |
| Name, role, affiliation, PDF CV    | `_config.yml`                 |
| Profile links (Scholar, ORCID, …)  | `_data/links.yml`             |
| News on the home page              | `_data/news.yml`              |
| Publications, awards, selected     | `_data/publications.yml`      |
| Talks                              | `_data/talks.yml`             |
| Blog posts                         | `_posts/`                     |
| Header navigation                  | `_data/navigation.yml`        |
| Bio                                | `_pages/about.html`           |
| CV (positions, education)          | `_pages/cv.html`              |
| Styles                             | `assets/css/minimal.css`      |
| Afri-MCQA project page             | `Afri-MCQA/index.html`        |

Publications marked `selected: true` also appear on the home page. Entries
with an `award` are listed automatically under "Awards and honours" on the CV.

### Adding a talk

Add an entry at the top of `_data/talks.yml` (the file has a template to copy).
Slides can be a link or a PDF placed in `files/talks/`.

### Writing a blog post

Create `_posts/YYYY-MM-DD-short-title.md`, for example
`_posts/2026-10-20-why-benchmarks-need-native-speakers.md`:

```markdown
---
title: "Why benchmarks need native speakers"
description: "One-sentence summary shown on the blog page and in link previews."
tags: [evaluation, African languages]
---

Write the post in Markdown here.
```

It appears at `/blog/2026/why-benchmarks-need-native-speakers/` and in the
RSS feed at `/feed.xml`.

### CV PDF

To link a PDF CV, add the file (for example `files/cv.pdf`) and set
`cv_pdf: "/files/cv.pdf"` in `_config.yml`.

## Run locally

```bash
bundle install
bundle exec jekyll serve --config _config.yml,_config.dev.yml
```

Then open <http://localhost:4000>.

## License

The site's code is MIT-licensed (see `LICENSE`); it began as a fork of the
Academic Pages / Minimal Mistakes template.
