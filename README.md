# linkinbio-site

A single-page Hugo link-in-bio site. One config file, one data file — deploy anywhere in minutes.

## Quick start

1. Clone this repo
2. Edit `hugo.toml` with your name, description, and logo
3. Edit `data/links.yml` with your links
4. Run `hugo server` and open `http://localhost:1313`

## Configuration

Edit `hugo.toml`:

```toml
title = "Your Name"

[params]
  description = "Links and things I'm working on"
  favicon = "https://example.com/favicon.png"
  logo = "https://example.com/photo.png"
  # ga4 = "G-XXXXXXX"  # uncomment to enable Google Analytics
```

## Adding / editing links

Edit `data/links.yml`. Each category has a list of items:

```yaml
- category: Social
  items:
    - title: GitHub
      url: https://github.com/yourname
      icon: mdi:github           # optional — browse icons at https://icon-sets.iconify.design/
      tag: New                   # optional badge label
```

Items without a `url` render as a non-clickable button (useful for "coming soon" placeholders).

PDFs and other static files go in `static/assets/` and are referenced as `/assets/filename.pdf`.

You can also add an optional `description` or `enddescription` (Markdown) to any category:

```yaml
- category: Projects
  description: "Things I'm building."
  items: [...]
```

## Social icon bar

Edit `data/social.yml` to configure the horizontal icon row beneath your header:

```yaml
- name: github
  url: https://github.com/yourname
  icon: mdi:github
  color: "#333"
```

## Optional features

These partials exist but are commented out in `layouts/index.html`. Uncomment to enable:

- `theme-switch.html` — dark/light mode toggle
- `bio.html` — Instagram/TikTok/YouTube link-in-bio grid (reads from `data/bio.yml`)
- `footer.html` — copyright footer

## Deployment

Works with any static host. Cloudflare Pages settings:
- Build command: `hugo`
- Publish directory: `public`
