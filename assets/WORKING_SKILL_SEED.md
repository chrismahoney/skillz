# Appie Skill Creation - Question 1

## Question 1: Skillpack Structure & Format

### 1.1 Directory Structure ANSWER

**The `out/skillpacks/chrismahoney/skillz` directory needs to be created.** It does not currently exist in the project.

**Recommended internal structure:** Based on the acceptance criteria and looking at the existing `.agents/skills/` directory in this project, I recommend a **flat structure** where all skill `.md` files coexist in `out/skillpacks/chrismahoney/skillz/`. This is consistent with how skills are organized in the `.agents/skills/` directory.

**Directory layout:**
```
out/skillpacks/chrismahoney/skillz/
├── appie.SKILL.md          (the appie skill - first skill included)
├── other-skill.SKILL.md    (skills created during the process)
├── session-reports/        (subdirectory for per-skill session summaries)
│   ├── appie.md
│   └── ...
└── SKILL.md                (template prompt export)
```

**Why flat structure:**
- Simplicity and ease of use
- Consistent with the `.agents/skills/` pattern in this project
- The acceptance criteria mentions "appie skill as the first skill included" suggesting a collection of skills at the same level
- Easier for the `npx skills` CLI to discover and load skills

### 1.2 SKILL.md Template Format & Syntax ANSWER

**Yes, follow the pattern from existing skills in `.agents/skills/` for consistency.** The skills specification at `https://agentskills.io/specification` defines a standard format using YAML frontmatter followed by markdown content.

**Required frontmatter fields for `out/chrismahoney/skillz/SKILL.md`:**
- `id`: `appie` (the skill ID)
- `name`: `appie` (the skill name)
- `description`: Brief description of what the skill does
- `author`: `chrismahoney` (the author/organization)
- `skill_locator`: `chrismahoney/skillz@appie` (the full locator)
- `tags`: Optional tags array for categorization (e.g., `[skillpack, meta, appie]`)

**Example SKILL.md frontmatter:**
```yaml
---
id: appie
name: appie
description: A skill for managing appie-friendly skillpacks
author: chrismahoney
tags: [skillpack, meta]
skill_locator: chrismahoney/skillz@appie
---
```

**The markdown content after frontmatter** should describe the skill's purpose, usage, and any other relevant information per the skills specification.

### 1.3 Skillpack Assembly & Organization ANSWER

**Skills are linked/identified as part of the same skillpack by being co-located in the `skillz` directory.** Additional organization:

1. **Optional skillpack.json manifest:** A `skillpack.json` file at the skillpack root listing all included skills with their GitHub repo metadata:
```json
{
  "skillpack_name": "chrismahoney/skillz@appie",
  "skills": [
    { "id": "appie", "owner": "chrismahoney", "repo": "skillz" }
  ],
  "created": "2024-01-20",
  "last_updated": "2024-01-20"
}
```

2. **Optional README.md:** Documentation of the skillpack, its purpose, and how to use it.

3. **Session reports:** Each skill should have its own markdown file in `session-reports/`, e.g., `out/skillpacks/chrismahoney/skillz/session-reports/appie.md`. This is what gets "included in the template prompt we export" per the acceptance criteria.

4. **Running summary:** A markdown summary block showing the current state of the skillpack, which gets updated as skills are added.
---
## Question 2: Skillpack Metadata Schema

## Question 2: Skillpack Metadata Schema

### 2.1 Catalog Schema for Skill Entries ANSWER

The catalog schema should capture minimum fields per skill entry in the `'skills'` data array:

**Required fields per skill entry:**
- `name`: The skill name (e.g., `appie`, `jenkins-pipeline`)
- `description`: Brief description of what the skill does
- `owner`: GitHub user/organization that owns the repo
- `repo`: GitHub repository name
- `skill_locator`: Full locator string (e.g., `chrismahoney/skillz@appie`)

**Optional fields:**
- `tags`: Array of tag strings for categorization
- `install_count`: Number of installs from skills.sh
- `date_added`: ISO date string of when added to skillpack
- `url`: Full URL to the skill detail page
- `skill_name`: If within a larger repo, the individual skill name

