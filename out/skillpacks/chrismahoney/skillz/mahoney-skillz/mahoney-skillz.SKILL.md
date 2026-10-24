---
id: mahoney-skillz
name: mahoney-skillz
description: A skillpack for managing the mahoney-skillz collection of skills, following the chrismahoney/skillz pattern with consistent metadata and session reporting
author: chrismahoney
tags: [skillpack, mahoney, truemotive]
skill_locator: chrismahoney/skillz@mahoney-skillz
---

## Skillpack Overview

The `chrismahoney/skillz@mahoney-skillz` skillpack is the 4th skillpack in the skillz ecosystem, following the established pattern of `appie`, `new-skillpack`, and `another-skillpack`. It provides a structured collection of skills with consistent metadata and session reporting.

### Skillpack Directory Structure

```out/skillpacks/chrismahoney/skillz/mahoney-skillz/
├ mahoney-skillz.SKILL.md              # Foundational skillpack metadata
├ session-report.md                    # Session report for mahoney-skillz skillpack
└ session-reports/
    └ mahoney-skillz.md                # Initial session report
```

### Skillpack Management

This skillpack follows the same management patterns as the other skillpacks:

- **Skill Locator**: Use `chrismahoney/skillz@mahoney-skillz` to reference skills in this skillpack
- **Moving Skills**: Skills can be moved between skillpacks by updating the `skill_locator` frontmatter and physically moving `.md` files
- **Session Reports**: Each skill within this skillpack should have a session report in `session-reports/`

### Environment Variables

This skillpack requires the following environment variables (configured via `.env.example`):

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