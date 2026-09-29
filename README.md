# Cloud Native PDX website

The website for the Cloud Native PDX meetup — a custom [Jekyll](https://jekyllrb.com/)
theme built to run on **GitHub Pages**. It provides a static home page and a
simple blog.

The theme's colors (green, blue, yellow) were extracted from the logo artwork in
[`/images`](images).

## Structure

```
├── _config.yml          Site configuration
├── index.md             Home page content (logo + text + links)
├── blog.md              Blog listing page
├── _posts/              Blog posts (one Markdown file per post)
├── _data/
│   ├── navigation.yml   Top navigation bar links
│   └── links.yml        Home page link cards (the 6–7 links)
├── _layouts/            Page templates (home, blog, post, page, default)
├── _includes/           Reusable partials (head, header, footer)
├── _sass/               Stylesheet source (colors live in _variables.scss)
├── assets/css/style.scss  Compiles to the site stylesheet
└── images/              Logos and post photos
```

## Editing content

Everything below is plain text/Markdown — no coding required.

### Home page

- **Logo** — replace `images/emblem.png` (or change `logo:` in `_config.yml`).
- **Text** — edit the Markdown body of `index.md`.
- **Heading / subtitle** — edit the `heading:` and `subtitle:` fields at the
  top of `index.md`.
- **The 6–7 links** — edit `_data/links.yml`. Each entry supports:

  ```yaml
  - title: Upcoming Events        # required
    url: "https://example.com"    # required (full URL or /site-relative path)
    description: Short supporting text   # optional
    icon: "📅"                    # optional emoji/badge
    external: true                # optional — open in a new tab
  ```

### Blog

Add a Markdown file to `_posts/` named `YYYY-MM-DD-title.md`:

```markdown
---
layout: post
title: "My post title"
date: 2026-09-22 09:00:00 -0700
author: Your Name
image: /images/my-photo.jpg        # optional photo
image_alt: "Description of photo"  # optional
image_caption: "Caption text"      # optional
---

Your post content in Markdown...
```

#### How to add a new post

1. Create a Markdown file in the `_posts/` folder.
2. Name it `YYYY-MM-DD-a-short-title.md` (the date drives the post's URL and
   ordering).
3. Add the front matter block at the top — copy the one at the top of this file
   as a starting point.
4. Write your post below the front matter using regular Markdown.

#### Adding a photo

Drop an image into the `/images` folder and reference it in the front matter:

```yaml
image: /images/my-photo.jpg
image_alt: "A short description of the photo"
image_caption: "An optional caption shown under the photo"
```

The photo appears at the top of the post and as the thumbnail on the blog
listing page.

#### Formatting

You get everything Markdown offers — **bold**, _italic_, [links](/), lists,
and code:

```bash
kubectl get pods -A
```

> Pull-quotes and callouts look like this.🎉

### Navigation

Edit `_data/navigation.yml` to change the top menu.

### Colors

All theme colors are defined in `_sass/_variables.scss`.

## Running locally

```bash
bundle install
bundle exec jekyll serve
```

Then open <http://localhost:4000>. GitHub Pages builds the site automatically
when you push to the configured branch — no build step required.