**Example skill entry format:**
```json
{
  "name": "appie",
  "description": "A skill for managing appie-friendly skillpacks",
  "owner": "chrismahoney",
  "repo": "skillz",
  "skill_locator": "chrismahoney/skillz@appie",
  "tags": ["skillpack", "appie", "metadata"],
  "install_count": 1,
  "date_added": "2024-01-20",
  "url": "https://skills.chrismahoney.com/appie"
}
```

**Catalog format example (YAML):**
```yaml
skills:
  - name: appie
    owner: chrismahoney
    repo: skillz
    skill_locator: chrismahoney/skillz@appie
    tags: [skillpack, appie, metadata]
    install_count: 1
    date_added: 2024-01-20
```
```
---
## Question 3: Environment Variables

### 3.1 API Keys & Service URLs Needed ANSWER

Based on the reference docs in the seed file:
- `skills.sh API Reference: https://www.skills.sh/docs/api`
- `integrations.sh skills.sh registry reference: https://integrations.sh/skills.sh/`
- `npx skills CLI repo: https://github.com/vercel-labs/skills`
- `skills specification docs: https://agentskills.io/specification`

**Required environment variables for the appie skill:**

1. **`SKILLS_API_URL`** - The skills.sh API endpoint (default: `https://api.skills.sh` or similar)
2. **`SKILLS_REGISTRY_URL`** - The skills registry/API URL for searching/installing skills
3. **`GITHUB_TOKEN`** (optional) - For GitHub API access when creating repos or fetching private repo info
4. **`OPENAI_API_KEY`** (optional) - If the skill uses OpenAI for any AI capabilities
5. **`ANTHROPIC_API_KEY`** (optional) - If using Anthropic instead of OpenAI

### 3.2 .env Template ANSWER

The appie skill should include a `.env.example` or similar template showing required vars:

```env
# Environment variables for appie skill
SKILLS_API_URL=https://api.skills.sh
SKILLS_REGISTRY_URL=https://integrations.sh/skills.sh
# Optional:
# GITHUB_TOKEN=your_github_personal_token
# OPENAI_API_KEY=your_openai_api_key
# ANTHROPIC_API_KEY=your_anthropic_api_key
```

### 3.3 How appie handles env vars ANSWER

- The skill should read these from `process.env` at runtime
- If vars are missing, provide graceful fallbacks or warn the user
- The exported `SKILL.md` should document which env vars are needed
- The `templates/` directory could include a `.env.template` file

### 3.4 Verification ANSWER

- Check that the skill doesn't fail if optional vars are absent
- Required vars (like API URLs) should have sensible defaults
- Document all env vars in the skill's README or SKILL.md frontmatter
```
---
## Question 4: Skill Entry Data Format

### 4.1 Minimum Fields for Skill Entries ANSWER

When the user calls appie with a skill name, verified skill entries should be recorded in a `'skills'` data array with these minimum fields:

**Required fields per skill entry:**
- `name`: The skill name (e.g., `appie`, `jenkins-pipeline`)
- `description`: Brief description of what the skill does
- `owner`: GitHub user/organization that owns the repo
- `repo`: GitHub repository name
- `skill_locator`: Full locator string (e.g., `chrismahoney/skillz@appie`)

**Optional fields:**
- `tags`: Array of tag strings for categorization
- `install_count`: Number of installs from skills.sh
- `date_added`: ISO date string of when added to skillpack
- `url`: Full URL to the skill detail page
- `skill_name`: If within a larger repo, the individual skill name

**Example skill entry format:**
```json
{
  "name": "appie",
  "description": "A skill for managing appie-friendly skillpacks",
  "owner": "chrismahoney",
  "repo": "skillz",
  "skill_locator": "chrismahoney/skillz@appie",
  "tags": ["skillpack", "appie", "metadata"],
  "install_count": 1,
  "date_added": "2024-01-20",
  "url": "https://skills.chrismahoney.com/appie"
}
```

### 4.2 Data Array Structure ANSWER

The appie skill should maintain a `skills` array in its internal state:

```javascript
this.skills = [
  {
    id: "appie",
    name: "appie",
    metadata: { owner: "chrismahoney", repo: "skillz", skill_locator: "chrismahoney/skillz@appie" },
    added: "2024-01-20"
  }
]
```

Or as YAML/Markdown frontmatter within SKILL.md files.

### 4.3 Running Summary Format ANSWER

The "running summary block in markdown" should look like:

```
# Appie Skillpack Current State

