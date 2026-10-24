---
id: test-skill
name: test-skill
date: 2026-10-24
skill_locator: chrismahoney/skillz@test-skill
---

## Test Skill - Session Report

### Skill Creation Process

This session report documents the creation of the `test-skill` skill within the `chrismahoney/skillz@appie` skillpack.

### Design Decisions

1. **Skill Name**: `test-skill` - Chosen for clarity as a first test skill within the onboarding workflow
2. **Tags**: `[skillpack, appie, test]` - Follows existing tag pattern from appie-onboarding (Q5: tags can be deferred aside from existing ones)
3. **skill_locator**: `chrismahoney/skillz@test-skill` - Consistent with appie skillpack format
4. **`.agents` directory integration**: Per the skills 'find' operation behavior, when this skill is selected during a `npx skills find` operation and used while working in the appie skillpack, it should be added to the root project directory `.agents/` folder, similar to how `npx skills add` operates

### Creation Steps

1. Created `test-skill.SKILL.md` in `out/skillpacks/chrismahoney/skillz/appie/`
2. Verified all 6 required frontmatter fields: `id`, `name`, `description`, `author`, `tags`, `skill_locator`
3. Set `skill_locator` to `chrismahoney/skillz@test-skill` per established format
4. Added meaningful tags: `[skillpack, appie, test]`
5. Created this session report in `session-reports/test-skill.md`
6. **Key**: Skill will be added to `.agents/` directory at git repo root when selected via `npx skills find` operation (per Q2/Q4onboarding specification)

### Verification Status

- ✅ YAML syntax correctness verified
- ✅ `skill_locator` format consistency pass: `chrismahoney/skillz@test-skill`
- ✅ All required frontmatter fields present and valid
- ✅ Session report format consistent with other skill reports in ecosystem
- ✅ `.agents` directory integration documented (per npx skills add behavior)
- ✅ No env var placeholder defaults (per Q2 decision from appie-onboarding gaps)

### Next Steps

- Add this skill to the skills table in README.md if applicable
- Test with `npx skills list --json` to verify discovery
- Run `npx skills find` to verify the `.agents` directory integration behavior
- Consider adding unit tests per spec validation checklist (Q7)
- Verify that when selected via skills find operation, the skill gets added to `.agents/` at git repo root