# Young Lab Website — CLAUDE.md

## Project Overview

Jekyll-based GitHub Pages site for the Young Lab at Worcester Polytechnic Institute.
URL: https://emyounglab.github.io

**Research focus:** Synthetic biology, metabolic engineering, nonconventional yeasts, microbial communities, biosensors.

---

## Local Development

```bash
bundle install
bundle exec jekyll serve --future --force_polling
# Visit http://localhost:4000
```

`--future` shows future-dated posts (also enabled via `future: true` in _config.yml).
`--force_polling` is required on Windows (Git Bash) for file-change watching to work.

Build only:
```bash
bundle exec jekyll build
# Output in _site/
```

**Note:** Always use `bundle exec` — do not run `jekyll` directly, as it may use a different system version.

---

## Project Structure

```
_config.yml          # Site title, URL, plugins, future: true
Gemfile              # Ruby gem dependencies (github-pages ~> 232, minima ~> 2.5)

_layouts/
  default.html       # Master template (Google Fonts, OG tags, favicon, nav + footer)
  page.html          # Extends default; adds page title/subtitle header
  project.html       # Extends default; shows title, body content, and related publications pulled from publications.yml

_projects/           # Individual project pages (Jekyll collection); filename slug matches projects key in publications.yml
  *.md               # Front matter: layout: project, title, theme (cell-factories|tools|etc.); body is free-form markdown

_includes/
  nav.html           # Header: image (40% left) + nav panel (right)
  footer.html        # Copyright + "Built with Jekyll" attribution
  person-card.html   # Avatar, name, role, email, website, interests
  project-card.html  # Title, status, summary, highlights, tags, URL
  pub-item.html      # Title (linked), authors, venue, year, DOI, PDF, tags
  news-item.html     # Date, title, text, optional "Read more" link (field: url)

_data/               # YAML content files — edit these to update site content
  people.yml         # PI, students, staff, alumni
  publications.yml   # All publications (journal, preprint, book-chapter)
  projects.yml       # Active research projects (4 areas)
  news.yml           # News items (sorted newest-first on news.md)

assets/
  css/style.css      # Custom CSS; CSS variables for theming
  img/
    young_header.png # Header image (40% width, left side of nav)
    people/          # Person photos
    logos/
      wpi_logo.png   # WPI logo (available for use in layouts)
    favicon/         # Full favicon set — all wired into default.html <head>
      favicon.ico
      favicon.svg
      favicon-96x96.png
      favicon.png
      apple-touch-icon.png
      web-app-manifest-192x192.png
      web-app-manifest-512x512.png
      site.webmanifest

Pages (Markdown):
  index.md           # Home: lead paragraph + 3 most recent publications (dynamic)
  research.md        # Four research area section cards + techniques list
  people.md          # Renders people.yml into card grids
  publications.md    # Renders publications.yml grouped by year/type
  projects.md        # Renders projects.yml as card grid
  news.md            # Renders news.yml newest-first via news-item.html include
  join.md            # Recruitment info for PhD, undergrad, postdoc, collaborators
  contact.md         # Eric Young's contact info + external profile links
```

---

## Design System

### Fonts (Google Fonts)
- **Body:** DM Sans (400, 500)
- **Headings & site title:** DM Serif Display

### Colors (CSS variables in style.css)
Palette inspired by the Time Variance Authority (TVA) from Loki — retro-bureaucratic, mid-century modern feel.

| Variable | Value | Usage |
|---|---|---|
| `--red` | `#AC2B37` | WPI Red — site title, header bg, lead paragraph bg, person card border |
| `--orange` | `#C97720` | TVA burnt orange — page titles, research section headings and borders, back links |
| `--green` | `#556B4A` | Dark sage — people page headings, person card borders, research nav buttons |
| `--navy` | `#1E2E4A` | Deep navy — body headings, footer border, pub section headers, tab active underline |
| `--blue` | `#5E8FAF` | Dusty slate blue — links, pub numbers, year stamps, join tab |
| `--fg` | `#1a1a1a` | Body text |
| `--muted` | `#6B6457` | Secondary text (roles, authors, meta) |
| `--bg` | `#F8F5EF` | Page background (warm off-white) |
| `--bg2` | `#EDE9E2` | Warm cream — cards, footer background, light text on dark backgrounds |
| `--line` | `#D4CCBF` | Warm tan — borders, dividers |

