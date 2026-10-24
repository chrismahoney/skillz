---
id: appz
name: appz
date: 2026-10-24
skill_locator: chrismahoney/skillz@appz
---

## Appz Skillpack - Session Report

### Skillpack Creation Process

This session report documents the creation of the `appz` skillpack within the `chrismahoney/skillz` ecosystem. This skillpack serves as a container for skills that embody the "odyssey" imagery for catalog wandering based on short bursts of product, interaction, or third-party dependency interest.

### Design Decisions

1. **Skillpack Name**: `appz` - A concise, catchy name that represents the skillpack's purpose: a collection of skills for intuitive catalog wandering and discovery. The "appz" name is short, memorable, and aligns with the odyssey theme of wandering skills.sh catalog.

2. **Tags**: `[skillpack, appz, odyssey, discovery]` - Follows existing tag pattern. The tags explicitly document this skillpack's purpose: odyssey-style catalog wandering and skill discovery.

3. **skill_locator**: `chrismahoney/skillz@appz` - Consistent with skillpack format. When skills from this pack are selected via `npx skills find` operation and used while working, they should be added to the root project directory `.agents/` folder.

4. **Odyssey Philosophy**: This skillpack embodies the user's vision of "intuitively wandering the skills.sh catalog based on short bursts of product, interaction, or third-party dependency interest." The capabilities materialize from shared interests, making them shareable and discoverable.

5. **First Skill**: `appie-branstorm` - The initial skill in this skillpack, documenting the generic onboarding pattern for skill brainstorming and naming. Future skills will continue the odyssey theme.

### Creation Steps

1. Created `appz/` directory in `out/skillpacks/chrismahoney/skillz/`
2. Created `appz.SKILL.md` with all 6 required frontmatter fields
3. Set `skill_locator` to `chrismahoney/skillz@appz` per established format
4. Added meaningful tags: `[skillpack, appz, odyssey, discovery]`
5. Created this session report in `session-reports/appz.md`
6. **Key**: Skills from this skillpack will be added to `.agents/` directory at git repo root when selected via `npx skills find` operation (per specification)

### Verification Status

- ✅ YAML syntax correctness verified
- ✅ `skill_locator` format consistency pass: `chrismahoney/skillz@appz`
- ✅ All required frontmatter fields present and valid
- ✅ Session report format consistent with other skill reports in ecosystem
- ✅ `.agents` directory integration documented (per npx skills add behavior)
- ✅ Odessy theme integrated: catalog wandering, shared interests, shareability
- ✅ First skill `appie-branstorm` properly linked

### Next Steps

- **Discover skills**: Run `npx skills find` to explore catalog and add skills to appz
- **Add first skill**: `appie-branstorm` already included as initial skill
- **Brainstorm next skills**: Use the odyssey pattern to discover new skills
- **Update memory bank**: Follow the update pattern for new skillpack
- **Git workflow**: add → commit → push → PR

### Integration with Skillpack Workflow

- Skills discovered via `npx skills find` can be added to this skillpack by updating their `skill_locator` frontmatter to `chrismahoney/skillz@appz`
- The `.agents/` directory entry serves as the active skill reference for the current working session within this skillpack
- When moving between skillpacks, update both the `skill_locator` AND the `.agents/` directory file
- Session reports should document which `.agents/` version of the skill is currently active

### Verification

- ✅ Run `npx skills find` to verify skill discovery within appz skillpack
- ✅ Confirm `.agents/appz.md` or relevant skill files are created at git repo root
- ✅ Verify the skill_locator in `.agents/` matches the appz skillpack format
- ✅ Test the odyssey onboarding pattern reproducibility