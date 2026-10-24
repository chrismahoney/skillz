# skillz

A comprehensive repository of individual skills following best practices from the skill- framework, paired with a modern React-based visual catalog for discovering, browsing, and managing skills. **Now includes skillpack support** with `chrismahoney/skillz@appie` as the first skillpack.

## 📦 Skillpack Structure

The `skillz` project now supports **skillpacks** - organized collections of skills with consistent metadata and session reporting.

### Current Skillpack: `chrismahoney/skillz@appie`

```
out/skillpacks/chrismahoney/skillz/
├ appie.SKILL.md
├ session-report.md
├ templates/
│   └ SKILL_TEMPLATE.md
└ session-reports/
    ├ appie.md
    └ session-report.md
```

### How to Create a New Skillpack

#### Step 1: Create Skillpack Directory
```bash
mkdir -p out/skillpacks/<scope>/skillz/
```

#### Step 2: Add Foundational Skill (`SKILL.md`)
Create with required frontmatter:
- `id`, `name`, `description`, `author`, `tags`, `skill_locator`

#### Step 3: Create Session Report (`session-reports/`)
Follow format in `session-reports/appie.md`.

#### Step 4: Add Additional Skills
Create `SKILL.md` files in skillpack root, each with session report.

#### Step 5: Template Skill Creation
Use `SKILL_TEMPLATE.md` with placeholders: `{{skill_id}}`, `{{skill_name}}`, etc.

#### Step 6: Update Skillpack
Update `WORKING_SKILL_SEED.md` to reflect new skills and milestone completion.

#### Step 7: Test CLI Integration
Test with `npx skills list --json` (note: CLI is GitHub-based; skillpack format is complementary).

#### Step 8: Validate Specification
Verify adherence to `https://agentskills.io/specification` - all required frontmatter fields, correct YAML syntax, session report format, export format (metadata + skills data array + session reports + usernotes + npx instructions).
## 📦 Skillpack Structure

The `skillz` project now supports **skillpacks** - organized collections of skills with consistent metadata and session reporting.

### Current Skillpack: `chrismahoney/skillz@appie`

```
out/skillpacks/chrismahoney/skillz/
├ appie.SKILL.md
├ session-report.md
├ templates/
│   └ SKILL_TEMPLATE.md
└ session-reports/
    ├ appie.md
    └ session-report.md

A comprehensive repository of individual skills following best practices from the skill-creator framework, paired with a modern React-based visual catalog for discovering, browsing, and managing skills. **Now includes skillpack support** with `chrismahoney/skillz@appie` as the first skillpack.
## Footnotes

- **Current version**: 1.1.0 (skillpack edition)
- **First skillpack**: `chrismahoney/skillz@appie` with appie and session-report skills
- **Known issue**: `npx skills list --json` returns empty array for skillpack skills until path resolution configured (CLI is GitHub-based; skillpack format is complementary)
- **Memory bank**: All 6 core files updated with persistent context
- **Design**: All 7 milestones (M1-M7) completed per `WORKING_SKILL_SEED.md`
- **Skillpack vs CLI**: `npx skills` CLI is GitHub-based for discovery/management; skillpack format (`out/skillpacks/`) is for local skill organization - both can coexist