# Technical Context: skillz

## Current Technology Stack

### Playground HTML SPA (`out/skillpacks/chrismahoney/skillz/playground/`)
- **Vanilla JavaScript** — no build step, no npm, no framework
- **Tailwind CSS** via CDN (`https://cdn.tailwindcss.com`)
- **HTML5** — semantic structure with `data-tab` attributes
- **Interactivity**: click listeners on `[data-tab]`, tab switching, search filtering, view mode toggle (grid/list), DOMContentLoaded init
- **Skill data**: mocked array of 11 skills in `<script>` tag

### Skillpack / CLI Stack
- **Node.js** — runtime for CLI tools
- **npm** — package management (for `npx skills`)
- **skills.sh** — CLI for skill discovery (`npx skills list --json`)
- **Markdown** — SKILL.md documentation with YAML frontmatter
- **Git** — version control

### Appz / Skillz Catalog (Reference, Not Current Focus)
- **React** — UI framework (referenced in project brief, not implemented in playground)
- **TypeScript** — type safety
- **Vite** — build tool and dev server
- **Tailwind CSS** — utility-first styling
- **React Three Fiber** — 3D graphics

## Development Setup

### Node Version
- Node 22 (specified for React conversion discussion)

### Build Commands (Playground)
- No build step — open `index.html` directly in browser
- No `package.json` exists for playground directory

### Dependencies (Playground)
- Zero — Tailwind via CDN only

## Technical Constraints

- Playground has no npm setup (no `package.json`)
- Vanilla JS skills data is mocked, not connected to `skills.sh` API
- React conversion would require introducing npm + build tooling
- Two parallel stacks: vanilla JS playground + React-based skillz-catalog (project brief references)

## Tool Usage Patterns

- `read_files` — inspect memory bank, HTML, SKILL.md files
- `run_commands` — check file structure, run grep/sed/python
- `editor` — modify HTML, memory bank files
- `ask_question` — user interviews (locked format going forward)