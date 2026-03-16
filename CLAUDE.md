# War Hares - CLAUDE.md

## What this site is
A humorous historian-style website for **WOCS 24-001**, a Warrant Officer Candidate School cohort that nicknamed themselves the **War Hares**. Mascot is **Rare O'Hare** - a battle-tested military hare. The tone is irreverent but respectful of military culture.

Built on **Jekyll 4.3** with a purchased Zerostatic/Jekyll Curate template, hosted on **Netlify**, deployed from the `main` branch.

## Tech stack
- Jekyll 4.3 + Bootstrap 5 grid
- SCSS: `_sass/theme/_variables.scss` (breakpoints), colors come from `_config.yml` → injected as CSS vars
- Fonts: DM Sans (self-hosted) + Fira Mono
- No JS framework - vanilla JS + Bootstrap

## Running locally
```bash
bundle install
bundle exec jekyll serve --livereload --port 4000
```
> Requires Ruby 3.4 compat gems (`csv`, `base64`, `bigdecimal`, `ostruct`) already in Gemfile.

## Site structure

| Path | Purpose |
|------|---------|
| `_config.yml` | All site config: title, colors, logo, nav toggles, footer |
| `_data/menu.yml` | Navigation menus (main, footer_primary, footer_secondary) |
| `_data/authors.yml` | Author bios (used by blog posts) |
| `_data/social.json` | Social media links shown in footer |
| `_data/contact.yml` | Contact info (currently all false/disabled) |
| `collections/_projects/` | **Hare profiles** - one .md per member |
| `collections/_posts/` | Blog posts / blurbs |
| `pages/` | Static pages (home, about, code, contact, etc.) |
| `_layouts/` | Page templates |
| `_includes/framework/` | Reusable partials (header, logo, footer, etc.) |
| `_sass/theme/` | SCSS - `_variables.scss`, `_custom.scss` |
| `assets/images/gen/projects/` | Hare profile images |

## Navigation
```
Home | Hares (/hares/) | The Story (/about/) | Code (/code/) | Playlist (/spotify/) | Blog (/blog/)
```

## Color scheme - pink & white (Energizer Bunny inspired)
Defined in `_config.yml` under `colors:`, injected as CSS variables:
- Background: `#ffffff` / `#fff5f8` / `#ffe8f0`
- Text: `#1a1a2e`
- Accent / hot pink: `#FF1493`
- Dark mode bg: `#1a0010` → `#280018`

## Hare profiles
Each member is a "Hare" - a file in `collections/_projects/`. Use `project-1.md` (Matt Burns / Hacker Hare) as the template. Key front matter fields:
```yaml
layout: project
title: "Full Name"
description: "Hare Nickname"
thumbnail: "/assets/images/gen/projects/<image>.png"
image: "/assets/images/gen/projects/<image>.png"
categories: ["Warhare"]
client: "Some funny value"
role: "MOS - Their role / title"
blurbs:
  - author: "Another Hare's name"
    text: "Quote or blurb about this person."
tattoos:
  - image: "/assets/images/gen/projects/<tattoo-image>.jpg"
    caption: "Optional caption."
```
Body content = bio/narrative paragraph(s).

## Key pages
- `/about/` - "The Story" - Rare O'Hare narrative (from WOCS Mascot & Description.docx)
- `/code/` - The War Hare Code (6 commandments, from GH issue #8)
- `/hares/` - Grid of all Hare profiles

## Open GitHub issues (as of 2024-09)
- #2 Create Profiles (more Hares)
- #3 Blogs/Blurbs page
- #4 Tattoos page
- #6 Enhancement (unspecified)
- #7 RSS feed
- #9 Spotify playlist
- #10 Improve CI/CD

## What NOT to do
- Do not reference Defense Unicorns or "UDS" - Matt no longer works there
- Do not re-enable the cookie banner
- Do not use the demo/placeholder Zerostatic template content
- Dark mode stays available as a toggle but light mode is the default
