# andreabedini.com

Static site built with [Zola](https://www.getzola.org). Deployed to GitHub
Pages by `.github/workflows/publish.yml` on every push to `main`, using the
Pages deployment API (`upload-pages-artifact` + `deploy-pages`) rather than
pushing a `gh-pages` branch.

This requires **Settings → Pages → Build and deployment → Source = "GitHub
Actions"**. The custom domain lives in those same settings, not in a `CNAME`
file — with this publishing source a `CNAME` file in the repo does nothing.

```sh
zola serve     # http://127.0.0.1:1111, live reload
zola build     # -> public/
zola check     # validate internal and external links
```

Pinned to Zola **0.23.4** in `mise.toml`; CI installs it with
`jdx/mise-action`, so local and CI builds use the same binary. 0.23 replaced
Tera macros with components, so `templates/components.html` uses the
`{% component %}` / `{{<name />}}` syntax rather than `{% macro %}`.

## Layout

- `content/` — pages and posts. The CV, Projects and Academia pages keep
  their data in TOML front matter (`[extra]`) and are rendered by their own
  templates; posts are ordinary markdown.
- `templates/` — Tera templates. `components.html` holds the shared
  components (icons, wordmark, tags, CV rows).
- `static/css/ds/` — the design system from `personal-design-system` (the
  `andreabedini-design` Agent Skill). It is **no longer a verbatim copy**;
  local edits pending validation upstream:
  - `tokens/fonts.css` — the Google Fonts `@import` moved into
    `templates/base.html` so the fonts load in parallel.
  - `tokens/colors.css` — `--ink-4` and `--blue-soft` retuned for contrast,
    the ink scope's `--text-faint` lifted, and a site-wide dark mode added
    on top of the system's scoped `[data-theme="ink"]`.
  - `tokens/base.css` — `::selection` moved onto semantic tokens.

  Re-copying from upstream will drop all of that, so reconcile rather than
  overwrite.
- `static/css/site.css` — the site layer: the UI-kit primitives
  (Button, Tag, Card, Avatar, Wordmark) re-implemented as CSS classes
  against the design system's custom properties.
