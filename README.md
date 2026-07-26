# muphi.com

Source for my personal site, built with [Jekyll](https://jekyllrb.com/) and hosted free on GitHub Pages. GitHub builds it on every push, so day-to-day I only ever touch Markdown.

---

## Publishing a new post

1. Create a file in [`_posts/`](_posts/) named `YYYY-MM-DD-a-short-slug.md`.
2. Front matter at the top, then Markdown below it:

   ```markdown
   ---
   layout: post
   title: "Your headline here"
   description: "One-sentence summary — shows on the writing index and in link previews."
   reading_time: "4 min read"   # optional
   ---

   First paragraph…
   ```

3. Commit and push. It shows up at `muphi.com/writing/a-short-slug/` within a minute or two, and automatically appears on the homepage and the [/writing](https://muphi.com/writing/) index, newest first.

No build step, no deploy button. [`_posts/2026-07-25-welcome.md`](_posts/2026-07-25-welcome.md) is a decent template to copy.

> To draft without publishing, drop the file in `_drafts/` instead (no date in the filename) and preview with `bundle exec jekyll serve --drafts`.

---

## How it's hosted

Repo: `martynfagg.github.io`, public (GitHub Pages needs that on the free plan), building from `main` / root via **Settings → Pages**.

The [`CNAME`](CNAME) file points it at `muphi.com`. DNS:

| Type  | Host / Name | Value |
|-------|-------------|-------|
| A     | `@`         | `185.199.108.153` |
| A     | `@`         | `185.199.109.153` |
| A     | `@`         | `185.199.110.153` |
| A     | `@`         | `185.199.111.153` |
| CNAME | `www`       | `martynfagg.github.io.` |

Reference if I ever need to redo this: [GitHub Pages custom domains](https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site).

---

## Previewing locally

Needs Ruby.

```bash
bundle install
bundle exec jekyll serve --livereload
```

<http://localhost:4000>

---

## Layout of the repo

| File / folder            | What it is |
|--------------------------|------------|
| `index.html`             | Homepage (hero, roles, about, writing, connect) |
| `_posts/`                | Blog posts, one Markdown file each |
| `blog/index.html`        | The `/writing/` listing page |
| `_layouts/`              | Page templates (`default`, `post`) |
| `assets/css/main.css`    | All styling — colours, fonts, layout |
| `_config.yml`            | Site title, tagline, LinkedIn handle, settings |
| `CNAME`                  | Custom domain (`muphi.com`) |

Palette and fonts live in the `:root` variables at the top of `assets/css/main.css`.
