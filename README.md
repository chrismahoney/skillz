# skillz

A comprehensive repository of individual skills following best practices from the skill-creator framework, paired with a modern React-based visual catalog for discovering, browsing, and managing skills. **Now includes skillpack support** with 4 skillpacks: appie, new-skillpack, another-skillpack, and mahoney-skillz, plus the appie-onboarding skill. **v1.2.0 includes 4 skillpacks: appie, new-skillpack, another-skillpack, and mahoney-skillz, plus the appie-onboarding skill.**

## 📦 Skillpack Structure

The `skillz` project now supports **skillpacks** - organized collections of skills with consistent metadata and session reporting.

### Current Skillpacks


| Skillpack | Skills | Status |
|-----------|--------|--------|
| `chrismahoney/skillz@appie` | appie, session-report, appie-onboarding | ✅ v1.2.0 Complete |
| `chrismahoney/skillz@new-skillpack` | new-skillpack | ✅ Created |
| `chrismahoney/skillz@another-skillpack` | another-skillpack | ✅ Created |
| `chrismahoney/skillz@mahoney-skillz` | mahoney-skillz skills | 🚧 In Development |

### Skillpack Directory Structure

```out/skillpacks/chrismahoney/skillz/
├ appie/
│   ├ appie.SKILL.md              # Foundational skill metadata
│   ├ session-report.md           # Session report for appie skill
│   ├ templates/
│   │   └ SKILL_TEMPLATE.md       # Template for creating new skills
│   └ session-reports/
│       ├ appie.md                # Initial session report
│       ├ session-report.md       # session-report skill session report
│       └ appie-onboarding.md     # appie-onboarding session report
├ new-skillpack/
│   ├ new-skillpack.SKILL.md      # New skillpack foundational skill
│   └ session-reports/
│       └ new-skillpack.md        # new-skillpack session report
├ another-skillpack/
│   ├ another-skillpack.SKILL.md  # Another-skillpack foundational skill
│   └ session-reports/
│       └ another-skillpack.md    # another-skillpack session report
├ mahoney-skillz/
│   ├ mahoney-skillz.SKILL.md     # Mahoney-skillz foundational skillpack metadata
│   ├ session-report.md           # Session report for mahoney-skillz skillpack
│   └ session-reports/
│       └ mahoney-skillz.md       # Initial session report
└ templates/
    └ SKILL_TEMPLATE.md           # Template for creating new skills

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

- **Current version**: 1.1.0 (skillpack edition)
- **First skillpack**: `chrismahoney/skillz@appie` - founding skillpack (v1.0.0)
- **Additional skillpacks**: `chrismahoney/skillz@new-skillpack`, `chrismahoney/skillz@another-skillpack`
- **Known issue**: `npx skills list --json` returns empty array for skillpack skills until path resolution configured (CLI is GitHub-based; skillpack format is complementary)
- **Memory bank**: All 6 core files updated with persistent context
- **Design**: All 7 milestones (M1-M7) completed per `WORKING_SKILL_SEED.md`
- **Skillpack vs CLI**: `npx skills` CLI is GitHub-based for discovery/management; skillpack format (`out/skillpacks/`) is for local skill organization - both can coexist