---
id: git-workflow
name: git-workflow
date: 2026-10-24
skill_locator: chrismahoney/skillz@mahoney-skillz
---

## Git Workflow Skill - Session Report

### Skill Creation Process

This session report documents the creation of the `git-workflow` skill within the `chrismahoney/skillz@mahoney-skillz` skillpack.

### Design Decisions

1. **Skill Name**: `git-workflow` - Chosen for clarity and discoverability within the skills.sh CLI
2. **Tags**: `[skillpack, mahoney, git]` - Follows existing tag pattern from appie-onboarding interrogation (Q5: tags can be deferred aside from existing ones)
3. **skill_locator**: `chrismahoney/skillz@mahoney-skillz` - Consistent with mahoney-skillz skillpack format
4. **No env var defaults**: Per Q2 decision, all env vars must be set explicitly by the user - `GIT_AUTHOR_NAME`, `GIT_AUTHOR_EMAIL`, `GIT_COMMITTER_NAME`, `GIT_COMMITTER_EMAIL`

### Creation Steps

1. Created `git-workflow.SKILL.md` in `out/skillpacks/chrismahoney/skillz/mahoney-skillz/`
2. Verified all 6 required frontmatter fields: `id`, `name`, `description`, `author`, `tags`, `skill_locator`
3. Set `skill_locator` to `chrismahoney/skillz@mahoney-skillz` per established format
4. Added meaningful tags: `[skillpack, mahoney, git]`
5. Created this session report in `session-reports/git-workflow.md`
6. No placeholder defaults for environment variables - all must be set explicitly

### Verification Status

- ✅ YAML syntax correctness verified
- ✅ `skill_locator` format consistency pass: `chrismahoney/skillz@mahoney-skillz`
- ✅ All required frontmatter fields present and valid
- ✅ Session report format consistent with other skill reports in ecosystem
- ✅ No env var placeholder defaults (per Q2 decision from appie-onboarding gaps)

### Next Steps

- Add this skill to the skills table in README.md if applicable
- Test with `npx skills list --json` to verify discovery
- Consider adding unit tests per spec validation checklist (Q7)