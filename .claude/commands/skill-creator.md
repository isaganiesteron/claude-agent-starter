---
name: skill-creator
description: Create a new skill file from either a completed process or uploaded knowledge. Packages workflows, processes, and knowledge into reusable skill files saved to .claude/commands/. Use after completing any repeatable process or when given a document, transcript, or course to turn into a skill.
triggers: create a skill, build a skill, package this as a skill, make a skill, skill for what we just did, turn this into a skill, create skill from this
---

# Skill Creator

## When to Use
- After completing a process manually that you will need to repeat in the future
- When given a document, transcript, course, or framework to convert into a skill
- When you want to standardize how a recurring task gets done
- Any time someone says "create a skill" or "package this as a skill"

## How to Execute

### Step 1 — Identify the Source
Determine what the skill is being built from:

**Option A — From a completed session process:**
Look back at the current conversation. Identify the full sequence of steps taken, decisions made, tools used, and the format of the final output. Extract the repeatable pattern from what was done.

**Option B — From uploaded knowledge (document, transcript, course):**
Read the provided content thoroughly. Identify the core process, methodology, or framework being described. Extract the key steps, rules, and principles that define how the process works.

### Step 2 — Define the Skill
Before writing anything, clarify:
- What is the skill's single clear purpose?
- What are the trigger words someone would naturally say to invoke it?
- What are the exact steps in the process?
- What does a completed, successful output look like?
- What are the failure conditions — what would make the output wrong or incomplete?

### Step 3 — Write the Skill File
Structure the skill file exactly as follows:

```
---
name: [short-kebab-case-name]
description: [One sentence describing what this skill does and when to use it. Be specific enough that Claude knows exactly when to auto-invoke it.]
triggers: [comma separated list of natural language phrases that would indicate this skill should be used]
---

# [Skill Title]

## When to Use
[2-3 sentences describing the exact conditions that call for this skill]

## How to Execute

### Step 1 — [Step Title]
[Clear instructions for this step]

### Step 2 — [Step Title]
[Clear instructions for this step]

[Continue for all steps]

## Definition of Done
[Bullet list of specific, concrete conditions that must all be true for this task to be complete. Avoid vague terms — be measurable and specific.]
```

### Step 4 — Handle Reference Material
If the skill is based on a document, transcript, or course that contains detailed reference material (formulas, templates, examples, frameworks):

- Create a subfolder in `.claude/commands/` named after the skill
- Save the skill file as `SKILL.md` inside that subfolder
- Save key reference material as separate files in the same subfolder (e.g. `templates.md`, `examples.md`, `formulas.md`)
- Reference these files from within the SKILL.md where relevant

If the skill is a simple process with no reference material, save it as a single file directly in `.claude/commands/`.

### Step 5 — Save the File
Save the completed skill file to `.claude/commands/[skill-name].md`

Or if it has reference material: `.claude/commands/[skill-name]/SKILL.md`

### Step 6 — Confirm and Summarize
Tell the user:
- The skill name and where it was saved
- The trigger words that will invoke it
- A one sentence summary of what it does
- Any reference files that were created alongside it

## Definition of Done
The skill is complete when:
- The skill file is saved to `.claude/commands/`
- It has a properly formatted YAML front matter block with name, description, and triggers
- It has clear step by step instructions that someone could follow without additional context
- It has a concrete definition of done
- Any reference material has been saved as separate files if needed
- The user has been told the skill name, location, and trigger words
