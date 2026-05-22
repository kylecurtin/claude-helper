# Claude Helper

A free, beginner-friendly training site that walks anyone — from a total newcomer to a curious tinkerer — through getting started with Claude and Claude Code.

**Live:** [claude-helper-kc.web.app](https://claude-helper-kc.web.app)

The goal is a **0 → 100** path: create a Claude account, pick the right plan, install Claude Code, link GitHub, learn what's possible. Warm tone, plain language, no jargon, no upsell.

---

## Why this exists

I (Kyle) learned Claude Code, was floored, and wanted to put it into the hands of friends, family, and coworkers — without making them watch a 30-minute YouTube video or wade through reference docs. This is the guide I wish I'd handed people on day one.

## What's shipped (v0.1 — MVP)

- **Landing page** — warm editorial design, chapter list, author's note
- **Chapter 01** — Make your Claude account
- **Chapter 02** — Pick the right plan (Free / Pro / Max, honest framing)
- **Chapter 03** — Install Claude Code & link GitHub

## Roadmap

The MVP covers roughly **0 → 30**. To get to a full 0 → 100, next up:

- [ ] **Chapter 04 — Set up Google Cloud (free tier).** Account, project, free tier, what to enable, what to avoid.
- [ ] **Chapter 05 — A tour of what Claude Code can do.** Real examples: writing a Python script, refactoring code, summarizing a PDF, automating a small chore.
- [ ] **Chapter 06 — Habits of effective use.** Prompting style, when to push back, when to start over, version control.
- [ ] Real screenshots in every lesson
- [ ] A "share this with a friend" button + simple referral text
- [ ] Glossary page (CLI, terminal, repo, etc.)
- [ ] Troubleshooting page (common install / sign-in errors)
- [ ] Dark mode toggle (optional)

## Design

Aesthetic direction is **warm editorial / personal letter**, not corporate or AI-startup.

- **Type:** Instrument Serif (display) · Newsreader (body) · JetBrains Mono (code/labels)
- **Palette:** cream paper `#F5EFE3` · deep ink `#1C1611` · terracotta accent `#C4502A`
- **Texture:** subtle SVG paper grain overlay (multiply blend, low opacity)
- **Motion:** staggered fade-in on page load, IntersectionObserver-driven reveals on scroll

No build step — plain HTML/CSS/JS so anyone reading the source can follow along.

## Project structure

```
.
├── public/                     # everything Firebase serves
│   ├── index.html              # landing page
│   ├── styles.css              # all styles
│   ├── script.js               # scroll reveals
│   └── lessons/
│       ├── 01-create-account.html
│       ├── 02-pick-subscription.html
│       └── 03-setup-claude-code.html
├── firebase.json               # hosting config (cleanUrls, cache headers)
├── .firebaserc                 # pins project to claude-helper-kc
└── README.md
```

## Local development

No build step. Either:

```bash
# Quick: just open the file
open public/index.html

# Better: serve locally so cleanUrls (lessons/01-create-account) work like prod
firebase serve --only hosting
# then visit http://localhost:5000
```

## Deploy

```bash
firebase deploy --only hosting
```

That's it. The site goes live at https://claude-helper-kc.web.app on the next page load.

## Hosting & cost

Hosted on **Firebase Hosting Spark plan** (free tier). No billing enabled, no credit card on file. Free includes:

- 10 GB storage
- 360 MB/day egress (~10 GB/month)
- Free SSL on `*.web.app`
- Global CDN

The site must stay on Spark to keep the "$0 forever" promise. If you (future me, or another contributor) ever feel tempted to enable Blaze, custom domains with paid SSL, or Cloud Functions — pause and find a free alternative first.

## License

Personal project, all rights reserved for now. Reach out if you want to adapt it for your own community.

— Kyle Curtin · [@kylecurtin](https://github.com/kylecurtin)
