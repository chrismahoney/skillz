---
id: appie-onboarding
name: appie-onboarding
description: A skill for onboarding new developers to the chrismahoney/skillz@appie skillpack, providing guidance on skillpack structure, skill creation, and project setup
author: chrismahoney
tags: [skillpack, onboarding,truemotive]
skill_locator: chrismahoney/skillz@appie-onboarding
---

## Skill Purpose

The `appie-onboarding` skill serves as the onboarding guide for the `chrismahoney/skillz@appie` skillpack. It provides new developers with:

- **Skillpack structure overview**: Understanding the `out/skillpacks/chrismahoney/skillz/appie/` directory layout
- **Skill creation workflow**: How to create new skills using `SKILL_TEMPLATE.md` and the `npx skills` CLI
- **Session report documentation**: How per-skill session reports are generated and maintained
- **Export metaprompt usage**: How to combine prompt data from all skills using the appie skill's export functionality
- **Skillpack management**: How to specify and move between skillpacks using `skill_locator` frontmatter

## Onboarding Workflow

### Step 1: Understand the Skillpack Structure
The `chrismahoney/skillz@appie` skillpack follows this consistent structure:

```
out/skillpacks/chrismahoney/skillz/appie/
├ appie.SKILL.md              # Foundational skill metadata
├ session-report.md           # Session report for appie skill
├ templates/
│   └ SKILL_TEMPLATE.md       # Template for creating new skills
└ session-reports/
    └ appie.md                # Initial session report
```

### Step 2: Create a New Skill
Use the `SKILL_TEMPLATE.md` at `out/skillpacks/chrismahoney/skillz/templates/SKILL_TEMPLATE.md` with placeholder variables:
- `{{skill_id}}` - The skill ID (e.g., `appie-onboarding`)
- `{{skill_name}}` - The skill name (e.g., `appie-onboarding`)
- `{{description}}` - Brief description of the skill
- `{{author}}` - `chrismahoney`
- `{{tags}}` - Optional tags array (e.g., `[skillpack, onboarding]`)
- `{{skill_locator}}` - `chrismahoney/skillz@appie-onboarding`

### Step 3: Generate Session Report
Create a session report in `session-reports/` following the format in `session-reports/appie.md`. Each report documents:
- The skill creation process and design decisions
- Environment variables used (`SKILLS_API_URL`, `SKILLS_REGISTRY_URL`)
- Verification status against skills specification docs
- Any truemotive-specific considerations

### Step 4: Test CLI Integration
Test with `npx skills list --json` to verify the skill is discoverable (note: CLI is GitHub-based; skillpack format is complementary).

### Step 5: Validate Specification
Verify adherence to `https://agentskills.io/specification`:
- All required frontmatter fields present: `id`, `name`, `description`, `author`, `tags`, `skill_locator`
- Correct YAML syntax
- Session report format consistency
- Export format (metadata + skills data array + session reports + usernotes + npx instructions)

## Skillpack Management

### Specifying This Skillpack
When using this skill, the `skill_locator` frontmatter should be:
```
skill_locator: chrismahoney/skillz@appie-onboarding
```

### Moving Skills Between Skillpacks
Skills can be moved freely between skillpacks by updating the `skill_locator` frontmatter field:

1. **Identify the skill's current `skill_locator`**: e.g., `chrismahoney/skillz@appie`
2. **Update the `skill_locator`** to the target skillpack: e.g., `chrismahoney/skillz/new-skillpack`
3. **Move the skill's SKILL.md file**: Physically move the `.md` file from the source skillpack directory to the target skillpack directory
4. **Update session reports**: Ensure the skill's session report is appropriate for the new skillpack
5. **Update related references**: Check and update any references to the skill's location in documentation

## Environment Variables

This skill requires the following environment variables (configured via `.env.example`):
- `SKILLS_API_URL` - skills.sh API endpoint (required)
- `SKILLS_REGISTRY_URL` - skills registry URL (required)
- `GITHUB_TOKEN` - GitHub personal access token (optional, for GitHub API access)
- `OPENAI_API_KEY` - OpenAI API key (optional, for AI features)
- `ANTHROPIC_API_KEY` - Anthropic API key (optional, for AI features)

## Session Reports

Full session reports are generated and included in the export metaprompt. Each report documents:
- The skill creation process and design decisions
- Environment variables used
- Verification status against skills specification docs
- Any truemotive-specific considerations for internal skill development

## Template Skill Creation

New skills can be created using the template at `out/skillpacks/chrismahoney/skillz/templates/SKILL_TEMPLATE.md`, which includes:
- Frontmatter with placeholder variables: `{{skill_id}}`, `{{skill_name}}`, `{{description}}`, `{{author}}`, `{{tags}}`, `{{skill_locator}}`
- Comprehensive usage instructions
- Environment variable documentation
- Verification steps to ensure adherence to skills specification docs