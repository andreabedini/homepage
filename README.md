# andreabedini.com

Static site built with [Zola](https://www.getzola.org). Deployed to GitHub
Pages by `.github/workflows/publish.yml` on every push to `main`.

```sh
zola serve     # http://127.0.0.1:1111, live reload
zola build     # -> public/
zola check     # validate internal and external links
```

Pinned to Zola **0.23.4** (see `ZOLA_VERSION` in the workflow). 0.23 replaced
Tera macros with components, so `templates/components.html` uses the
`{% component %}` / `{{<name />}}` syntax rather than `{% macro %}`.

## Layout

- `content/` — pages and posts. The CV, Projects and Academia pages keep
  their data in TOML front matter (`[extra]`) and are rendered by their own
  templates; posts are ordinary markdown.
- `templates/` — Tera templates. `components.html` holds the shared
  components (icons, wordmark, tags, CV rows).
- `static/css/ds/` — the design system, copied verbatim from
  `personal-design-system` (the `andreabedini-design` Agent Skill). Re-copy
  it from there to pick up upstream changes; the only local edit is
  `tokens/fonts.css`, whose Google Fonts `@import` moved into
  `templates/base.html` so the fonts load in parallel.
- `static/css/site.css` — the site layer: the UI-kit primitives
  (Button, Tag, Card, Avatar, Wordmark) re-implemented as CSS classes
  against the design system's custom properties.
