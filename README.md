# Claude Helper

A free, beginner-friendly training site that walks anyone — from a total newcomer to a curious tinkerer — through getting started with Claude and Claude Code.

**Live:** [claude-helper-kc.web.app](https://claude-helper-kc.web.app)

The goal is a real **0 → 100** path: create a Claude account, understand the landscape, set up GitHub and your computer, install Claude Code, and learn the meta-skill of asking sharper questions. Warm tone, plain language, no jargon-without-definition, no upsell.

---

## Why this exists

I (Kyle) learned Claude Code, was floored, and wanted to put it into the hands of friends, family, and coworkers — without making them watch a 30-minute YouTube video or wade through reference docs. This is the guide I wish I'd handed people on day one.

## What's in the guide (v0.2 — 7 chapters)

1. **Make your Claude account** — sign up on claude.ai
2. **Pick the right plan** — the honest pitch for Max ($100/mo) as self-investment, with a stepped path for the uncertain
3. **The lay of the land** — what Anthropic, GitHub, and GCP each are
4. **Make a GitHub account & your first repo** — repositories explained, public vs private, hands-on creation
5. **Open your terminal & set up your Claude folder** — terminal basics + the `~/claude/project-name` habit
6. **Install Claude Code & link GitHub** — the hands-on chapter where everything clicks
7. **Asking Claude harder questions** — the meta-skill: board-of-directors reviews, roleplay critics, sharper thinking

## Roadmap

Currently at roughly **0 → 70**. To round out the full 0 → 100:

- [ ] Real screenshots in every lesson (currently text-only)
- [ ] A "share with a friend" CTA on the landing page
- [ ] A glossary page (CLI, terminal, repo, commit, branch, etc.)
- [ ] A troubleshooting page (common install / sign-in errors)
- [ ] A "what to build first" gallery — concrete project ideas matched to skill level
- [ ] A short habits chapter (prompting style, version control hygiene, knowing when to start over)
- [ ] Dark mode toggle (optional)
- [ ] Light analytics (privacy-respecting) so we can see which chapters lose people

## Design

Aesthetic direction: **warm editorial / personal letter** — not corporate, not generic AI-startup.

- **Type:** Instrument Serif (display) · Newsreader (body) · JetBrains Mono (code/labels)
- **Palette:** cream paper `#F5EFE3` · deep ink `#1C1611` · terracotta accent `#C4502A`
- **Texture:** subtle SVG paper grain overlay (multiply blend, low opacity)
- **Motion:** staggered fade-in on page load, IntersectionObserver-driven reveals on scroll

No build step — plain HTML/CSS/JS so anyone reading the source can follow along.

## Project structure

```
.
├── public/
│   ├── index.html                            # landing page
│   ├── styles.css
│   ├── script.js
│   └── lessons/
│       ├── 01-create-account.html
│       ├── 02-pick-subscription.html
│       ├── 03-lay-of-the-land.html
│       ├── 04-github-and-first-repo.html
│       ├── 05-terminal-and-folders.html
│       ├── 06-install-claude-code.html
│       └── 07-asking-harder-questions.html
├── firebase.json
├── .firebaserc                               # pins project to claude-helper-kc
└── README.md
```

## Local development

No build step. Either:

```bash
# Quick: just open the file
open public/index.html

# Better: serve locally so cleanUrls (e.g. lessons/03-lay-of-the-land) work like prod
firebase serve --only hosting
# then visit http://localhost:5000
```

## Deploy

```bash
firebase deploy --only hosting
```

The site goes live at https://claude-helper-kc.web.app on the next page load.

## Hosting & cost

Hosted on **Firebase Hosting Spark plan** (free tier). No billing enabled, no credit card on file. Free includes:

- 10 GB storage
- 360 MB/day egress (~10 GB/month)
- Free SSL on `*.web.app`
- Global CDN

The site must stay on Spark to keep the "$0 forever" promise. If anyone is ever tempted to enable Blaze, custom domains with paid SSL, or Cloud Functions — pause and find a free alternative first.

## Method note

This site has been refined by repeatedly asking Claude to roleplay critics. Chapter 07 documents the technique explicitly. Past virtual board reviews used Steve Wozniak (accessibility), Steve Jobs (narrative + ruthless editing), and Richard Feynman (pedagogy + honesty). If you ship a meaningful change, consider running another board before merging.

## License

Personal project, all rights reserved for now. Reach out if you want to adapt it for your own community.

— Kyle Curtin · [@kylecurtin](https://github.com/kylecurtin)
