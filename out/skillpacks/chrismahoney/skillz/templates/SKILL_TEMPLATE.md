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