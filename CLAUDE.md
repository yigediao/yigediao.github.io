# CLAUDE.md — Project Context for yigediao.github.io

This file records the project structure, design decisions, and conventions established for this site, so future Claude sessions can pick up where we left off.

## Site Overview

Personal research homepage for **Chao (Frank) Xie**, Ph.D. Candidate at the University of Florida.

- **URL**: https://yigediao.github.io
- **Repo**: https://github.com/yigediao/yigediao.github.io
- **Branch**: `main` (deploys directly via GitHub Pages)
- **Stack**: Single-file static site — everything lives in `index.html` (HTML + CSS + JS, no build step)

## Design System (established 2026-02-19)

The site was redesigned from a Minecraft pixel-art theme to a **clean academic style**.

### Typography
- Body / UI: **Inter** (Google Fonts, weights 300/400/500/600)
- Headings: **Lora** (Google Fonts, serif, weights 400/600 + italic)

### Color Palette (CSS variables in `:root`)
| Variable | Value | Usage |
|---|---|---|
| `--bg` | `#ffffff` | Page background |
| `--bg-alt` | `#f8f8f6` | Cards, info boxes |
| `--border` | `#e5e5e2` | Dividers, card borders |
| `--text` | `#1a1a1a` | Primary text |
| `--text-muted` | `#6b6b6b` | Secondary text, labels |
| `--accent` | `#2563eb` | Links, badges, progress bar |
| `--accent-light` | `#dbeafe` | Journal badge background |
| `--max-w` | `900px` | Max content width |

### Key CSS Classes
- `.section-label` — small-caps uppercase label above each section
- `.timeline li` — left-border timeline items (Education, Teaching)
- `.interest-list li` — arrow-prefixed list items (Research Interests)
- `.pub-item` — two-column layout: badge + content
- `.pub-badge` — blue (Journal) or green (Conference) pill badge
- `.card` — bordered card with hover shadow (Projects)
- `.hero-nickname` — smaller, muted style for "(Frank)" in the h1
- `.scroll-progress` — fixed 2px blue bar at top of viewport

## Page Structure & Section Order

```
Topbar (sticky nav)
└── Hero (name, bio, info box)
    ├── About (Advanced Robotics & Embodied AI)
    ├── Featured Project (video, id="projects")
    ├── Education (id="education")
    ├── Research Interests (id="interests")
    ├── Publications (id="publications")
    ├── Teaching (id="talks")
    └── Contact (id="contact")
Footer
```

> The Featured Project section was moved near the top intentionally so visitors see the demo video early.

## Content Notes

- **(Frank)** in the hero h1 is styled smaller and muted via `.hero-nickname` — keep this span when editing the name.
- Southwest Jiaotong University has **two separate B.E. degrees** on separate lines:
  - B.E. in Environmental Engineering
  - B.E. in Economics (International Economics and Trade)
- The About section label reads "Advanced Robotics & Embodied AI" (not "About").

## Deployment

```bash
git add index.html
git commit -m "..."
git push origin main
```

GitHub Pages serves from `main` branch root. Changes typically go live within 1–2 minutes.
