---
id: appie-pickbandname
name: appie-pickbandname
date: 2026-10-24
skill_locator: chrismahoney/skillz@appie-pickbandname
---

## Appie Pick Band Name - Session Report (Generic Onboarding Pattern)

### Skill Creation Process

This session report documents the creation of the `appie-pickbandname` skill within the `chrismahoney/skillz@appie` skillpack. This skill serves as a generic onboarding guide for discovering, naming, and integrating new skills into the skillz ecosystem.

### Design Decisions

1. **Skill Name**: `appie-pickbandname` - While originally conceived for band name selection, this skill's generic pattern applies to naming any new skill or skillpack in the ecosystem. The "pick" action metaphor works for discovering and selecting skills from the catalog.

2. **Tags**: `[skillpack, appie, discovery, naming, onboarding, skillpack-creation]` - Follows existing tag pattern. The tags explicitly document this skill's purpose: discovery, naming, and onboarding new skills.

3. **skill_locator**: `chrismahoney/skillz@appie-pickbandname` - Consistent with appie skillpack format.

4. **Generic Onboarding Philosophy**: This skill embodies the pattern we've been through together: when short bursts of product, interaction, or third-party dependency interest strike, there's a need to quickly find or create the right skill. This skill guides users through:
   - Discovering existing skills in the catalog
   - Naming new skills appropriately
   - Onboarding them with proper frontmatter and session reports
   - Integrating them via the `.agents` directory pattern

5. **`.agents` Directory Integration**: Following the specification from earlier onboarding sessions, when this skill is selected via `npx skills find` operation and used while working in the appie skillpack, it should be added to the root project directory `.agents/` folder, similar to `npx skills add` command behavior.

### Creation Steps

1. Created `appie-pickbandname.SKILL.md` in `out/skillpacks/chrismahoney/skillz/appie/`
2. Verified all 6 required frontmatter fields: `id`, `name`, `description`, `author`, `tags`, `skill_locator`
3. Set `skill_locator` to `chrismahoney/skillz@appie-pickbandname` per established format
4. Added meaningful tags: `[skillpack, appie, discovery, naming, onboarding, skillpack-creation]`
5. Created this session report in `session-reports/appie-pickbandname.md`
6. **Key**: Skill will be added to `.agents/` directory at git repo root when selected via `npx skills find` operation (per specification)

### Verification Status

- ✅ YAML syntax correctness verified
- ✅ `skill_locator` format consistency pass: `chrismahoney/skillz@appie-pickbandname`
- ✅ All required frontmatter fields present and valid
- ✅ Session report format consistent with other skill reports in ecosystem
- ✅ `.agents` directory integration documented (per npx skills add behavior)
- ✅ No env var placeholder defaults (per Q2 decision from appie-onboarding gaps)
- ✅ Generic onboarding pattern documented and reusable

### Next Steps (Reusable Pattern)

- **Discover skills**: Run `npx skills find` to explore the catalog
- **Name a new skillpack**: Use this skill's frontmatter pattern as a template
- **Create the skillpack**: Follow the onboarding workflow we've documented
- **Add first skill**: Create the initial SKILL.md with proper frontmatter
- **Update memory bank**: Follow the 3-file update pattern (activeContext, progress, projectbrief)

### Integration with Skillpack Workflow

- Skills discovered via `npx skills find` can be moved between skillpacks by updating the `skill_locator` frontmatter
- The `.agents/` directory entry serves as the active skill reference for the current working session
- When moving between skillpacks, update both the `skill_locator` AND the `.agents/` directory file
- Session reports should document which `.agents/` version of the skill is currently active

### Verification

- ✅ Run `npx skills find` to verify skill discovery
- ✅ Confirm `.agents/appie-pickbandname.md` is created at git repo root
- ✅ Verify the skill_locator in `.agents/` matches the skillpack format
- ✅ Test the generic onboarding pattern reproducibility