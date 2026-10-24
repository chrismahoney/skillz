# skillz Documentation

Welcome to the skillz documentation site. This repository contains a comprehensive collection of skills following best practices from the skill-creator framework, paired with a modern React-based visual catalog for discovering, browsing, and managing skills.

## 📦 Current Version

**1.1.0** (skillpack edition)

## 📚 Documentation Sections

### Skillpack Management
- **`docs/SKILL_PACKAGING.md`** - Complete guide to skillpack management including:
  - Specifying skillpacks via `skill_locator` frontmatter
  - Moving skills between skillpacks
  - Directory structure consistency
  - How to create new skillpacks
  - Skill structure format
  - Session report format
  - Environment variables
  - Export format

### Skill Documentation
- Individual `SKILL.md` files in each skillpack
- `SKILL_TEMPLATE.md` - Template for creating new skills

### Project Overview
- `README.md` - Project overview and quick start
- `memory-bank/` - Cline session context and progress tracking
- `projectbrief.md` - Project goals and structure
- `progress.md` - What works, evolution of decisions

### Skillpacks Currently Available

| Skillpack | Skills | Status |
|-----------|--------|--------|
| `chrismahoney/skillz@appie` | appie, session-report | ✅ v1.0 Complete |
| `chrismahoney/skillz@new-skillpack` | (skills defined) | ✅ Created |
| `chrismahoney/skillz@another-skillpack` | another-skillpack | ✅ Created |

## 🛠️ Development

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

## 🔗 Quick Links

- [Skillpack Management Guide](docs/SKILL_PACKAGING.md)
- [Project Brief](memory-bank/projectbrief.md)
- [Progress Log](memory-bank/progress.md)
- [Active Context](memory-bank/activeContext.md)
- [Skillz Repository](out/skillpacks/chrismahoney/skillz/)