---
id: test-skill
name: test-skill
description: A test skill created to verify the onboarding workflow and skills 'find' operation behavior
author: chrismahoney
tags: [skillpack, appie, test]
skill_locator: chrismahoney/skillz@test-skill
---

## Test Skill

This is a test skill created as part of the onboarding workflow verification. It demonstrates the skill creation process and the `.agents` directory integration.

### Purpose
- Verify the skill creation workflow from appie-onboarding
- Test the `.agents` directory integration when skills are discovered via `npx skills find`
- Demonstrate how new skills are added to the git repo root `.agents` directory

### Usage
This skill is primarily used for onboarding verification and testing the skills.sh CLI integration.

### Environment Variables
This skill follows the appie skillpack pattern and requires:
- `SKILLS_API_URL` - skills.sh API endpoint (required)
- `SKILLS_REGISTRY_URL` - skills registry URL (required)

No additional environment variables are needed for this test skill.

### Verification
- ✅ All 6 required frontmatter fields present: `id`, `name`, `description`, `author`, `tags`, `skill_locator`
- ✅ YAML syntax validated
- ✅ `skill_locator` format matches `<scope>/skillz@<skillpack-name>`: `chrismahoney/skillz@test-skill`
- ✅ Tags follow existing pattern: `[skillpack, appie, test]`
- ✅ Added to `.agents` directory at git repo root per `npx skills add` behavior