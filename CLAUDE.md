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

                     # NOTE: the whole Projects system is retired. The _projects
                     # collection, _layouts/project.html and the collections: block
                     # went 2026-08-25; projects.md and _data/projects.yml went
                     # 2026-08-29. All of it duplicated the research page and none of
                     # it was in the nav. Files sit in _to_delete/ until removed by hand.

_includes/
  nav.html           # Header: image (40% left) + nav panel (right)
  footer.html        # Copyright + "Built with Jekyll" attribution
  person-card.html   # Avatar, name, role, email, website, interests
  pub-item.html      # Title (linked), authors, venue, year, DOI, PDF, tags
  news-item.html     # Date, title, text, optional "Read more" link (field: url)
  addgene-widget.html # Addgene kit widget, included by the Part Kits section of research.md

_data/               # YAML content files — edit these to update site content
  people.yml         # PI, students, staff, alumni
  publications.yml   # All publications (journal, preprint, book-chapter)
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
  research.md        # The .rmap map + collapsed Research Areas / Applications / Resources
  people.md          # Renders people.yml into card grids
  publications.md    # Renders publications.yml grouped by year/type
  news.md            # Renders news.yml newest-first via news-item.html include
  join.md            # Recruitment info for PhD, undergrad, postdoc, collaborators
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

### Page colour keying
**The nav tab colour keys the page.** Each page uses its tab colour as its accent;
other palette colours appear only where genuinely needed, and sparingly.

| Page | Key colour |
|---|---|
| Home | `--red` |
| Research | `--orange` |
| People | `--green` |
| Publications | `--navy` |
| Join | `--blue` |

On the research page that means orange carries the group labels, section borders,
headings, the +/− markers, and the map chips.

**Links take the colour of where they lead.** The paper links on the research page
are navy because they go to publications, and Publications is the navy page. That
is the rule, not a contrast workaround. It also happens to read well: orange at
body size on cream is 2.81:1 and would not hold as link text.

Red, green and blue do not appear on the research page at all; the site-wide
`a{color:var(--blue)}` is overridden by `.research-section a`.

Do not "fix" orange headings to navy for contrast. That is a deliberate choice.

### Header Layout
- Flex row: `young_header.png` on the left (40% width, height auto), nav panel on the right
- Site title: DM Serif Display, cream (`--bg`) on WPI Red (`--red`) background
- Nav tabs: colored backgrounds per tab; active page underline matches tab color via `--tab-border` CSS variable

### Research Page — the map is the page
**Rebuilt 2026-08-25.** The navy map carries the page; everything below it is a
collapsed `<details>`. No `.pub-nav` row.

**Inside the navy panel** (`.rmap`), top to bottom: `.rmap-cap` capability line
(DM Serif, white) · **Research Areas** band, four orange chips, label above ·
**Applications** band, five cream chips, label **below** the row so the arcs,
which land on chip tops, never cross it · **Get Our Parts and Tools** row of
outlined white pills · **Current Funding** line · the hover note.

**Four Research Areas** — `#onboarding`, `#metabolic-engineering`, `#circuits`
(Genetic Circuits), `#biofoundries`.

**Five Applications**, each its own card — `#app-soil-sensing`,
`#app-biomanufacturing`, `#app-medicines`, `#app-biomaterials`,
`#app-biosecurity`. Each lists the areas that feed it, and **those links must
match the `EDGES` array** in the inline script. Eleven edges, checked both ways.

**Funding and Experience** (`#funding`) — three tiers. Current as solid navy
pills (`.fund-now`), Past as a quiet tan-ruled list (`.fund-past`), and
Fellowships separately, labelled *"Awarded to trainees, not to the lab."*
Fellowships are the trainee's award, not the lab's; do not merge them into Past.

**Resources** — three cards: `#part-kits`, `#software-projects`, `#organizations`.

**Papers are inline links on the claims they support**, not citation lists. An
earlier version generated a publication list per area with Liquid; it read as a
second copy of the publications page and was removed. Full citations live on
`publications.md`. Of the area-tagged papers, all but one are linked in prose —
audit with: every `doi` in `publications.yml` that has `areas` should appear in
`research.md`.

**Prose structure.** One organism per paragraph with a bolded lead-in
(Metabolic Engineering), and named facilities integrated into the paragraph
whose claim they support — CREATE under Automation, BioHub under Scale. Do not
add standalone `<h3>` blocks for organisations; they read as disconnected.

