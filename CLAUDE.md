# VAILL Faculty Guide to AI Agents

## Project Overview
MkDocs Material site for the Vanderbilt AI Law Lab faculty guide to AI agents.
Target audience: law faculty with little to no coding experience.

## Tech Stack
- MkDocs Material 9.7.2
- GitHub Pages (auto-deploy via GitHub Actions on push to main)
- Python 3.x for build

## Key Files
- `mkdocs.yml` — Site configuration, navigation, theme
- `docs/stylesheets/extra.css` — Vanderbilt black/gold color palette, Fraunces headings
- `overrides/main.html` — Custom header, footer, announcement bar
- `overrides/partials/header.html` — Header with clickable title
- `requirements.txt` — Python dependencies

## Branding
- Primary: `#1C1C1C` (header, nav bar)
- Accent: `#D4A843` (muted gold — links, highlights)
- Font: Inter (body), Fraunces (headings), JetBrains Mono (code)
- Logo: white filter on dark header (`filter: brightness(0) invert(1)`)

## Content Guidelines
- Use "we" voice (VAILL), never "I"
- Approachable but slightly formal — law faculty expect it
- Frame AI as augmentation, never replacement of legal judgment
- Include ethical considerations: ABA Rule 1.1, 1.6, hallucinated citations
- CSS classes: badge-gold (accent badges)
- Links styled with gold underline for visual distinction

## Navigation Structure
7 top-level tabs: Home, AI Essentials, What Are Coding Agents?, Setup, For Legal Practice, For Legal Academia, Build Your Own

## Local Development
```bash
pip install -r requirements.txt
mkdocs serve
```

## Deployment
Push to `main` triggers GitHub Actions → `mkdocs gh-deploy --force`
