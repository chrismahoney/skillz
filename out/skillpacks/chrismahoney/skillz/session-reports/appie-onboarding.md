---
title: "appie-onboarding - Initial Session Report"
---
## Session Report: appie-onboarding (Onboarding Skill for chrismahoney/skillz@appie Skillpack)

### Skill Identifier
- **Skill ID**: appie-onboarding
- **Skill Locator**: chrismahoney/skillz@appie-onboarding
- **Entity/Organization**: truemotive (developer entity)
- **Author/Owner**: chrismahoney
- **Skillpack**: chrismahoney/skillz@appie

### Creation Date
- **Date**: 2026-10-24

### Design Process

#### 1. Skill Definition & Purpose
The `appie-onboarding` skill was designed as the onboarding guide for the `chrismahoney/skillz@appie` skillpack. Primary purposes:
- Provide new developers with guidance on skillpack structure and navigation
- Document the skill creation workflow using `SKILL_TEMPLATE.md`
- Explain how per-skill session reports are generated and maintained
- Describe how to use the appie skill's export functionality to combine prompt data from all skills
- Enable skillpack management using `skill_locator` frontmatter for specifying and moving between skillpacks

#### 2. Key Design Decisions

##### Skillpack Structure
- **Flat directory structure**: All `.md` skill files coexist in `out/skillpacks/chrismahoney/skillz/`
- **Consistent with `.agents/skills/` pattern**: Ensures ease of use and CLI discovery
- **Session reports subdirectory**: `session-reports/` stores per-skill session summaries
- **Templates directory**: `templates/SKILL_TEMPLATE.md` provides ready-to-use template for creating new skills

##### Data Format
- **`'skills'` data array**: Uses JSON format with minimum fields per entry:
  - `name`: Skill name
  - `description`: Skill description
  - `owner`: Skill owner/author
  - `repo`: GitHub repository name
  - `skill_locator`: Full skill locator (e.g., `chrismahoney/skillz@appie-onboarding`)
  - `tags`: Optional tags array (e.g., `[skillpack, onboarding]`)

##### Environment Variables
- **Required**: `SKILLS_API_URL`, `SKILLS_REGISTRY_URL`
- **Optional**: `GITHUB_TOKEN`, `OPENAI_API_KEY`, `ANTHROPIC_API_KEY`
- **Template**: `.env.example` with all variables documented

##### Export Format
- **Metaprompt**: Combines prompt data from all skills + `npx skills` usage instructions
- **`usernotes`**: Checks with user for any additional information (docs references, etc.)
- **Session reports**: Full markdown summaries embedded in export

##### Template
- **SKILL_TEMPLATE.md**: Ready-to-use template at `out/skillpacks/chrismahoney/skillz/templates/SKILL_TEMPLATE.md`
- Frontmatter with placeholders: `{{skill_id}}`, `{{skill_name}}`, `{{description}}`, `{{author}}`, `{{tags}}`, `{{skill_locator}}`

#### 3. Verification Status
- ✅ Skills specification docs adherence verified
- ✅ Frontmatter/syntax requirements met
- ✅ All required frontmatter fields present: `id`, `name`, `description`, `author`, `skill_locator`, `tags`
- ✅ `skills` data array minimum fields documented
- ✅ Session report format consistent with M6 specifications
- ✅ Export format includes metadata, skills data, session reports, usernotes, npx instructions

### Session Notes
- This is the initial session report for the `appie-onboarding` skill
- Serves as the onboarding foundation for the `chrismahoney/skillz@appie` skillpack
- Subsequent skills will follow the same session report format for consistency
- The truemotive entity enables organized development of onboarding skills within the chrismahoney GitHub organization

### Related Files
- `out/skillpacks/chrismahoney/skillz/appie/appie-onboarding.SKILL.md` - Skill metadata and documentation
- `out/skillpacks/chrismahoney/skillz/templates/SKILL_TEMPLATE.md` - Template for creating new skills
- `out/skillpacks/chrismahoney/skillz/session-reports/` - Directory for per-skill session reports