### Header Layout
- Flex row: `young_header.png` on the left (40% width, height auto), nav panel on the right
- Site title: DM Serif Display, cream (`--bg`) on WPI Red (`--red`) background
- Nav tabs: colored backgrounds per tab; active page underline matches tab color via `--tab-border` CSS variable

### Research Page
- Four `.research-section` cards, each with a unique left border color keyed by ID:
  - `#cell-factories` → orange
  - `#biosensors` → blue
  - `#nonconventional-yeasts` → sage green
  - `#microbial-communities` → navy
- Card titles: WPI Red; base border color is orange (overridden per ID)

### Home Page (`index.md`)
- **Palette stripe** — 17px tall bar of five skewed parallelogram segments (red, orange, green, navy, blue) at top of content; uses `.palette-stripe` with five `<span>` children (`.ps-red`, `.ps-orange`, `.ps-green`, `.ps-navy`, `.ps-blue`)
- **Focus badges** — four solid-fill pill links to research sections; cream text on colored backgrounds (`.focus-badge` + `.badge-orange/blue/green/navy`)
- **Lead paragraph** — `.lead` has `--line` warm tan background with padding and rounded corners
- **Dividers** — `<hr class="palette-rule"/>` renders as a 2px gradient line across the full palette

---

## Key Conventions

- **CSS variables** in `:root` — always edit variables rather than hardcoding colors
- **Liquid indentation:** Do NOT indent Liquid tags with 4+ spaces in `.md` files — Markdown treats 4-space indentation as a code block. Use flush-left Liquid and `<h2>`/`<h3>` tags instead of `##` inside loops.
- **Responsive breakpoint:** 900px (grids collapse to single column)
- **Navigation links** are hardcoded in `_includes/nav.html`
- **No custom plugins** — must remain GitHub Pages safe (`plugins: []` in _config.yml)
- **Permalink style:** `pretty` (e.g., `/people/` not `/people.html`)
- **alumni** `current_position:` field in people.yml uses key `current:`

---

## Content Management

### Adding a person (`_data/people.yml`)
```yaml
- name: "First Last"
  role: "PhD Student"          # or Postdoctoral Researcher, Undergraduate, etc.
  email: "user@wpi.edu"        # optional
  website: "https://..."       # optional
  photo: "/assets/img/people/filename.jpg"  # optional
  interests: "topic one, topic two"         # optional string
```
Alumni go under the `alumni:` key with `current:` for their current position.

### Adding a publication (`_data/publications.yml`)
```yaml
- title: "Paper Title"
  authors: "Last A, Last B, Young EM"
  venue: "Journal Name"
  year: 2026
  type: journal                # journal | preprint | book-chapter
  doi: "10.xxxx/xxxxx"        # shown as text; title links to url
  url: "https://doi.org/..."   # link on title
  pdf: "/assets/pdf/..."       # optional
  tags: ["yeast", "CRISPR"]   # optional
```

### Adding a news item (`_data/news.yml`)
```yaml
- date: "2026-03-01"
  title: "News headline"
  text: "Short description."
  url: "https://..."           # optional "Read more" link
```

### Adding a project (`_data/projects.yml`)
```yaml
- title: "Project Name"
  status: "Active"
  summary: "One paragraph description."
  highlights:
    - "Key point one"
  tags: ["tag1", "tag2"]
  url: "https://..."           # optional
```

### Adding an individual project page (`_projects/`)
Create a new `.md` file in `_projects/` — the filename slug (without `.md`) must match the value used in the `projects:` field of `publications.yml` so that related publications are auto-linked.

```yaml
---
layout: project
title: "Project Name"
theme: cell-factories   # cell-factories | tools | (other theme identifiers)
---

Free-form markdown content describing the project in detail.
```

Publications that list this project's slug in their `projects:` array will appear automatically in a "Publications" section at the bottom of the page.

---

## PI Contact

Eric M. Young — Associate Professor, Chemical Engineering, WPI
emyoung@wpi.edu | GP 4003, Life Sciences & Bioengineering Center, Gateway Park
