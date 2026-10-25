# System Patterns: skillz

## Skillpack Structure Pattern

Each skillpack lives under `out/skillpacks/chrismahoney/skillz/<skillpack-name>/` with:
```
<skillpack-name>/
├── SKILL.md              # Foundational skill doc with frontmatter
├── session-reports/      # Session documentation
│   └── <skillpack-name>.md
└── templates/            # SKILL_TEMPLATE.md for new skills
```

Frontmatter schema (6 required fields): `id`, `name`, `description`, `author`, `tags`, `skill_locator`

`skill_locator` format: `chrismahoney/skillz@<skillpack-name>`

## Skillpack Management Pattern

Users can:
- Specify new/existing skillpack from `out/skillpacks/` list
- Move skills freely between packs by updating `skill_locator` frontmatter
- Physically move `.md` files between pack directories

## HTML SPA Pattern (Playground)

Located at `out/skillpacks/chrismahoney/skillz/playground/index.html`:
- Vanilla JS (no build step, no npm, no framework)
- Tailwind CSS via CDN
- 3 tab panels: Grid View, MindMap, MapManifest
- `data-tab` attribute on buttons, `.tab-panel` on panels
- Client-side skill data array (mocked, 11 skills)
- Filter/search, tab switching, view mode toggle (grid/list)
- DOMContentLoaded initialization with hash-based tab selection

## React Conversion Discussion (Pending)

Question 1 (React conversion strategy) was posed during this session:
- Option 1: Fresh React Project + Migration (Vite + React, Node 22)
- Option 2: In-Place React Refactor (inline JSX, esbuild)
- Option 3: New React Package Side-by-Side (playground-react/)
- Option 4: Hybrid Approach (vanilla JS core + React for specific parts)
- Option 5: Defer/Clarify (need more details)

Awaiting user selection.

## Interview Question Format (Locked)

All interviews going forward must use this format:
- Question with emoji + title
- Well-presented options with numbers (🔘 Single Choice)
- Response format: single choice (1-5) or free text + choice
- Options structured as button-triggering components in AI agent harnesses

Example from screenshot:
```
🛠️ React Conversion Interview: Appz & Skillz Odyssey

🎯 Core Question: What is the appropriate React conversion strategy...?

📋 5 Options:
1️⃣ Fresh React Project + Migration
2️⃣ In-Place React Refactor
3️⃣ New React Package Side-by-Side
4️⃣ Hybrid Approach
5️⃣ Defer/Clarify

📝 Your Response Format: exactly one of 1-5, or 5 + constraints

📚 Odyssey Note: recorded as part of new appz and skillz generation odyssey
```