**Collaborations are a rule, not a group.** Each area names who it works with in
a `.rs-collab` line. Do not create a Collaborations section.

**Collapsed sections.** `<details class="research-section">` with an `<h2>` in
`<summary>` and a +/− marker. Any in-page link opens its target `<details>`, and
a deep link like `/research/#biosecurity` opens on load.

Arcs hide and bands stack below 900px. `draw()` uses the same 900px gate, and
also bails when either chip row wraps, because the arc geometry assumes one line
per row. `prefers-reduced-motion` kills transitions.

Focus rings: orange chips take a white border; cream Application chips take an
orange `outline` with a 2px offset. A navy border on a cream chip is invisible —
it merges into the navy panel behind it. Verified 2026-08-28.

- Prose is Eric's own text, recut. Do not rewrite it without asking; the register
  is deliberate (peers and collaborators, method first, no premise-explaining).
- The Projects system is retired (2026-08-29). Do not recreate `projects.md`,
  `_data/projects.yml`, or a `_projects` collection. Research areas and
  applications live on `research.md` and nowhere else.
- Two different Massachusetts funders, and they are not interchangeable. The
  **BioHub** was launched with $5.2M from the **Massachusetts Technology
  Collaborative**. **CERES** came from the **Massachusetts Life Sciences Center**
  Building Breakthroughs award. Corrected by Eric 2026-08-28 after an audit
  wrongly called them one inconsistency.
- The Genetic Circuits section is knowingly the thinnest-sourced on the page: the
  patent is the only citation. It stays as written until the DARPA-cleared
  preprint lands. Do not paper over it. Decided 2026-08-28.

### Publication tagging
Two independent fields on each `_data/publications.yml` entry, added 2026-08-25:

```yaml
areas:   [onboarding, metabolic-engineering, circuits, biofoundries]   # 0+, subject
context: [training, collaboration]                                      # 0+, provenance
```

`biofoundries` is the whole area — software and bioinformatics, automation, and
scale. Bioinformatics work belongs here; there is no separate slug for it. The
*Candida auris* paper is `biofoundries` because it was a PRYMETIME collaboration,
not because it is foundry infrastructure. Confirmed by Eric 2026-08-29.

**Rule: a training publication never carries an area.** Training means Eric's own
doctoral and postdoctoral work, before the lab. Those papers appear only in the
Prior work section, never under a research area.

Current counts: onboarding 8, biofoundries 11, metabolic-engineering 6,
circuits 2. Context: 13 training, 12 collaboration, 14 current lab.
Verified 2026-08-29.

**Rule: `areas` records why the lab was in the room, not what technique it used.**
Settled by Eric 2026-08-29 after this exact case came up twice.

- *C. auris* (Rao), probiotic yeast (Rao), episomal plasmids (Vickers) →
  `biofoundries`, because genome reading *was* the contribution.
- *K. delftensis*, *O. polymorpha* → `onboarding` only. Those genomes were built
  to onboard a yeast. PRYMETIME was incidental, so it earns no tag.

Do not retag the two reference genomes to `biofoundries`. It was proposed and
rejected 2026-08-29; the technique is not the reason.

**PRYMETIME usage is a separate record from the tags.** The Software Projects
section lists what the tool has done, in four groups: the *K. delftensis* and
*O. polymorpha* reference genomes, IARPA FELIX detection, the two Rao papers,
and the Vickers plasmid work. That list is not `areas` and does not have to
match it. PRYMETIME does not do transcriptomics, so the *X. dendrorhous* omics
onboarding and the oleaginous-yeast comparative transcriptomics papers are not
on it. The Vickers collaboration is finished &mdash; do not write it as ongoing.
Circuits is thin because the fungal-highways results are patented and the
preprint is pending DARPA approval.

The old `projects:` field is gone — it pointed at the deleted `_projects` pages.

### Publications page
Three sections, built by pushing into three arrays in one pass:
1. **Current work** — everything not training and not a review/chapter. Numbered,
   grouped by year.
2. **Reviews and perspectives** (`#reviews`) — reviews and book chapters, not
   training. Six entries.
3. **Prior work** (`#prior-work`) — everything tagged `context: training`.

Reviews deliberately do NOT get a section on the research page: a review is not a
result, and the research page is kept to the map plus collapsed strips.

