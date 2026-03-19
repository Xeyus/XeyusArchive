# Limbus Archive Theme - Installation & Usage Guide

## Quick Start

### 1. Install Hugo

Make sure you have Hugo Extended version 0.120.0 or later:

```bash
# Check your Hugo version
hugo version

# Should output something like: hugo v0.120.0+extended
```

### 2. Create a New Hugo Site

```bash
hugo new site my-archive
cd my-archive
```

### 3. Install the Theme

**Option A: As a Git submodule (recommended)**

```bash
git init
git submodule add https://github.com/yourusername/limbus-archive.git themes/limbus-archive
```

**Option B: Clone directly**

```bash
git clone https://github.com/yourusername/limbus-archive.git themes/limbus-archive
```

### 4. Configure Your Site

Copy the example config:

```bash
cp themes/limbus-archive/exampleSite/config.toml config.toml
```

Edit `config.toml` to customize:

```toml
baseURL = "https://yoursite.com/"
title = "Your Archive Name"
theme = "limbus-archive"

[params]
  description = "Your description here"
  footer = "© 2025 Your Name"
```

### 5. Create Your First Post

```bash
hugo new posts/hello-world.md
```

Edit `content/posts/hello-world.md`:

```markdown
---
title: "Hello World"
date: 2025-03-18
categories: ["General"]
draft: false
---

Welcome to my archive!

## First Heading

This is my first post using the Limbus Archive theme.
```

### 6. Run the Development Server

```bash
hugo server -D
```

Visit `http://localhost:1313` to see your site!

## Content Organization

### Recommended Structure

```
content/
├── posts/          # Blog posts
│   ├── 2025/
│   │   └── my-post.md
│   └── _index.md
├── about/          # About page
│   └── index.md
└── links/          # Links/Blogroll
    └── index.md
```

### Creating Different Content Types

**Regular Post:**
```bash
hugo new posts/my-new-post.md
```

**About Page:**
```bash
hugo new about/index.md
```

**Links Page with Embossed Links:**

Create `content/links/index.md`:

```yaml
---
title: "Links"
layout: "links"
links:
  - name: "Hugo Documentation"
    url: "https://gohugo.io/"
    description: "Official Hugo docs"
  - name: "Anthropic"
    url: "https://anthropic.com/"
    description: "AI Safety & Research"
---

Here are some interesting links from around the web.
```

## Customization Guide

### Change Colors

Edit `static/css/main.css`:

```css
:root {
  --color-background: #DEDAC8;  /* Change background */
  --color-text: #2B2B2B;        /* Change text color */
  --color-border: #A19C8C;      /* Change borders */
  --color-accent: #802020;      /* Change accent (links) */
}
```

### Modify Fonts

1. Update the Google Fonts import in `layouts/_default/baseof.html`:

```html
<link href="https://fonts.googleapis.com/css2?family=Your+Font&display=swap" rel="stylesheet">
```

2. Update CSS variables:

```css
:root {
  --font-ui: 'Your Monospace', monospace;
  --font-body: 'Your Serif', serif;
}
```

### Adjust Layout Widths

In `static/css/main.css`, find `.site-container`:

```css
.site-container {
  grid-template-columns: 280px 1fr 280px;  /* Left / Center / Right */
  max-width: 1400px;  /* Maximum site width */
}
```

### Add Custom CSS

Create `static/css/custom.css` and add to `baseof.html`:

```html
<link rel="stylesheet" href="{{ "css/custom.css" | relURL }}">
```

## Advanced Features

### Enable Syntax Highlighting

In `config.toml`:

```toml
[markup.highlight]
  style = "monokailight"  # or "monokai", "github", etc.
  lineNos = true
  lineNumbersInTable = false
```

### Configure Table of Contents

```toml
[markup.tableOfContents]
  endLevel = 4      # Include up to H4
  startLevel = 2    # Start from H2
  ordered = false   # Use bullet points instead of numbers
```

### Add Custom Menus

```toml
[[menu.main]]
  name = "Archive"
  url = "/archive/"
  weight = 5

[[menu.main]]
  name = "Tags"
  url = "/tags/"
  weight = 6
```

### Set Pagination

```toml
paginate = 15  # Number of posts per page
```

## Deployment

### Build Your Site

```bash
hugo --minify
```

This creates a `public/` directory with your static site.

### Deploy to Netlify

1. Push your site to GitHub
2. Connect to Netlify
3. Build command: `hugo --minify`
4. Publish directory: `public`

### Deploy to GitHub Pages

1. Create `.github/workflows/hugo.yml`:

```yaml
name: Deploy Hugo site to Pages

on:
  push:
    branches: ["main"]

jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v3
        with:
          submodules: recursive
      - name: Setup Hugo
        uses: peaceiris/actions-hugo@v2
        with:
          hugo-version: 'latest'
          extended: true
      - name: Build
        run: hugo --minify
      - name: Deploy
        uses: peaceiris/actions-gh-pages@v3
        with:
          github_token: ${{ secrets.GITHUB_TOKEN }}
          publish_dir: ./public
```

## Troubleshooting

### Theme Not Found

```bash
# Make sure the theme is in themes/ directory
ls themes/limbus-archive

# Check config.toml has correct theme name
theme = "limbus-archive"
```

### Fonts Not Loading

Check your internet connection - fonts are loaded from Google Fonts CDN.

### TOC Not Showing

1. Make sure you have H2 or H3 headings in your content
2. Check `config.toml` has TOC enabled:

```toml
[markup.tableOfContents]
  startLevel = 2
  endLevel = 3
```

### RSS Feed Not Working

Enable RSS in `config.toml`:

```toml
[outputs]
  home = ["HTML", "RSS"]
  section = ["HTML", "RSS"]
```

## Tips & Best Practices

1. **Use meaningful H2/H3 headings** - They populate the TOC
2. **Keep categories consistent** - They appear in article metadata
3. **Write good summaries** - First ~70 words appear on the home page
4. **Optimize images** - Compress before adding to posts
5. **Test accessibility** - Use keyboard navigation to ensure everything works

## Support

- **Documentation**: [GitHub Wiki](https://github.com/yourusername/limbus-archive/wiki)
- **Issues**: [GitHub Issues](https://github.com/yourusername/limbus-archive/issues)
- **Discussions**: [GitHub Discussions](https://github.com/yourusername/limbus-archive/discussions)

---

Happy archiving! 📁
