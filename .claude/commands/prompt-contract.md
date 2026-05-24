---
name: prompt-contract
description: Before executing any non-trivial task, generate a structured contract defining the goal, constraints, output format, and definition of done. Present it for user approval before proceeding. Use this to prevent misaligned work and wasted effort on complex tasks.
triggers: prompt contract, define task, scope this, clarify task, before we start, plan this out
---

# Prompt Contract

## When to Use
- Before starting any task that will take more than a few steps
- When a request is vague or open to multiple interpretations
- When the wrong output would waste significant time or effort
- When you need the user to align on what "done" looks like before you start

## How to Execute

### Step 1 — Analyze the Request
Read the user's request and identify:
- What they explicitly asked for
- What they implicitly assumed but did not say
- What could be interpreted multiple ways
- What constraints likely apply even if unstated
- What a failure would look like

### Step 2 — Draft the Contract
Structure the contract with exactly these four sections:

**Goal**
One clear sentence stating what will be produced or achieved.

**Constraints**
Bullet list of boundaries, requirements, and limitations that apply.
Include both stated and reasonably inferred constraints.

**Output Format**
Exactly what the deliverable will look like — format, length, structure, location.

**Definition of Done**
The specific conditions that must be true for this task to be considered complete.
Be concrete. Avoid vague terms like "good quality" — define what good looks like.

### Step 3 — Present for Approval
Present the contract clearly and ask:
"Does this match what you want? Any changes before I proceed?"

Do not start the task until the user explicitly approves.

### Step 4 — Execute Against the Contract
Once approved, use the contract as your guide throughout execution.
If something unexpected arises that would require deviating from the contract, pause and inform the user rather than silently changing direction.

## Definition of Done
The contract is complete when:
- All four sections are clearly defined
- The user has reviewed and approved the contract
- Execution has begun against the approved scope
