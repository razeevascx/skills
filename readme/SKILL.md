---
name: readme
description: Generate professional, visually polished GitHub README files for any project. Use this skill whenever the user wants to create, write, or improve a README, generate project documentation, or produce a GitHub profile/repo overview. Trigger on phrases like "write a README", "create docs for my project", "generate README.md", "make my project documentation", "help me document my project", or any request to create or improve project documentation files. Even if the user only says "document this" or "make a README for this code", use this skill.---


# Essential README Structure


Produce complete, professional `README.md` files for any project — from quick personal scripts to production open-source libraries. The output should be visually polished (centered header, badges, tech stack icons) and precisely scoped to what the project actually contains.

---


## Step 1: Gather Project Information

Before writing anything, collect the facts you need. Check the conversation for already-provided context first — don't ask for things the user already supplied.

**Auto-detect from files when available:**

| Signal | What to look for |
|--------|-----------------|
| Language / framework | `package.json`, `requirements.txt`, `pyproject.toml`, `Cargo.toml`, `pom.xml`, `go.mod`, `composer.json`, file extensions |
| Project name | Repo name, top-level directory name, `name` field in manifest |
| License | `LICENSE` or `LICENSE.md` file |
| Scripts / entry points | `scripts` in `package.json`, `Makefile`, `Dockerfile` |
| Live demo / URL | `homepage` in `package.json`, mentions in existing docs |

**Ask the user only for what you can't infer:**
- What problem does this project solve? (one sentence)
- Who is the target user?
- Is there a live demo or screenshot to include?
- Any support/contact channels?

Keep questions to a minimum — one focused ask is better than a checklist.

---

## Step 2: Build the README

Assemble the sections below **in order**, including only sections that are relevant and present in the project. Omit sections that don't apply (e.g., no license file → no License section).

---

### Section 1 — Project Header (always include)

```markdown
<div align="center">

# PROJECT NAME

*One-line value proposition — what it does and why it matters*

![Last Commit](https://img.shields.io/github/last-commit/USERNAME/REPO?style=for-the-badge&logo=git&logoColor=D9E0EE&labelColor=1E202B&color=8ad7eb)
![TypeScript](https://img.shields.io/badge/typescript-100%25-blue?style=flat-square)
![Languages](https://img.shields.io/github/languages/count/YOUR-USERNAME/vue?label=languages&color=orange&style=flat-square)


**Built with:**

![React](https://img.shields.io/badge/React-1E202B?style=for-the-badge&logo=react&logoColor=61DAFB)
![TypeScript](https://img.shields.io/badge/TypeScript-1E202B?style=for-the-badge&logo=typescript&logoColor=3178C6)
![Node.js](https://img.shields.io/badge/Node.js-1E202B?style=for-the-badge&logo=nodedotjs&logoColor=339933)

</div>
```

**Two distinct badge types — understand the difference:**

**Stat badges** (last commit, stars, repo size, forks, license):
- `style=for-the-badge`
- `labelColor=1E202B` — dark charcoal, always the same across ALL stat badges
- `logoColor=D9E0EE` — soft off-white, always the same across ALL stat badges
- `color=ACCENT` — the value pill color; vary these across badges for visual interest using a cohesive palette (e.g. `8ad7eb` → `86dbd7` → `86dbce` → `86dbc0`, a teal-to-mint gradient)
- Logo: a fitting generic icon (git, andela, protondrive, etc.) — NOT the tech brand icon

**Tech / "Built with" badges:**
- `style=for-the-badge`
- Background (color after the label text): always `1E202B` — matches stat badge `labelColor`, unifying the whole header visually
- `logoColor=BRAND_HEX` — the technology's exact brand color; this is the ONLY color that appears, making the icon pop against the dark background
- No `labelColor` param needed — the entire badge is dark

**Badge URL patterns:**

Stat badge:
` ` `
 https://img.shields.io/github/STAT/USERNAME/REPO?style=for-the-badge&logo=ICON&logoColor=D9E0EE&labelColor=1E202B&color=ACCENT_HEX
` ` `

