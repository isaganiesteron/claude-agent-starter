---
name: prompt-master
description: Optimize a messy, unstructured, or brain-dumped prompt into a clear, well-structured prompt following best practices before executing the task. Use on any complex or long unstructured request to improve output quality.
triggers: optimize this prompt, prompt master, clean up this prompt, structure this, brain dump, messy prompt, optimize before running
---

# Prompt Master

## When to Use
- When the user gives a long, unstructured, or brain-dumped request
- Before executing any complex multi-step task
- When the request is ambiguous or could be interpreted multiple ways
- Auto-trigger when a prompt is medium to long and unstructured

## How to Execute

### Step 1 — Analyze the Raw Input
Read the original prompt carefully and identify:
- The core intent — what is actually being asked for
- Key requirements that are stated explicitly
- Implicit requirements that are assumed but not stated
- Ambiguities that could lead to the wrong output
- Any context that should be pulled in to make the prompt stronger

### Step 2 — Check Existing Context
Before optimizing, check if there is relevant context already available:
- Look in memory/research/ for relevant background knowledge
- Check CLAUDE.md for relevant agent context, tone, or preferences
- Pull in any relevant context to make the optimized prompt more specific and accurate

### Step 3 — Restructure the Prompt
Rewrite the prompt following these best practices:

**Role** — Define who Claude is for this task if relevant
**Context** — Provide the essential background needed to do the task well
**Task** — State the exact task clearly and specifically in one sentence
**Requirements** — List specific requirements, constraints, and preferences
**Format** — Specify exactly what the output should look like
**Tone** — Define the voice and style if the output is written content

Keep the optimized prompt concise. Remove filler, repetition, and vague language. Replace general requests with specific ones.

### Step 4 — Present the Optimized Prompt
Show the user the optimized prompt clearly and explain in 2-3 bullet points what was changed and why.

Ask: "Should I run this optimized prompt now or would you like to adjust anything first?"

### Step 5 — Execute
Once confirmed, run the task using the optimized prompt rather than the original.

## Definition of Done
The skill is complete when:
- The original prompt has been restructured following best practices
- Relevant context has been pulled in where available
- The optimized prompt has been presented and confirmed
- The task has been executed using the optimized version
