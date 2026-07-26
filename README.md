# muphi.com

Personal site for Martyn Fagg — built with [Jekyll](https://jekyllrb.com/) and hosted free on GitHub Pages. GitHub builds the site for you on every push, so day-to-day you only ever touch Markdown.

---

## Publishing a new blog post (the only thing you'll do often)

1. Create a file in [`_posts/`](_posts/) named `YYYY-MM-DD-a-short-slug.md`.
2. Put this front matter at the top, then write in Markdown below it:

   ```markdown
   ---
   layout: post
   title: "Your headline here"
   description: "One-sentence summary — shows on the writing index and in link previews."
   reading_time: "4 min read"   # optional
   ---

   Your first paragraph…
   ```

3. Commit and push. The post appears at `muphi.com/writing/a-short-slug/` within a minute or two, and automatically shows up on the homepage and the [/writing](https://muphi.com/writing/) index (newest first).

That's it — no build step, no deploy button. Copy [`_posts/2026-07-25-welcome.md`](_posts/2026-07-25-welcome.md) as a template.

> Tip: to draft without publishing, keep the file in a `_drafts/` folder (no date in the name). Run locally with `bundle exec jekyll serve --drafts` to preview.

---

## Adding your headshot

Drop a photo at `assets/img/martyn.jpg` (portrait, ~1000×1250px, under ~300KB), then in [`index.html`](index.html) replace the `<figcaption class="portrait__ph">…</figcaption>` placeholder block with:

```html
<img src="/assets/img/martyn.jpg" alt="Martyn Fagg">
```

---

## First-time setup on GitHub

1. Create a **public** repo. For a user site the simplest is naming it `martynfagg.github.io`; any repo name works too since we use a custom domain.
2. Push these files to the `main` branch.
3. In the repo: **Settings → Pages → Build and deployment → Source: Deploy from a branch**, branch `main`, folder `/ (root)`. Save.
4. GitHub builds and publishes within a minute or two.

### Pointing muphi.com at it

The [`CNAME`](CNAME) file already tells GitHub the domain is `muphi.com`. At your DNS provider add:

| Type  | Host / Name | Value |
|-------|-------------|-------|
| A     | `@`         | `185.199.108.153` |
| A     | `@`         | `185.199.109.153` |
| A     | `@`         | `185.199.110.153` |
| A     | `@`         | `185.199.111.153` |
| CNAME | `www`       | `martynfagg.github.io.` |

Then in **Settings → Pages**, set the custom domain to `muphi.com` and tick **Enforce HTTPS** once the certificate provisions (can take up to ~24h). Full reference: [GitHub Pages custom domains](https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site).

---

## Previewing locally (optional)

Requires Ruby. From this folder:

```bash
bundle install
bundle exec jekyll serve --livereload
```

Then open <http://localhost:4000>.

---

## Where things live

| File / folder            | What it is |
|--------------------------|------------|
| `index.html`             | Homepage (hero, roles, about, writing, connect) |
| `_posts/`                | Your blog posts, one Markdown file each |
| `blog/index.html`        | The `/writing/` listing page |
| `_layouts/`              | Page templates (`default`, `post`) |
| `assets/css/main.css`    | All styling — colours, fonts, layout |
| `_config.yml`            | Site title, tagline, LinkedIn handle, settings |
| `CNAME`                  | Custom domain (`muphi.com`) |

To tweak the palette or fonts, edit the `:root` variables at the top of `assets/css/main.css`.
