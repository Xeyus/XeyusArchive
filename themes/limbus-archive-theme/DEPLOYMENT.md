# Deployment Guide - Limbus Archive Theme

This guide covers various deployment options for sites using the Limbus Archive theme.

## Pre-Deployment Checklist

Before deploying your site, ensure:

- [ ] `baseURL` is set correctly in `config.toml`
- [ ] All content has `draft: false` (or use `hugo` instead of `hugo -D`)
- [ ] Images are optimized for web
- [ ] External links use HTTPS where possible
- [ ] Meta descriptions are set for SEO
- [ ] RSS feed is configured

## Build Your Site

```bash
# Production build with minification
hugo --minify

# Output will be in the 'public/' directory
```

## Deployment Options

### 1. Netlify

**Simplest option with automatic builds from Git**

#### Setup:

1. Push your Hugo site to GitHub/GitLab/Bitbucket
2. Log in to [Netlify](https://netlify.com)
3. Click "New site from Git"
4. Connect your repository
5. Configure build settings:
   - **Build command**: `hugo --minify`
   - **Publish directory**: `public`
   - **Environment variables**: `HUGO_VERSION = 0.120.0`

#### `netlify.toml` Configuration:

Create a `netlify.toml` in your site root:

```toml
[build]
  publish = "public"
  command = "hugo --minify"

[build.environment]
  HUGO_VERSION = "0.120.0"
  HUGO_ENV = "production"

[context.production.environment]
  HUGO_ENV = "production"

[context.deploy-preview]
  command = "hugo --minify --buildFuture -b $DEPLOY_PRIME_URL"

[context.branch-deploy]
  command = "hugo --minify -b $DEPLOY_PRIME_URL"

[[headers]]
  for = "/*"
  [headers.values]
    X-Frame-Options = "DENY"
    X-XSS-Protection = "1; mode=block"
    X-Content-Type-Options = "nosniff"
    Referrer-Policy = "strict-origin-when-cross-origin"

[[headers]]
  for = "*.css"
  [headers.values]
    Cache-Control = "public, max-age=31536000, immutable"

[[headers]]
  for = "*.js"
  [headers.values]
    Cache-Control = "public, max-age=31536000, immutable"
```

### 2. GitHub Pages

**Free hosting with GitHub Actions**

#### Setup:

1. Create `.github/workflows/hugo.yml`:

```yaml
name: Deploy Hugo site to Pages

on:
  push:
    branches: ["main"]
  workflow_dispatch:

permissions:
  contents: read
  pages: write
  id-token: write

concurrency:
  group: "pages"
  cancel-in-progress: false

defaults:
  run:
    shell: bash

jobs:
  build:
    runs-on: ubuntu-latest
    env:
      HUGO_VERSION: 0.120.0
    steps:
      - name: Install Hugo CLI
        run: |
          wget -O ${{ runner.temp }}/hugo.deb https://github.com/gohugoio/hugo/releases/download/v${HUGO_VERSION}/hugo_extended_${HUGO_VERSION}_linux-amd64.deb \
          && sudo dpkg -i ${{ runner.temp }}/hugo.deb
      
      - name: Checkout
        uses: actions/checkout@v4
        with:
          submodules: recursive
      
      - name: Setup Pages
        id: pages
        uses: actions/configure-pages@v4
      
      - name: Build with Hugo
        env:
          HUGO_ENVIRONMENT: production
          HUGO_ENV: production
        run: |
          hugo \
            --minify \
            --baseURL "${{ steps.pages.outputs.base_url }}/"
      
      - name: Upload artifact
        uses: actions/upload-pages-artifact@v3
        with:
          path: ./public

  deploy:
    environment:
      name: github-pages
      url: ${{ steps.deployment.outputs.page_url }}
    runs-on: ubuntu-latest
    needs: build
    steps:
      - name: Deploy to GitHub Pages
        id: deployment
        uses: actions/deploy-pages@v4
```

2. In your repo settings:
   - Go to Settings → Pages
   - Source: GitHub Actions

### 3. Vercel

**Fast edge network with preview deployments**

#### Setup:

1. Install Vercel CLI: `npm i -g vercel`
2. Run `vercel` in your project directory
3. Or connect via [vercel.com](https://vercel.com)

#### `vercel.json` Configuration:

```json
{
  "build": {
    "env": {
      "HUGO_VERSION": "0.120.0"
    }
  },
  "headers": [
    {
      "source": "/(.*)",
      "headers": [
        {
          "key": "X-Content-Type-Options",
          "value": "nosniff"
        },
        {
          "key": "X-Frame-Options",
          "value": "DENY"
        },
        {
          "key": "X-XSS-Protection",
          "value": "1; mode=block"
        }
      ]
    }
  ]
}
```

### 4. Cloudflare Pages

**Global CDN with excellent performance**

#### Setup:

1. Log in to [Cloudflare Pages](https://pages.cloudflare.com)
2. Connect your Git repository
3. Configure build settings:
   - **Build command**: `hugo --minify`
   - **Build output directory**: `public`
   - **Environment variables**: 
     - `HUGO_VERSION = 0.120.0`
     - `HUGO_ENV = production`

### 5. GitLab Pages

**Built into GitLab CI/CD**

#### Setup:

Create `.gitlab-ci.yml`:

```yaml
image: registry.gitlab.com/pages/hugo/hugo_extended:latest

variables:
  GIT_SUBMODULE_STRATEGY: recursive

pages:
  script:
    - hugo --minify
  artifacts:
    paths:
      - public
  rules:
    - if: $CI_COMMIT_BRANCH == $CI_DEFAULT_BRANCH
```

### 6. AWS S3 + CloudFront

**Enterprise-grade hosting**

#### Setup:

1. Build your site: `hugo --minify`
2. Create S3 bucket with static website hosting
3. Upload `public/` contents to S3
4. Create CloudFront distribution
5. Point your domain to CloudFront

Script for deployment:

```bash
#!/bin/bash
hugo --minify
aws s3 sync public/ s3://your-bucket-name --delete
aws cloudfront create-invalidation --distribution-id YOUR_DIST_ID --paths "/*"
```

### 7. Self-Hosted (VPS)

**Full control with Nginx/Apache**

#### Nginx Configuration:

```nginx
server {
    listen 80;
    server_name yourdomain.com;
    root /var/www/yoursite/public;
    index index.html;

    location / {
        try_files $uri $uri/ =404;
    }

    # Cache static assets
    location ~* \.(css|js|jpg|jpeg|png|gif|ico|svg|woff|woff2|ttf|eot)$ {
        expires 1y;
        add_header Cache-Control "public, immutable";
    }

    # Security headers
    add_header X-Frame-Options "DENY";
    add_header X-Content-Type-Options "nosniff";
    add_header X-XSS-Protection "1; mode=block";
}
```

Deploy script:

```bash
#!/bin/bash
hugo --minify
rsync -avz --delete public/ user@yourserver:/var/www/yoursite/public/
```

## Post-Deployment

### 1. Test Your Site

- [ ] All pages load correctly
- [ ] Navigation works
- [ ] RSS feed is accessible
- [ ] Images display properly
- [ ] Links are not broken
- [ ] Mobile responsive works
- [ ] No console errors

### 2. SEO Setup

**robots.txt** (auto-generated by Hugo):
```
User-agent: *
Disallow:

Sitemap: https://yourdomain.com/sitemap.xml
```

**Submit to search engines**:
- Google Search Console
- Bing Webmaster Tools
- Submit RSS feed to feed directories

### 3. Performance Testing

Test your site with:
- [PageSpeed Insights](https://pagespeed.web.dev/)
- [GTmetrix](https://gtmetrix.com/)
- [WebPageTest](https://www.webpagetest.org/)

### 4. Analytics (Optional)

If you want privacy-friendly analytics:

**Plausible Analytics** (`config.toml`):
```toml
[params]
  plausibleDomain = "yourdomain.com"
  plausibleScript = "https://plausible.io/js/script.js"
```

Add to `baseof.html` `<head>`:
```html
{{ if .Site.Params.plausibleDomain }}
<script defer data-domain="{{ .Site.Params.plausibleDomain }}" 
        src="{{ .Site.Params.plausibleScript }}"></script>
{{ end }}
```

## Continuous Deployment

Most platforms support automatic deployment on git push:

1. **Commit changes**: `git commit -am "Update content"`
2. **Push to remote**: `git push origin main`
3. **Platform auto-builds**: Your hosting service detects the push and rebuilds

## Troubleshooting

### Build Fails

- Check Hugo version matches requirements (0.120.0+)
- Ensure theme is properly installed as submodule
- Verify `config.toml` syntax

### CSS Not Loading

- Check `baseURL` is set correctly
- Ensure files are in `static/css/` not `assets/css/`
- Clear browser cache

### Images Not Showing

- Use relative paths: `/images/photo.jpg`
- Or use Hugo's image processing
- Check file names for case sensitivity on Linux servers

### RSS Feed 404

- Enable RSS in `config.toml` outputs
- Check feed URL: `https://yourdomain.com/feed.xml` or `/index.xml`

## Backup Strategy

**What to backup**:
- `content/` directory
- `static/` directory (images, files)
- `config.toml`
- Any customizations to the theme

**Git is your backup**: If everything is in Git, you have a complete history.

## Custom Domain Setup

### Netlify
1. Add custom domain in site settings
2. Configure DNS with your registrar
3. Enable HTTPS (automatic with Let's Encrypt)

### GitHub Pages
1. Add `CNAME` file to `static/` directory
2. Configure DNS A records to GitHub IPs
3. Enable HTTPS in repo settings

### Cloudflare Pages
1. Add custom domain in project settings
2. Cloudflare handles DNS automatically

---

**Ready to deploy?** Pick a platform and go live! 🚀
