# Copilot Instructions for personal-site.github.io

## Project Overview

This is a **Jekyll-based static site** hosting a COMP110 research analysis on whether lectures should be livestreamed. The site is published to GitHub Pages at `https://bedsand.github.io/comp110-livestream/`.

**Tech Stack:**
- Jekyll (static site generator)
- Minima theme (remote-theme: `jekyll/minima@1e8a445`)
- GitHub Pages
- Markdown for content

## Key Architecture

### File Organization
- **Content Pages**: `index.md`, `about.markdown` — main research findings using front matter (YAML) and Markdown
- **Layouts**: `_layouts/default.html` — single layout wrapping page content with `{{ content }}`
- **Components**: `_includes/*.html` — reusable HTML partials (header, footer, social, comments, etc.)
- **Assets**: `images/` — PNG charts referenced in Markdown (e.g., `![](images/chart1_distribution.png)`)
- **Configuration**: `_config.yml` — site metadata, theme settings, build plugins

### Data Flow
1. Markdown files (with YAML front matter) → Jekyll processes → uses `_layouts/default.html`
2. Layout includes `header.html` and conditionally includes footer/comments
3. `{{ content }}` placeholder replaced with rendered Markdown
4. Static HTML deployed to GitHub Pages

## Development Workflow

### Local Development
```bash
# Install dependencies
bundle install

# Start Jekyll development server (auto-reload on file changes)
bundle exec jekyll serve

# Clean build
bundle exec jekyll clean && bundle exec jekyll build
```

### Content Authoring
- **Front matter pattern**: All pages use YAML front matter (lines 1-5 in index.md: `layout`, `title`, optionally `permalink`)
- **Charts**: Stored as PNG images in `images/`; reference inline with `![alt](images/chartX_name.png)`
- **No MathJax enabled**: Commented out in `_layouts/default.html` (can uncomment if needed)

### Deployment
- Automatic: push to GitHub main branch → GitHub Pages builds and deploys
- No manual build step required (GitHub Pages runs Jekyll 232 with `github-pages` gem)

## Key Conventions

### Front Matter Structure
```yaml
---
layout: default  # or "page" for about.markdown
title: "Page Title"
permalink: /custom-path/  # optional; defaults to file structure
---
```

### Component Includes
- `{% include header.html %}` — site title header with optional nav
- Navigation is currently commented out (see `_includes/header.html` line 11-15)
- Footer and sub-footer are commented out in default layout (line 20-21)

### Theme Customization
- **Theme source**: Remote `jekyll/minima@1e8a445` — custom includes override remote theme
- **Custom head**: `_includes/custom-head.html` for additional meta tags or scripts
- **Analytics**: `_includes/google-analytics.html` available (not currently active)

## Common Tasks

| Task | Approach |
|------|----------|
| Add new page | Create `.md` or `.markdown` file with front matter; layout will auto-render |
| Update header/nav | Edit `_includes/header.html` |
| Add inline styles/scripts | Modify `_includes/custom-head.html` or specific layout |
| Deploy | Push to main branch; GitHub Pages handles build |
| Test locally | `bundle exec jekyll serve` and visit `http://localhost:4000/comp110-livestream/` |
| Add new chart | Save PNG to `images/`, reference in Markdown as `![alt](images/chartN_name.png)` |

## Integration Points

- **GitHub Pages**: Builds via `Gemfile` with `github-pages ~> 232`
- **Minima Theme**: Provides CSS/JS/default layouts; overridable via `_includes/` and `_layouts/`
- **Jekyll Plugins**: Currently only `jekyll-remote-theme` active (disabled: `jekyll-feed`)

## Developer Notes

- **Baseurl**: Set to `/comp110-livestream` — all relative links must account for this
- **No custom plugins** — standard Jekyll + Minima theme only
- **Minimal JS**: No frontend framework; pure HTML/CSS/Liquid templating
- **Git tracking**: `.gitignore` excludes typical Jekyll build artifacts (`.sass-cache/`, `.jekyll-cache/`)
