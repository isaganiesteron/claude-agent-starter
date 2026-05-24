---
name: agent-review
description: After completing a task, spawn a fresh sub-agent with zero context to objectively review the output for quality, accuracy, gaps, and improvements. Use when output quality matters and a second opinion would catch things the original pass might have missed.
triggers: review this, check this, verify, second opinion, agent review, quality check, is this good, critique this
---

# Agent Review — Sub-Agent Verification

## When to Use
- After producing a research report, content piece, or strategic recommendation
- When the output will be used for an important decision
- When you want to catch errors or gaps before presenting to the user
- Any time a fresh perspective would improve the output quality

## Why This Works
An agent that has just completed a task is biased toward its own work. It spent effort getting there and is likely to miss its own mistakes. A fresh sub-agent with no context evaluates purely on output quality — no sunk cost, no attachment to the reasoning that produced it.

## How to Execute

### Step 1 — Prepare the Review Package
Collect the output to be reviewed. Do not include:
- The original conversation history
- The reasoning or process that produced the output
- Any context that would bias the reviewer toward validating the work

Only pass the output itself and a description of what it was supposed to achieve.

### Step 2 — Spawn the Reviewer Sub-Agent
Spawn a fresh sub-agent via Task() with:
- The output to review
- A one-sentence description of what the output was supposed to achieve
- These four review criteria:
  1. **Correctness** — Is anything factually wrong, misleading, or unsupported?
  2. **Completeness** — What is missing that should be there?
  3. **Clarity** — Is anything confusing, ambiguous, or poorly structured?
  4. **Improvement** — What one change would most improve this output?

### Step 3 — Collect Review Findings
The reviewer returns a structured assessment:
- Issues found (critical, moderate, minor)
- Specific suggestions for each issue
- Overall quality assessment
- Whether it is ready to present or needs revision

### Step 4 — Act on Findings
- If no significant issues: present the output to the user with a note that it passed review
- If issues found: revise the output addressing the reviewer's findings, then present
- If critical issues: inform the user and discuss how to proceed before presenting

### Step 5 — Report
Tell the user:
- That a review was conducted
- Whether issues were found and what they were
- What was changed as a result (if anything)

## Definition of Done
The review is complete when:
- The reviewer sub-agent has returned a structured assessment
- All critical and moderate issues have been addressed
- The output is ready to present with confidence
