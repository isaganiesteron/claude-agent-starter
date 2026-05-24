---
name: reverse-prompt
description: Before starting a complex task, identify and ask the user 3-5 clarifying questions that would significantly affect the output. Use to surface unstated assumptions, preferences, and constraints before investing effort in the wrong direction.
triggers: reverse prompt, clarify, what do you need, before I start, ask me questions, what are you expecting, make sure we're aligned
---

# Reverse Prompting

## When to Use
- Before starting any task where the wrong assumptions would produce a useless output
- When the request is open to multiple valid interpretations
- When personal preferences, style, or context would significantly affect the result
- When you notice you are about to assume something important

## How to Execute

### Step 1 — Analyze the Request
Before asking anything, think through:
- What is explicitly stated vs. what is assumed
- What decisions you would have to make that the user might have opinions about
- What context would change your approach significantly if you had it
- What a "wrong" output would look like — what led to it

### Step 2 — Generate Candidate Questions
Identify 5-7 questions that would genuinely improve the output. For each ask:
- Would the answer meaningfully change what I produce?
- Is this something the user likely has a preference about?
- Is this something I could not reasonably infer from context?

If the answer to all three is yes — include the question.
If you could reasonably infer the answer from context — skip it.

### Step 3 — Select the Best 3-5
From your candidates, select the 3-5 questions that would have the highest impact on output quality. Do not ask more than 5 — asking too many signals poor judgment.

Order them from most impactful to least impactful.

### Step 4 — Ask Clearly
Present the questions in a natural, conversational way. Do not number them robotically or make it feel like a form. Frame them as genuine curiosity about getting this right.

Example framing:
"Before I start, a few things would help me get this right for you..."

### Step 5 — Proceed With Answers
Once the user responds, confirm your understanding and proceed. If their answers reveal additional ambiguity, ask one follow-up at most — do not turn this into an interrogation.

Optionally chain into `/prompt-contract` after receiving answers for full task alignment before execution.

## Definition of Done
The reverse prompt is complete when:
- 3-5 high-impact clarifying questions have been asked
- The user has responded
- You have enough context to proceed with confidence
