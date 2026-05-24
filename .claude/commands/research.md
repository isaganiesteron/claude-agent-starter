---
name: research
description: Research a topic thoroughly using web search, compile findings, and save results as a markdown file in memory/research/. Use when the agent needs to gather external information to inform decisions or complete a task.
triggers: research, look up, find information, investigate, analyze, study, gather data, what do we know about
---

# Research and Save

## When to Use
- Gathering information on a topic before making a decision
- Competitor analysis
- Trend research
- Background information needed for a task
- Any time external knowledge needs to be brought into the agent's memory

## How to Execute

### Step 1 — Define the Research Scope
Before searching, clarify:
- What specific questions need to be answered
- What depth of research is needed (quick overview vs. thorough analysis)
- What format the output should take
- Where findings will be used

### Step 2 — Search and Gather
- Run multiple targeted web searches with varied query terms
- Do not rely on a single search — cover the topic from multiple angles
- Prioritize authoritative, recent sources
- Note the source URL for every key finding
- Aim for at least 5-10 distinct sources for thorough research

### Step 3 — Synthesize Findings
Organize findings into clear sections:
- **Summary** — 2-3 sentence overview of what was found
- **Key Findings** — the most important discoveries, each with source
- **Patterns and Trends** — what themes emerged across sources
- **Gaps** — what questions remain unanswered
- **Implications** — what this means for the task at hand

### Step 4 — Save to File
Save the compiled research as a markdown file:
- Location: `memory/research/`
- Filename: descriptive and dated, e.g. `competitor-analysis-2025-05.md`
- Include the date researched at the top of the file
- Include all source URLs

### Step 5 — Report
- Summarize the key findings to the user
- Reference the saved file location
- Flag anything surprising or that requires a decision

## Definition of Done
The task is complete when:
- At least 5 distinct sources have been consulted
- Findings are synthesized into a clear, structured summary
- The research file has been saved to memory/research/
- Key findings and implications have been reported to the user
