## Skillpack Management

### Specifying Skillpacks

Users can specify which skillpack to use by updating the `skill_locator` frontmatter field in their `SKILL.md` files. The format is:

```
skill_locator: <scope>/skillz@<skillpack-name>
```

Examples:
- `skill_locator: chrismahoney/skillz@appie` - Use appie skillpack
- `skill_locator: chrismahoney/skillz@new-skillpack` - Use new-skillpack
- `skill_locator: chrismahoney/skillz@another-skillpack` - Use another-skillpack

### Moving Skills Between Skillpacks

The Skillpack Management feature enables users to move skills between packs by:

1. **Updating the `skill_locator` frontmatter** in the skill's `SKILL.md` file to point to the new skillpack
2. **Physically moving the `.md` file** to the new skillpack's directory

Example: Moving a skill from appie to another-skillpack:
```bash
# 1. Update skill_locator in the SKILL.md frontmatter
# 2. Move the file
mv out/skillpacks/chrismahoney/skillz/appie/skill-name.md \
   out/skillpacks/chrismahoney/skillz/another-skillpack/skill-name.md
```

### Skillpack Directory Structure

All skillpacks follow a consistent structure:

```
out/skillpacks/chrismahoney/skillz/<skillpack-name>/
├── <skillname>.SKILL.md          # Skill metadata and documentation
├── session-reports/              # Per-skill session summaries
│   └── <skillname>.md
├── templates/                    # Skill creation templates
│   └── SKILL_TEMPLATE.md
└── README.md                     # Optional skillpack documentation
```

## How to Create a New Skillpack

### Step 1: Create Skillpack Directory

```bash
mkdir -p out/skillpacks/chrismahoney/skillz/<skillpack-name>
```

### Step 2: Add Foundational Skill (`SKILL.md`)

Create with required frontmatter:
- `id`: `<skill-id>` (the skill ID)
- `name`: `<skill-name>` (the skill name)
- `description`: Brief description of what the skill does
- `author`: `chrismahoney` (the author/organization)
- `tags`: Optional tags array for categorization (e.g., `[skillpack, meta]`)
- `skill_locator`: `<scope>/skillz@<skillpack-name>` (the full locator)

## Export Format

The export combines:
- **metadata** - Skillpack and skill metadata
- **skills data array** - Array of skill objects with full metadata
- **session reports** - Per-skill session summaries
- **usernotes** - User notes and additional information (check with user for additional info)
- **npx instructions** - Usage info for `npx skills` CLI

The metaprompt combines prompt data from all skills + `npx skills` usage info.

## Additional Skills

Once the foundational three skillpacks (appie, new-skillpack, another-skillpack) are complete, users can:

1. Create additional skills within existing skillpacks
2. Create new skillpacks for different domains or purposes
3. Move skills between skillpacks using the Skillpack Management feature
4. Update WORKING_SKILL_SEED.md to reflect new skills and completion status