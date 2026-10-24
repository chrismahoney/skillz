---
title: "appie - Initial Session Report"
---

## Session Report: appie (First Skill in chrismahoney/skillz@appie Skillpack)

### Skill Identifier
- **Skill ID**: appie
- **Skill Locator**: chrismahoney/skillz@appie
- **Entity/Organization**: truemotive (developer entity)
- **Author/Owner**: chrismahoney
- **Skillpack**: chrismahoney/skillz@appie

### Creation Date
- **Date**: 2026-10-24

### Design Process

#### 1. Skill Definition & Purpose
The `appie` skill was designed as the foundational skill for the `chrismahoney/skillz@appie` skillpack. Primary purposes:
- Organize and manage the skillpack metadata
- Maintain a `skills` data array with verified skill entries
- Provide a running summary of the skillpack's current state
- Enable export of a metaprompt combining prompt data from all skills

#### 2. Key Design Decisions

##### Skillpack Structure
- **Flat directory structure**: All `.md` skill files coexist in `out/skillpacks/chrismahoney/skillz/`
- **Consistent with `.agents/skills/` pattern**: Ensures ease of use and CLI discovery
- **Session reports subdirectory**: `session-reports/` stores per-skill session summaries

##### Data Format
- **`'skills'` data array**: Uses JSON format with minimum fields per entry:
  - `name`: Skill name
  - `description`: Skill description
  - `owner`: Skill owner/author
  - `repo`: GitHub repository name
  - `skill_locator`: Full skill locator (e.g., `chrismahoney/skillz@appie`)
  - `tags`: Optional tags array (e.g., `[skillpack, meta, truemotive]`)

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
- This is the initial session report for the `appie` skill
- Serves as the foundation for future skill additions to the `chrismahoney/skillz@appie` skillpack
- Subsequent skills will follow the same session report format for consistency
- The truemotive entity enables organized development of internal skills within the chrismahoney GitHub organization

### Related Files
- `out/skillpacks/chrismahoney/skillz/appie.SKILL.md` - Skill metadata and documentation
- `out/skillpacks/chrismahoney/skillz/templates/SKILL_TEMPLATE.md` - Template for creating new skills
- `out/skillpacks/chrismahoney/skillz/session-reports/` - Directory for per-skill session reports