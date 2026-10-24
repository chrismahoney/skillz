---
id: another-skillpack
name: another-skillpack
description: A skillpack for additional skills beyond the appie and new-skillpack foundational skills
author: chrismahoney
tags: [skillpack, another-skillpack, truemotive, appie, new-skillpack]
skill_locator: another-skillpack/skillz@another-skillpack
---

## Skill Purpose

The `another-skillpack` skillpack serves as an extension to the existing skillpacks, providing a framework for additional skills that complement the appie and new-skillpack foundational skills. It maintains consistency with the skillz ecosystem while introducing new capabilities and use cases.

## Usage

### User starts the call to another-skillpack with a skill name

The skill will:
1. Record the "skillpack" metadata for this new application pack
2. Record any verified skill entry in a `'skills'` data array
3. Interpret the description and rich data via the provided API docs
4. Provide a running summary block in markdown of the another-skillpack skillpack's current state

### User asks to export

The skill will react and respond with a skillpack metaprompt:
- Export a markdown prompt meant to combine the various "prompt" data from all skills in scope
- Along with instructions for an arbitrary AI coding agent to pull down and assemble the skillpack into project-scoped skills via `'npx skills'` usage info via the vercel-labs/skills and mastra-ai/skills-api repos
- Check with the user if there is any additional information that should be included (docs references, etc.) in a metadata "usernotes" field

## Additional Functionality

### Environment Variables

The skill requires the following environment variables (configured via `.env.example`):
- `SKILLS_API_URL` - skills.sh API endpoint (required)
- `SKILLS_REGISTRY_URL` - skills registry URL (required)
- `GITHUB_TOKEN` - GitHub personal access token (optional, for GitHub API access)
- `OPENAI_API_KEY` - OpenAI API key (optional, for AI features)
- `ANTHROPIC_API_KEY` - Anthropic API key (optional, for AI features)

### Session Reports

Full session reports are generated and included in the export metaprompt. Each report documents:
- The skill creation process and design decisions
- Environment variables used
- Verification status against skills specification docs
- Any truemotive-specific considerations for internal skill development

### Template Skill Creation

New skills can be created using the template at `out/skillpacks/chrismahoney/skillz/templates/SKILL_TEMPLATE.md`, which includes:
- Frontmatter with placeholder variables: `{{skill_id}}`, `{{skill_name}}`, `{{description}}`, `{{author}}`, `{{tags}}`, `{{skill_locator}}`
- Comprehensive usage instructions
- Environment variable documentation
- Verification steps to ensure adherence to skills specification docs

### Skillpack Management

#### Specifying Skillpack

When creating a new skill, you can specify a new or existing skillpack from the list of current ones in `out/skillpacks/`. The skillpack selection determines:

1. **Skill Locator**: The `skill_locator` frontmatter field should follow the format `<scope>/skillz@<skillpack_name>`, where `<scope>` is your developer entity (e.g., `chrismahoney`, `new-skillpack`, `another-skillpack`, `truemotive`) and `<skillpack_name>` is the name of the skillpack.

2. **Current Skillpacks List**: To view all available skillpacks, examine the directory structure under `out/skillpacks/`:
   - `out/skillpacks/chrismahoney/skillz/appie/` - appie skillpack
   - `out/skillpacks/chrismahoney/skillz/new-skillpack/` - new-skillpack skillpack
   - `out/skillpacks/chrismahoney/skillz/another-skillpack/` - another-skillpack skillpack
   - Additional skillpack directories as they are created

3. **Creating in a Specific Skillpack**: To create a new skill in an existing skillpack, specify the target skillpack's `skill_locator` in the new skill's frontmatter. For example, to add a skill to the `another-skillpack` skillpack, use:
   ```yaml
   skill_locator: another-skillpack/skillz@another-skillpack
   ```

#### Moving Skills Between Skillpacks

Skills can be moved freely between skillpacks by updating the `skill_locator` frontmatter field:

1. **Identify the skill's current `skill_locator`**: e.g., `chrismahoney/skillz@appie`

2. **Update the `skill_locator`** to the target skillpack: e.g., `chrismahoney/skillz/another-skillpack`

3. **Move the skill's SKILL.md file**: Physically move the `.md` file from the source skillpack directory to the target skillpack directory:
   - From: `out/skillpacks/chrismahoney/skillz/appie/`
   - To: `out/skillpacks/chrismahoney/skillz/another-skillpack/`

4. **Update session reports**: Ensure the skill's session report is appropriate for the new skillpack, or create a new session report in the target skillpack's `session-reports/` directory.

5. **Update related references**: Check and update any references to the skill's location in documentation, export metaprompts, or other skills' session reports.

#### Skillpack Directory Structure

Each skillpack follows this consistent structure under `out/skillpacks/<scope>/skillz/`:

```text
<skillpack_name>/
├ <skill_name>.SKILL.md              # Skill metadata with frontmatter
├ session-report.md                   # Skill-specific session report
├ templates/
│   └ SKILL_TEMPLATE.md               # Template for creating sub-skills
└ session-reports/
    └ <skill_name>.md                 # Initial session report for the skill
```

#### Example: Moving the `session-report` Skill from appie to another-skillpack

1. Update `session-report.md`'s `skill_locator` from `chrismahoney/skillz@appie` to `chrismahoney/skillz/another-skillpack`
2. Move `session-report.md` from `out/skillpacks/chrismahoney/skillz/appie/` to `out/skillpacks/chrismahoney/skillz/another-skillpack/`
3. The skill is now part of the `another-skillpack` skillpack while maintaining its session report