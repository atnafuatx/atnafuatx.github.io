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
| Header navigation                  | `_data/navigation.yml`        |
| Bio                                | `_pages/about.html`           |
| CV (positions, education)          | `_pages/cv.html`              |
| Styles                             | `assets/css/minimal.css`      |
| Afri-MCQA project page             | `Afri-MCQA/index.html`        |

Publications marked `selected: true` also appear on the home page. Entries
with an `award` are listed automatically under "Awards and honours" on the CV.

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
