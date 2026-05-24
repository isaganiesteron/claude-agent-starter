---
name: consensus
description: Spawn multiple sub-agents with slightly varied analytical framings to independently analyze a problem, then aggregate results by consensus, divergence, and outliers. Use for strategic decisions, ideation, content planning, or any question where a single perspective might miss something important.
triggers: consensus, multiple perspectives, brainstorm, best option, what should I, decide, ideate, explore options, varied ideas
---

# Stochastic Multi-Agent Consensus

## When to Use
- Strategic decisions where one answer might be biased or incomplete
- Content ideation where you want maximum variety of ideas
- Evaluating options where you want stress-tested recommendations
- Any question where "what am I missing?" matters
- Research synthesis where multiple analytical lenses add value

## How to Execute

### Step 1 — Define the Question
Clearly state:
- The core question or problem to analyze
- Any relevant context sub-agents need to know
- How many sub-agents to spawn (default: 5, use 3 for quick pass, 10 for thorough)
- What kind of output is needed (ideas, ranking, recommendation, analysis)

### Step 2 — Generate Varied Framings
Create N distinct analytical framings of the same question. Each framing should approach the problem from a genuinely different angle. Examples of framing variations:
- Conservative vs. bold perspective
- User/audience perspective
- Skeptic/devil's advocate perspective
- Data and measurability focused
- Resource-constrained perspective
- Long-term vs. short-term lens
- Competitor or outside observer perspective

### Step 3 — Spawn Sub-Agents
For each framing, spawn a sub-agent via Task() with:
- The core question
- Its specific analytical framing as an instruction
- Relevant context
- A request to produce 3-5 specific, actionable ideas or recommendations

Each sub-agent runs independently with no knowledge of the others.

### Step 4 — Collect and Aggregate Results
Once all sub-agents complete, aggregate their outputs:

**Consensus Items** — ideas or recommendations that appeared across 3+ agents
These are your safest, most validated options. High confidence.

**Divergent Items** — ideas that appeared in 2 agents
These are worth examining. May represent legitimate alternative approaches.

**Outliers** — ideas that only one agent produced
These are wildcards. Could be brilliant or irrelevant. Flag for human judgment.

### Step 5 — Synthesize and Present
Present findings in this format:
- Brief context summary
- Consensus recommendations (with frequency count)
- Divergent ideas worth considering
- Outlier ideas flagged for human review
- Recommended next action based on consensus

## Definition of Done
The task is complete when:
- All sub-agents have completed and returned results
- Results have been aggregated into consensus, divergent, and outlier categories
- A clear synthesis with recommended next action has been presented
- Raw sub-agent outputs are available if the user wants to review them
