# Project Brief: skillz

**Created:** October 23, 2026  
**Version:** 1.2.0 (skillpack edition)  
**Type:** Skills Repository & Visual Catalog

---

## 🎯 Mission Statement

A comprehensive repository of individual skills following best practices from the skill-creator framework, paired with a modern React-based visual catalog for discovering, browsing, and managing skills. **Now includes skillpack support** with `chrismahoney/skillz@appie` as the first skillpack, and `new-skillpack`, `another-skillpack`, and `mahoney-skillz` as complementary skillpacks.

---

## 📋 Core Objectives

### Primary Goals
1. **Skills Repository** - Host and organize individual skills following standardized structure
2. **Visual Catalog** - Provide an interactive UI for discovering and managing skills
3. **Best Practices** - Enforce consistent skill formatting and documentation standards
4. **Community Growth** - Enable easy contribution and discovery of new skills
5. **Skillpack Support** - Enable users to specify and move skills between multiple skillpacks

### Success Metrics
- Skills discoverable via command line and web UI
- Zero TypeScript compilation errors
- Responsive design across all viewports
- Efficient build pipeline (fast compilation, optimized output)
- Skillpack management feature working end-to-end
- All 3 skillpacks (appie, new-skillpack, another-skillpack) follow consistent structure

---

## 🏗️ Project Structure

```
skillz/
├── memory-bank/              # Cline memory bank (6 core files)
├── docs/                     # Documentation
├── .clinerules/              # Cline automation rules
├── skills/                   # Individual skill directories
│   ├── skillz-organizer/     # Repository management skill
│   ├── playground/           # Visual catalog prototype
│   └── [future skills...]
├── appz/                     # Applications
│   └── skillz-catalog/       # React + Vite skill catalog UI
├── README.md                 # Project overview
└── [archive files]
```

---

## 🚀 Key Features

### Skills Repository
- Modular skill structure (`.skill` trigger + `SKILL.md` documentation)
- YAML frontmatter for metadata (name, description, license)
- Skill discovery and indexing capabilities
- Organizational and personal skill collections

### Visual Catalog (skillz-catalog)
- **2D Grid View** - Standard card-based layout with hover effects
- **3D Starfield Background** - Atmospheric visual backdrop
- **Facet Grouping** - Organization/Individual/Collection filters
- **kbar Command Palette** - Cmd+Ctrl+K quick search
- **Collection Management** - Save skills to personal/org collections
- **Update Badges** - Color-coded status indicators

---

## 🛠️ Technology Stack

### Frontend
- **React** - UI framework
- **TypeScript** - Type safety
- **Vite** - Build tool and dev server
- **Tailwind CSS** - Utility-first styling
- **PostCSS** - CSS processing pipeline
- **React Three Fiber** - 3D graphics (for skill card miniatures)

### Build & Tooling
- **npm** - Package management
- **PostCSS plugins** - Autoprefixer, cssnano, preset-env
- **TypeScript compiler** - Zero-error compilation target

---

## 📊 Current Status

### Completed
- ✅ Project scaffolding (Vite + TypeScript + React)
- ✅ Tailwind CSS dark theme
- ✅ Skills data fetching (`skills list --json`)
- ✅ LocalStorage data persistence
- ✅ SkillCard components (2D grid + 3D miniatures)
- ✅ Facet-based grouping (org/user/collection)
- ✅ 3D starfield background
- ✅ kbar command palette overlay
- ✅ TypeScript type system
- ✅ **appie.SKILL.md created** (P1)
- ✅ **Initial session report created** (P2)
- ✅ **session-report skill added** (P3)
- ✅ **SKILL_TEMPLATE.md created**
- ✅ **Memory bank updated** (activeContext.md, progress.md, projectbrief.md)
- ✅ **new-skillpack created** (new-skillpack.SKILL.md and session report)
- ✅ **another-skillpack created** (another-skillpack.SKILL.md and session report)
- ✅ **mahoney-skillz created** (mahoney-skillz.SKILL.md and session report)
- ✅ **Skillpack Management feature added** - specifying new/existing skillpacks and moving skills between packs
- ✅ **All 7 design milestones (M1-M7) completed**
- ✅ 5/5 unit tests passed
- ✅ **Memory bank fully updated** (6 core files)
- ✅ **appie-onboarding skill added** to appie skillpack
- ✅ **git-workflow skill added** to mahoney-skillz (new skill within existing skillpack)
- ✅ **test-skill added** to appie skillpack with .agents directory integration
- ✅ **appie-branstorm added** - generic onboarding pattern for skill discovery and naming
- ✅ **appz skillpack added** - odyssey catalog wandering pattern
- ✅ **first-skillz-skill added** - interview/grilling step for appz app assembly (mahoney-skillz)
- ✅ **PR #1 merged**: "feat: initial skillz ecosystem v1.0 release"
- ✅ **v1.2.0 released**: 5 skillpacks (appie, new-skillpack, another-skillpack, mahoney-skillz, appz), 9 skills total, gaps & decisions fully synthesized
- ✅ **HTML SPA playground completed** — `out/skillpacks/chrismahoney/skillz/playground/index.html` with vanilla JS interactivity (skillsData, renderGridSkills, renderMapmanifestSkills, filterSkills, tab switching, search filtering, view mode toggle)
- ✅ **Interview question format locked** — button-selector component format with numbered options (1-5) + free text response format

---

## 🔄 Development Workflow

### Adding New Skills
1. Create directory under `out/skillpacks/chrismahoney/skillz/`
2. Add `SKILL.md` with required frontmatter: `id`, `name`, `description`, `author`, `tags`, `skill_locator`
3. Create session report in `session-reports/`
4. Use `SKILL_TEMPLATE.md` for new skills

### Adding New Skillpack

1. Create directory: `mkdir -p out/skillpacks/chrismahoney/skillz/<skillpack-name>`
2. Add foundational `SKILL.md` with `skill_locator: chrismahoney/skillz@<skillpack-name>`
3. Create session report in `session-reports/`
4. Add `SKILL_TEMPLATE.md` for skill creation
5. Update `WORKING_SKILL_SEED.md` to reflect new skills and completion status
```

### Development Commands
```bash
# Start dev server
npm run dev

# Build for production
npm run build

# Type check
npm run type-check

# List skills (JSON format)
npx skills list --json
```

---

## 🎨 Design Principles

1. **Modularity** - Each skill is self-contained and reusable
2. **Type Safety** - Full TypeScript coverage, zero compilation errors
3. **Performance** - Optimized builds, efficient data caching
4. **Accessibility** - Semantic HTML, keyboard navigation
5. **Responsiveness** - Mobile-first, adaptive layouts

---

## 📚 Documentation

- `README.md` - Project overview and quick start
- `memory-bank/` - Cline session context
- `appz/skillz-catalog/` - Application-specific docs
- Individual `SKILL.md` files - Skill documentation

---

## 🤝 Contributing

To contribute a skill:
1. Follow the skill structure guidelines
2. Include comprehensive documentation
3. Test with `npx skills list --json`
4. Submit via pull request

---

## 📝 Notes

- Current version: 1.7.4 (skills package)
- Known issue: `npx skills list --json` returns empty array until path resolution fixed
- Week 1-3 of development complete in skillz-catalog
- Focus shifting to production readiness and additional skills