### Area publication lists
Each research area's `<details>` ends with a Liquid block:
`where_exp: "p", "p.areas contains '<slug>'"`, rendered with `pub-item.html`.
Verified against a real build 2026-08-25: 8 / 6 / 2 / 8, no unrendered Liquid.

- `Software Projects` under Resources lists **PRYMETIME only**
  (github.com/emyounglab/prymetime). The other repos in the emyounglab org are
  paper supplements, not projects — do not list them. SBKS is Myers' project, not
  the lab's repo; it is described in the Software and Bioinformatics area instead.
- Author-name convention: Cassandra publishes under both Brzycki and Newton. All
  `publications.yml` entries use **C. Newton** so one person does not read as two.
  `people.yml` keeps the fuller "Dr. Cassandra Brzycki Newton" so readers who knew
  the earlier name can connect them.

### Home Page (`index.md`)
- **Palette stripe** — 17px tall bar of five skewed parallelogram segments (red, orange, green, navy, blue) at top of content; uses `.palette-stripe` with five `<span>` children (`.ps-red`, `.ps-orange`, `.ps-green`, `.ps-navy`, `.ps-blue`)
- **Focus badges** — four solid-fill pill links to research sections; cream text on colored backgrounds (`.focus-badge` + `.badge-orange/blue/green/navy`)
- **Lead paragraph** — `.lead` has `--line` warm tan background with padding and rounded corners
- **Dividers** — `<hr class="palette-rule"/>` renders as a 2px gradient line across the full palette

---

## Writing register — Eric's voice

Derived from his own research summary and proposal text, 2026-08-29. The site's
prose should read as his. Match these, and do not "improve" past them.

**Do**

- Open with "We have developed…" and repeat the stem. He does not vary it for elegance.
- Use `can` as the capability verb: can grow, can support, can be transformed.
  Reserve `may` for real uncertainty.
- Gloss by apposition or parentheses: "the halotolerant yeast *D. hansenii*",
  "*Cupriavidus necator* (a potential platform host for biomaterial production
  from CO<sub>2</sub>)".
- Connect and conclude with `Thus,` `In fact,` `Furthermore,` `For example,`.
- State necessity flatly: "is necessary", "must have", "took a great deal of".
- Open a section with a problem statement when there is one — "Engineered model
  organisms rarely become commercially viable biofuel factories" — followed
  immediately by the mechanism.
- Repeat a distinctive word rather than swapping a synonym. His word is
  **actual** dry soil, not "real".
- End with significance when earned: "Thus, *D. hansenii* is an ideal organism for…".
- Keep his terms of art intact: "high-throughput combinatorial pathway
  engineering", "broad host range plasmid", "on-demand manufacture".

**Do not**

- Address the reader as "you", or ask a rhetorical question.
- Use antithesis for effect: "grown rather than manufactured", "invented at the
  bench rather than shipped elsewhere", mirrored clauses.
- Use an aphoristic opener with rhetorical timing ("X is only half the problem —").
- Use em-dashes for timing. He uses them almost never; parentheses instead.
- Write verbless labels or fragments as sentences.
- Use `lets` where he uses `enables`.
- Write empty bridge sentences ("The yeast work points the same way").
- Balance list items into matching grammatical shapes for their own sake.
- Hedge a claim he would assert.

**Passages that are near-verbatim his — never copyedit them.** The Genetic
Circuits paragraph; "Our key strategy is merging bioinformatics…"; the bacteria
part-library sentence; the *D. hansenii* and *X. dendrorhous* entries under
Metabolic Engineering; the first two sentences of Software and bioinformatics.
An edit to any of these is a rewrite request, not a copyedit — ask first.

A fuller sample lives outside the repo. Ask Eric for it before a prose pass.

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

### Adding a research area or application (`research.md`)
Both are plain HTML in `research.md` — no collection, no data file. Each is a
`<details class="research-section" id="...">` with `<summary><h2>Title</h2></summary>`,
one or more `<p>`, and for an application a `.project-links` list naming the
research areas it draws on. A new chip also needs an entry in the `EDGES` array
in the inline `<script>`, or it will have no arcs.
Then add a chip to the matching `.rmap-band` and an entry to the `EDGES` array in
the script. Keep anchor IDs stable.

---

## PI Contact

Eric M. Young — Associate Professor, Chemical Engineering, WPI
emyoung@wpi.edu | GP 4003, Life Sciences & Bioengineering Center, Gateway Park
