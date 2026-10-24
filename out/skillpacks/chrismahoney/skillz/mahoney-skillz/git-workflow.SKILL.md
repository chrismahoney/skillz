---
id: git-workflow
name: git-workflow
description: A skill that provides git workflow automation and best practices for the chrismahoney/skillz@mahoney-skillz skillpack
author: chrismahoney
tags: [skillpack, mahoney, git]
skill_locator: chrismahoney/skillz@mahoney-skillz
---

## Git Workflow Skill

This skill provides automated git workflow commands and best practices for the mahoney-skillz skillpack.

### Features
- Automated commit message generation
- Branch management utilities
- PR template suggestions
- Code review checklists

### Usage
```bash
# Example usage within skillz ecosystem
npx skills run git-workflow --help
```

### Environment Variables
This skill requires the following environment variables (configured via `.env`):

- `GIT_AUTHOR_NAME` - Git author name (required)
- `GIT_AUTHOR_EMAIL` - Git author email (required)
- `GIT_COMMITTER_NAME` - Git committer name (required)
- `GIT_COMMITTER_EMAIL` - Git committer email (required)

### Session Report
A session report documenting this skill's creation process should be created in `session-reports/git-workflow.md`.

### Verification
- ✅ All 6 required frontmatter fields present: `id`, `name`, `description`, `author`, `tags`, `skill_locator`
- ✅ YAML syntax validated
- ✅ `skill_locator` format matches `<scope>/skillz@<skillpack-name>`: `chrismahoney/skillz@mahoney-skillz`
- ✅ Tags follow existing pattern: `[skillpack, mahoney, git]`