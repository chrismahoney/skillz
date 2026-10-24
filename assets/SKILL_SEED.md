create a skill called chrismahoney/truemotive@appie. then grill me on design decisions about the skill once you have an idea of how it should be organized, etc. (json data formats, prompt format, anything you can think of)

# Meta information about generating this "root" skill

## Initial prompt to begin the process
Use your skill-creator skill to grill-me about the following initial request for skill creation: @/assets/SKILL_SEED.md - consider utilizing the find-skills tool to suggest retrievable skills that we can use in this task.

Acceptance Criteria:
- A fully assembled skillpack (or what it is eventually named) in out/skillpacks/chrismahoney/skillz
-- this appie skill as the first skill included
-- any other skills we end up creating in here along the way (record this for metadata usage in the appie skill if we do create others during this work)
- Verification of adherence to the skills specification docs
- A full session summary per skill in a session-reports/ dir in out/chrismahoney/skillz/session-reports (include this in the template prompt we export
- template prompt we export: out/chrismahoney/skillz/SKILL.md that adheres to spec frontmatter/syntax requirements
- consider needs for env vars like API keys, service URLs etc.

Before we start, grill-me about this "meta" task we're undertaking to allow me and others to build appie to create more appie-friendly skillpacks.

##

# Skill: appie

## Skill Master Data

### Metadata

Skill locator: chrismahoney/skillz@appie
Repo (TBD): chrismahoney/skillz
Skill ID: appie
[Augment this information as part of the process]

## Supplemental information

### Reference Docs
- skills.sh API Reference: https://www.skills.sh/docs/api
- integrations.sh skills.sh registry reference: https://integrations.sh/skills.sh/
- Github repo that serves skills.sh as an API: https://github.com/mastra-ai/skills-api
-- Always include this in the tabular list of github repos
- npx skills CLI repo: https://github.com/vercel-labs/skills
- skills specification docs: https://agentskills.io/specification

### Supplemental files (onboard with skill in repo)
- templates/ directory with deployed current templates for skillpack initialization (including optional github setup), individual skill creation which we're looking at right now, subagent prompts, other AI agent resources
- assets/ directory with any logos, media, whatever
-- SKILLPACK_SEED.md/SKILL_SEED.md - The raw filled out template for the skill or skillpack
- README.md - Usage and functional details
[Augment this filesystem as part of the process]

## Skill Purpose

### Maintain tabular data related to:

- a "skillpack" of skills from all skills.sh pages that are open:
- [Suggest alternative names for this skillpack data object]
-- Metadata for the skill pack collected from the user context provided (skillpack name, optional github repo link, other useful information you can infer)
-- example here: jenkins-pipeline (determine "catalog" schema based on the 
-- capture all skill information from the detail page schema (determine this schema as part of the skill)
--- Main page: https://skills.sh
--- Detail link example: https://skills.sh/aj-geddes/useful-ai-prompts/jenkins-pipeline 
---- Link format: (/[github user]/[github repo for skillset] [optional /[individual skill name]])
- a separate "manifest" of the github repos associated with the "skillpack" list

## Usage

### User will start the call to appie with the name of one skill to start with. you will:
- Record the "skillpack" metadata for this new application pack.
- Record any verified skill entry in a 'skills' data array
- Interpret the description and rich data via the provided API docs
- Provide a running summary block in markdown of the appie skillpack's current state

### User will ask to export

### You will react and respond with skillpack metaprompt
- Export a markdown prompt meant to combine the various "prompt" data from all skills in scope along with instructions for an arbitrary AI coding agent to pull down and assemble the skillpack into project-scoped skills via 'npx skills' usage info via the vercel-labs/skills and mastra-ai/skills-api repos
- You will check with the user if there is any additional information that should be included (docs references, etc) in a metadata "usernotes" field

## Additional functionality

### User can ask for mockup or secondary plan prompt artifacts to be included with metadata
- optionally associated with a specific skills collection repo, or a specific skill
- user may ask to 'FIND' packages and you will help via the https://skills.sh search capability
- user may ask for a 'TEMPLATE' which you will respond to with a current version of this new skill's supplemental template in the templates/ subdirectory