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

## AGENTS Rules: Document Formatting

**STRICT REQUIREMENT**: Document formatting must always be applied to code and JSON blobs.

### Rules

1. **Code blocks**: All code fences must use triple backticks (```) with appropriate language identifiers for syntax highlighting

2. **JSON formatting**: All JSON blobs must be:
   - Properly indented with 2-space indentation
   - Have keys sorted alphabetically where feasible
   - Be valid JSON (no trailing commas, proper quoting)
   - Include type annotations when the JSON represents typed data

3. **YAML frontmatter**: All YAML frontmatter in Markdown files must:
   - Use `---` delimiters on separate lines
   - Have keys quoted consistently
   - Be valid YAML

4. **Markdown code spans**: Inline code must use single backticks (`) with no spaces between backticks and code

5. **Tabular data**: Tables must use the pipe-table format with:
   - Header row separated by `---`
   - Column alignment specified (:-:, :-, or :--)

6. **Consistency**: Formatting style must be consistent throughout a document - do not mix indentation styles (2-space vs 4-space) within the same document

### Rationale

- Ensures AI-generated and modified code is immediately usable
- Reduces debugging time from formatting-related issues
- Maintains professional code quality standards
- Facilitates automated processing and tooling

### Enforcement

- All file modifications must pass formatting checks
- New files must adhere to these conventions from creation
- Existing files being modified must be brought into compliance
- Deviations must be documented with justification