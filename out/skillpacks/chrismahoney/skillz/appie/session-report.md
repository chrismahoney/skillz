---
id: session-report
name: session-report
description: A skill for generating and tracking session reports within the appie skillpack
author: chrismahoney
tags: [skillpack, meta, session-report, appie]
skill_locator: chrismahoney/skillz@session-report
---

## Skill Purpose

The `session-report` skill provides specialized functionality for generating and tracking session reports within the `chrismahoney/skillz@appie` skillpack. It complements the foundational `appie` skill by focusing on:

- **Session report generation**: Creates structured markdown session reports documenting skill creation processes, design decisions, and verification status
- **Skill tracking**: Maintains a record of skill development sessions, including environment variables used and adherence to skills specification docs
- **Export integration**: Provides session report data format compatible with the appie skillpack metaprompt export
- **fmetry tracking**: Enables per-skill session summaries for organized development of internal skills

## Usage

### User starts the call to session-report with report type

The skill will:

1. Generate a structured session report markdown based on the specified report type
2. Record the report in the skillpack's session-reports directory
3. Update the `skills` data array with the new session entry
4. Provide a running summary of the skillpack's current session state

### User asks to export session reports

The skill will react and respond with session report data included in the skillpack metaprompt:

- Include session report markdown content in the combined export
- Check with the user if there are specific report types or additional fields to include
- Ensure the `usernotes` field with any user-specific customization requests

## Additional Functionality

### Report Types

The skill supports the following report types:

- `initial` - Initial session report for a new skill (format: appie.md, session-report.md)
- `design` - Design decision documentation
- `verification` - Skillsskills specification adherence verification
- `export` - Export format metadata and instructions

### Environment Variables

The skill uses the same environment variables as the appie skill:

- **Required**: `SKILLS_API_URL`, `SKILLS_REGISTRY_URL`
- **Optional**: `GITHUB_TOKEN`, `OPENAI_API_KEY`, `ANTHROPIC_API_KEY`

### Session Report Format

Each session report follows a consistent structure:

- Skill identifier (ID, locator, author, organization)
- Creation date and report type
- Design process summary
- Key design decisions documented
- Verification status against skills specification
- Related files and notes

## Verification

- Verify adherence to the skills specification docs at https://agentskills.io/specification
- Check frontmatter/syntax requirements are met
- Validate all required frontmatter fields are present: `id`, `name`, `description`, `author`, `skill_locator`, `tags`
- Confirm session report format consistency with appie skillpack conventions
- Validate the `skills` data array entries contain minimum required fields