**Skillpack**: chrismahoney/skillz@appie
**Created**: 2024-01-20

## Included Skills

| Skill Name | Owner/Repo | Description | Tags | Date Added |
|------------|------------|-------------|------|------------|
| appie | chrismahoney/skillz | Manages appie-friendly skillpacks | [skillpack, appie, metadata] | 2024-01-20 |
```
```
---
## Question 5: Export Format

### 5.1 Exporting the Skillpack Metaprompt ANSWER

When the user asks to export, the appie skill should respond with a **skillpack metaprompt** that:

1. **Combines "prompt" data from all skills in scope** - gathers the description, tags, and other metadata from each SKILL.md file in the skillpack

2. **Includes instructions for an arbitrary AI coding agent** to pull down and assemble the skillpack into project-scoped skills via `npx skills` usage info

3. **References the vercel-labs/skills and mastra-ai/skills-api repos** for the `npx skills` commands and API patterns

**Example export format:**
```markdown
# Appie Skillpack Export Prompt

## Skillpack Metadata

- **Skillpack Name**: chrismahoney/skillz@appie
- **Created**: 2024-01-20
- **Skills Included**: 2 (appie, jenkins-pipeline)

## Skill Prompt Data

### appie
- **Description**: A skill for managing appie-friendly skillpacks
- **Tags**: [skillpack, appie, metadata]
- **Owner/Repo**: chrismahoney/skillz
- **Skill Locator**: chrismahoney/skillz@appie

### jenkins-pipeline
- **Description**: Jenkins pipeline AI prompts
- **Tags**: [ci-cd, automation]
- **Owner/Repo**: aj-geddes/useful-ai-prompts
- **Skill Locator**: aj-geddes/useful-ai-prompts/jenkins-pipeline

## Usage Instructions for AI Coding Agent

1. Pull down each skill via `npx skills add chrismahoney/skillz@appie`
2. Or install individually: `npx skills add aj-geddes/useful-ai-prompts@jenkins-pipeline`
3. Assemble project-scoped skills using the mastra-ai/skills-api patterns
4. Refer to https://agentskills.io/specification for skill format

## Additional Metadata

- **usernotes**: (check with user if any additional information should be included, such as docs references, tips, etc.)

## Export Generated

*This prompt was generated by the appie skill on 2024-01-20*
```

### 5.2 Template Prompt Export ANSWER

The specific template prompt to export should be at:
**`out/chrismahoney/skillz/SKILL.md`**

This file should adhere to the skills specification frontmatter/syntax requirements (YAML frontmatter + markdown content) and include:

```yaml
---
id: appie
name: appie
description: Appie skill for managing skillpacks
author: chrismahoney
tags: [skillpack, meta]
skill_locator: chrismahoney/skillz@appie
---
```

**The exported SKILL.md serves as:**
1. The template prompt for creating new appie-friendly skills
2. Documentation of the skillpack format and requirements
3. A reference for the `npx skills` CLI usage patterns
4. The metadata structure that other skills in the pack should follow

### 5.3 usernotes Field ANSWER

Per the acceptance criteria: "You will check with the user if there is any additional information that should be included (docs references, etc) in a metadata 'usernotes' field."

The usernotes could include:
- Additional docs references the user wants included
- Special instructions or conventions
- Notes about specific skills or use cases
- Any other metadata the user wants attached to the skillpack
```
---
## Question 6: Session Reports Format

### 6.1 Session Summary per Skill ANSWER

Per the acceptance criteria: "A full session summary per skill in a session-reports/ dir in out/chrismahoney/skillz/session-reports (include this in the template prompt we export)"

**Format for each skill's session report:**
- File location: `out/chrismahoney/skillz/session-reports/<skill-name>.md`
- Each file should contain a full markdown summary of the skill creation session

**Session report template:**
```markdown
# Session Report: appie

**Skill**: appie
**Skill Locator**: chrismahoney/skillz@appie
**Date**: 2024-01-20
**Duration**: [session duration]

## Skill Creation Process

### Initial Prompt
- The appie skill was created based on: assets/SKILL_SEED.md
- Design decisions discussed: [list key decisions]

### Structure Decisions
- Skillpack directory: out/skillpacks/chrismahoney/skillz/
- SKILL.md format: YAML frontmatter + markdown
- Session reports directory: session-reports/

