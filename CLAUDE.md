# VAILL Coding Agents Workshop

## Project Overview
MkDocs Material site for the Vanderbilt AI Law Lab coding agents workshop.
Target audience: law faculty with little to no coding experience.

## Tech Stack
- MkDocs Material 9.7.2
- GitHub Pages (auto-deploy via GitHub Actions on push to main)
- Python 3.x for build

## Key Files
- `mkdocs.yml` — Site configuration, navigation, theme
- `docs/stylesheets/extra.css` — Vanderbilt gold/black color palette
- `overrides/main.html` — Custom header, footer, announcement bar
- `overrides/partials/header.html` — Header with clickable title
- `requirements.txt` — Python dependencies

## Branding
- Vanderbilt Gold: `#ECB748` (accent), `#CFAE70` (muted gold for display)
- Vanderbilt Black: `#1C1C1C` (primary)
- Font: DM Sans (body), Fraunces (headings), JetBrains Mono (code)

## Content Guidelines
- Use "we" voice (VAILL workshop), never "I"
- Approachable but slightly formal — law faculty expect it
- Frame AI as augmentation, never replacement of legal judgment
- Include ethical considerations: ABA Rule 1.1, 1.6, hallucinated citations
- Workshop session admonitions on content pages
- CSS classes: badge-gold (not badge-teal), workshop admonition

## Navigation Structure
7 top-level tabs: Home, AI Essentials, What Are Coding Agents?, Setup, For Legal Practice, For Legal Academia, Build Your Own

## Local Development
```bash
pip install -r requirements.txt
mkdocs serve
```

## Deployment
Push to `main` triggers GitHub Actions → `mkdocs gh-deploy --force`
