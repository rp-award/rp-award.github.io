# The Research Parasite Awards website

Source for [researchparasite.com](https://researchparasite.com) — the homepage of
the PSB Research Parasite Awards, which recognize rigorous secondary analysis of data.

It's a small [Jekyll](https://jekyllrb.com/) site hosted on **GitHub Pages**. GitHub
builds it automatically on every push to `master`; there is no separate deploy step.

## Updating the site

Almost all routine updates are edits to plain-text data files — you should rarely
need to touch the HTML.

| To change… | Edit |
| --- | --- |
| Application deadline, award year, PSB number, intro video | `_config.yml` |
| Award recipients (the year-by-year grid) | `_data/recipients.yml` |
| Honorable mentions | `_data/honorable_mentions.yml` |
| Current selection committee | `_data/committee.yml` |
| Former committee members | `_data/former_members.yml` |
| This year's sponsors | `_data/sponsors.yml` |

Each data file has a comment at the top explaining its fields. To add a new award
year, copy the most recent block in `_data/recipients.yml` and edit the names,
photos, and labels. Drop new photos into `img/past-recipients/` (or `img/team/`)
and reference them by path.

The page structure, prose sections (Mission, Apply, COI rules), and recipient
detail pop-ups live in:

- `index.html` — the page sections and the loops that render the data files
- `_includes/modals.html` — the historical recipient detail modals
- `_layouts/default.html` — the `<head>`, footer, and script tags

## Editing styles

The visual theme is the vendored [Start Bootstrap "Agency"](https://startbootstrap.com/theme/agency)
template (`css/agency.css`, `js/agency.min.js`, plus `vendor/`). Put site-specific
style tweaks in **`css/custom.css`** rather than editing the theme file, so the
theme stays easy to replace later.

## Previewing locally (optional)

You don't need to build locally to publish — just push. But to preview changes first:

```bash
bundle install        # one-time
bundle exec jekyll serve
```

Then open <http://localhost:4000>.

## Notes

- The custom domain is configured in `CNAME`.
- The old `gulp`/LESS build from the original theme has been removed; the compiled
  CSS/JS are committed directly and served as-is.

## License

Site content © the Research Parasite Awards committee. The underlying Agency theme
is released by Start Bootstrap under the [MIT license](LICENSE).