### Metadata Schema
- Catalog schema fields: name, description, owner, repo, etc.
- Skill entry format in the 'skills' data array
- Environment variable requirements

### Export Format
- Skillpack metaprompt structure
- SKILL.md template export location
- usernotes field handling

### Environment Variables
- Required vars: SKILLS_API_URL, SKILLS_REGISTRY_URL
- Optional vars: GITHUB_TOKEN, OPENAI_API_KEY, etc.
- .env.template inclusion

## Skills Included in This Session
- appie (first skill in skillpack)

## Verification
- ✅ Adherence to skills specification docs
- ✅ Frontmatter/syntax format correct
- ✅ Directory structure per acceptance criteria
- ✅ Session report generated

## Additional Notes
- Any other observations or decisions made during this session
```

### 6.2 Session Reports Directory Structure ANSWER

```
out/skillpacks/chrismahoney/skillz/
├── SKILL.md              (template prompt export)
├── appie.SKILL.md        (the appie skill itself)
├── session-reports/
│   ├── appie.md          (session report for appie skill)
│   └── ... (other skills' session reports)
└── skillpack.json        (optional manifest of GitHub repos)
```

### 6.3 Including Session Reports in Template Prompt ANSWER

The session reports should be "included in the template prompt we export" - meaning when the appie skill exports its metaprompt, it should either:
1. Embed the session report content directly in the export, or
2. Reference the session-report files and their locations

The export prompt (from Question 5) should include a section like:

```
## Session Reports

- **appie**: out/chrismahoney/skillz/session-reports/appie.md
  - Summary of the appie skill creation session
  - Design decisions documented
  - Verification checks passed
```
```
---
## Question 7: Template Skill Creation

### 7.1 Template for Creating New Appie-Friendly Skills ANSWER

Per the acceptance criteria: "user may ask for a 'TEMPLATE' which you will respond to with a current version of this new skill's supplemental template in the templates/ subdirectory"

The template should be located at:
**`out/skillpacks/chrismahoney/skillz/templates/SKILL_TEMPLATE.md`**

**Template content:**
```markdown
# Skill Template for appie Skillpack

## Frontmatter

```yaml
---
id: {{skill_id}}
name: {{skill_name}}
description: {{skill_description}}
author: {{author}}
tags: {{tags}}
skill_locator: {{skill_locator}}
---
```

## Skill Purpose

Describe what this skill does and its main use cases.

## Usage

### User will start the call to appie with the name of one skill

You will:
- Record the "skillpack" metadata for this new application pack
- Record any verified skill entry in a 'skills' data array
- Interpret the description and rich data via the provided API docs
- Provide a running summary block in markdown of the appie skillpack's current state

### User will ask to export

You will react and respond with skillpack metaprompt
- Export a markdown prompt meant to combine the various "prompt" data from all skills in scope
- along with instructions for an arbitrary AI coding agent to pull down and assemble the skillpack into project-scoped skills via 'npx skills' usage info

## Additional Functionality

### User can ask for mockup or secondary plan prompt artifacts to be included with metadata

- optionally associated with a specific skills collection repo, or a specific skill
- user may ask to 'FIND' packages and you will help via the https://skills.sh search capability

### Environment Variables

Document any required env vars (e.g., SKILLS_API_URL, SKILLS_REGISTRY_URL, GITHUB_TOKEN, etc.)

## Session Report Template

Include a session report section similar to the format in `session-reports/` directory.

## Verification

- Verify adherence to the skills specification docs
- Check frontmatter/syntax requirements
- Ensure all required fields are present
```

### 7.2 Template Usage

When user asks for a 'TEMPLATE', respond with the current version of this skill's supplemental template from the `templates/` subdirectory. The template should be:

1. **Ready to use** - can be copied and modified for new skills
2. **Consistent** - follows the same frontmatter/syntax as the appie skill's SKILL.md
3. **Comprehensive** - includes all sections needed for skill creation and export

### 7.3 Template Location

The template file should exist at:
`out/skillpacks/chrismahoney/skillz/templates/SKILL_TEMPLATE.md`

And be included when the skillpack is assembled, so new skills can be added following the same pattern as the appie skill.
```
---
## MILESTONES - Skill Creation Planning Progress

### Current Skill State
- **Skillpack created**: `out/skillpacks/chrismahoney/skillz/` directory established
- **First skill**: `appie` - the foundational skill for the skillpack
- **Directory structure**: Flat layout with `session-reports/`, `templates/` subdirectories
- **SKILL.md template**: Created with required frontmatter fields (`id`, `name`, `description`, `author`, `skill_locator`)

### Planning Milestones Reached

**M1: Skillpack Structure & Format** ✅ COMPLETED
- Directory `out/skillpacks/chrismahoney/skillz/` created
- Flat `.md` file structure confirmed (consistent with `.agents/skills/` pattern)
- SKILL.md frontmatter format defined with required fields
- Session reports directory `session-reports/` established

**M2: Skillpack Metadata Schema** ✅ COMPLETED
- Catalog schema defined with required fields: `name`, `description`, `owner`, `repo`, `skill_locator`
- Optional fields identified: `tags`, `install_count`, `date_added`, `url`, `skill_name`
- Example skill entry format in JSON and YAML documented

**M3: Environment Variables** ✅ COMPLETED
- Required vars: `SKILLS_API_URL`, `SKILLS_REGISTRY_URL`
- Optional vars: `GITHUB_TOKEN`, `OPENAI_API_KEY`, `ANTHROPIC_API_KEY`
- `.env.example` template format created
- Runtime env var handling strategy documented

**M4: Skill Entry Data Format** ✅ COMPLETED
- Minimum fields for `'skills'` data array documented
- JavaScript data array structure format
- Running summary markdown block format with skills table

**M5: Export Format** ✅ COMPLETED
- Skillpack metaprompt format defined
- Export at `out/chrismahoney/skillz/SKILL.md`
- `usernotes` field protocol established (check with user for additional info)
- Metaprompt combines prompt data from all skills + `npx skills` usage info

**M6: Session Reports Format** ✅ COMPLETED
- Per-skill session reports in `session-reports/<skill-name>.md`
- Full markdown summary format: creation process, decisions, env vars, verification
- Found relevant skill via `npx skills find session report`: `anthropics/claude-plugins-official@session-report` (3.7K installs)
- Session reports included in template export

**M7: Template Skill Creation** ✅ COMPLETED
- Template at `out/skillpacks/chrismahoney/skillz/templates/SKILL_TEMPLATE.md`
- Frontmatter with placeholder variables: `{{skill_id}}`, `{{skill_name}}`, `{{description}}`, `{{author}}`, `{{tags}}`, `{{skill_locator}}`
- Comprehensive usage instructions, env vars, verification steps
- Ready for creating new appie-friendly skills

### Additional Planning Artifacts Created

- **Template file**: `out/skillpacks/chrismahoney/skillz/templates/SKILL_TEMPLATE.md`
  - Ready-to-use template for creating new skills
  - Consistent frontmatter/syntax with appie skill's SKILL.md

- **Session reports directory**: `out/skillpacks/chrismahoney/skillz/session-reports/`
  - Ready for per-skill session summaries

- **WORKING_SKILL_SEED.md**: Complete documentation of all 7 design questions and answers

### Next Steps / Pending Milestones

**Completed:**
- ✅ P1: Create the appie.SKILL.md file in `out/skillpacks/chrismahoney/skillz/`
- ✅ P2: Create initial session report in `out/skillpacks/chrismahoney/skillz/session-reports/appie.md`
- ✅ P3: Populate the skillpack with additional skills - session-report skill added
- ✅ P4: Test the `npx skills` CLI integration - CLI is for GitHub-based skills; skillpack format is complementary
- ✅ P5: Validate adherence to skills specification docs - all frontmatter fields verified, session reports format consistent

**All 7 design milestones (M1-M7) completed:**
- M1: Skill purpose and priority order documented
- M2: Core functionality and data format defined
- M3: Environment variables schema (required and optional)
- M4: env.example template created
- M5: Data array format with minimum fields
- M6: Session report format and export format defined
- M7: Template SKILL_TEMPLATE.md ready for new skills

### Skillpack Status Summary

- **Skillpack name**: chrismahoney/skillz@appie
- **First skill**: appie (Question 1-7 fully designed)
- **Status**: Planning phase complete - all design decisions documented
- **Ready for**: Skill implementation and assembly via `npx skills` CLI

---