Tech badge:
` ` `
https://img.shields.io/badge/LABEL-1E202B?style=for-the-badge&logo=LOGO_NAME&logoColor=BRAND_HEX
` ` `

**Header rules:**
- Title: ALL CAPS, centered
- Tagline: italicised, punchy — never generic ("A project that does things")
- Stat badges row first, then "Built with:" tech badges row below
- Use [shields.io](https://shields.io/) for all badge URLs
- Verify every logo name at [simpleicons.org](https://simpleicons.org/) — shields.io uses that exact icon set

---

**Tech badge brand color reference — `logoColor=` values (background is always `1E202B`):**

| Technology | `logoColor=` | `logo=` |
|------------|-------------|---------|
| JavaScript | `F7DF1E` | `javascript` |
| TypeScript | `3178C6` | `typescript` |
| Python | `3776AB` | `python` |
| React | `61DAFB` | `react` |
| Vue.js | `4FC08D` | `vuedotjs` |
| Node.js | `339933` | `nodedotjs` |
| Next.js | `ffffff` | `nextdotjs` |
| Vite | `646CFF` | `vite` |
| Tailwind CSS | `06B6D4` | `tailwindcss` |
| HTML5 | `E34F26` | `html5` |
| CSS3 | `1572B6` | `css3` |
| Rust | `ffffff` | `rust` |
| Go | `00ADD8` | `go` |
| Java | `007396` | `java` |
| Kotlin | `7F52FF` | `kotlin` |
| Swift | `F05138` | `swift` |
| PHP | `777BB4` | `php` |
| Ruby | `CC342D` | `ruby` |
| C++ | `00599C` | `cplusplus` |
| C# | `239120` | `csharp` |
| Docker | `2496ED` | `docker` |
| PostgreSQL | `4169E1` | `postgresql` |
| MongoDB | `47A248` | `mongodb` |
| Redis | `DC382D` | `redis` |
| MySQL | `4479A1` | `mysql` |
| GraphQL | `E10098` | `graphql` |
| GitHub Actions | `2088FF` | `githubactions` |
| AWS | `FF9900` | `amazonaws` |
| Vercel | `ffffff` | `vercel` |
| Firebase | `FFCA28` | `firebase` |
| Supabase | `3ECF8E` | `supabase` |
| npm | `CB3837` | `npm` |
| ESLint | `4B32C3` | `eslint` |
| Markdown | `ffffff` | `markdown` |
| JSON | `ffffff` | `json` |

- Hex values are **without** the `#` prefix
- For technologies not listed: look up the exact logo name at [simpleicons.org](https://simpleicons.org/)
- If no Simple Icons entry exists: omit `logo=` and use `logoColor=D9E0EE`

---

### Section 2 — Project Overview (always include)

2–3 sentences covering:
1. What problem this solves
2. Who it's for
3. What makes it different

> **Example:** TaskFlow automates repetitive business workflows with a visual drag-and-drop builder. Built for non-technical operations teams, it integrates with 50+ tools without requiring code or infrastructure setup.

---

### Section 3 — Key Features (include when project has distinct features)

Present as **benefit → capability**, not just a feature list:

## Features

- **Visual Workflow Builder** — Create complex automations with intuitive drag-and-drop
- **Native Integrations** — Connect with Slack, Gmail, Salesforce, and 47+ other tools
- **Real-time Monitoring** — Track performance with detailed analytics dashboards
- **Team Collaboration** — Share and co-edit with role-based permissions
` ` `

Aim for 3–6 bullets. Each bullet: bold label, em-dash, then the user benefit.

---

### Section 4 — Visual Demo (include if demo/screenshot exists or user can provide one)
` `
## Demo

![Project Demo](https://github.com/user/repo/raw/main/demo.gif)

[Try the Live Demo](https://your-demo-url.com)

` `

If the user has no demo yet, omit the section entirely.

---

### Section 5 — Tech Stack (include when stack is non-trivial)

` ` `markdown
## Tech Stack

- **Backend:** Node.js 18+, Express.js, PostgreSQL
- **Frontend:** React 18, TypeScript, Tailwind CSS
- **Infrastructure:** Docker, AWS Lambda, Redis
- **Testing:** Jest, Cypress, GitHub Actions
` ` `

Group by layer. Only include layers that exist in the project.

---

### Section 6 — Installation & Setup (always include for code projects)

## Getting Started

### Prerequisites
- Node.js 18+
- PostgreSQL 14+

### Setup

1. **Clone the repository**
   ` ` `bash
   git clone https://github.com/USERNAME/REPO.git
   ` ` `

2. **Navigate to the project directory**
   ` ` `bash
   cd REPO
   ` ` `

3. **Install dependencies**
   ` ` `bash
   npm install
   ` ` `

4. **Configure environment variables**
   ` ` `bash
   cp .env.example .env
   ` ` `
   Edit `.env` with your credentials.

5. **Start the development server**
   ` ` `bash
   npm run dev
   ` ` `

6. **Verify installation**
   Open [http://localhost:3000](http://localhost:3000) in your browser.
` ` `

**Rules:**
- `cd` is always its own step
- Each step has a **bold label** + code block
- Never include a project tree/file structure diagram
- Remove any sensitive values from example commands
- Use the correct package manager (npm / yarn / pip / maven / cargo / etc.)
- Double-check all repository URLs

---

### Section 7 — License (include only if a LICENSE file exists)

## License

This project is licensed under the MIT License — see the [LICENSE](LICENSE) file for details.

Replace "MIT" with the actual license. If no license file exists, omit this section entirely.

---

### Section 8 — Support (include if support channels are known)

## Support

- **Documentation:** [docs.example.com](https://docs.example.com)
- **Issues:** [GitHub Issues](https://github.com/USERNAME/REPO/issues)
- **Discord:** [Join the community](https://discord.gg/invite)
- **Email:** support@example.com

Only list channels that actually exist. Never fabricate URLs.


## Step 3: Quality Check

Before presenting the README, verify:

- [ ] Project name matches the actual repo/directory name
- [ ] All badge URLs reference the correct GitHub username and repo name
- [ ] Stat badges all use `labelColor=1E202B` and `logoColor=D9E0EE`
- [ ] Stat badge accent `color=` values form a cohesive palette (not random/clashing)
- [ ] Tech badges all use `1E202B` as the badge background
- [ ] Tech badge `logoColor=` values match the brand hex from the reference table above
- [ ] All logo names verified against simpleicons.org before including
- [ ] Tech badges only show technologies confirmed to be in the project
- [ ] Installation steps use the correct package manager
- [ ] No sensitive credentials appear in example commands
- [ ] No placeholder text (USERNAME, REPO) left unfilled
- [ ] License section present only if a LICENSE file was found
- [ ] No footer section added
- [ ] No project tree structure included

---

## Common Mistakes to Avoid

1. **Wrong badge style** — Always `for-the-badge`; never `flat-square` or `flat`
2. **Inconsistent stat badge colors** — All stat badges must share `labelColor=1E202B` and `logoColor=D9E0EE`
3. **Wrong background for tech badges** — Must be `1E202B`, not the brand color
4. **Swapped colors** — Brand hex belongs in `logoColor=` on a dark background; it is NOT the badge background
5. **Stale placeholders** — Replace every `USERNAME` / `REPO` with real values or clearly flag them
6. **Invalid logo names** — Verify at simpleicons.org; wrong names render as broken badges silently
7. **Invented URLs** — Never fabricate demo links, docs URLs, or Discord invites
8. **Wrong package manager** — Match the manifest (package.json → npm/yarn, requirements.txt → pip, etc.)
9. **Footer sections** — Do not add a footer by default
10. **Project tree diagrams** — Do not include file structure diagrams in the READMEs
11. **License section without LICENSE file** — Only include if a license file is actually present
12. **Generic taglines** — Avoid bland descriptions like "A project that does things"; make it specific and compelling
