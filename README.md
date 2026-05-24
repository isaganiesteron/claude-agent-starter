# Claude Agent Starter Template

A general-purpose starter for building Claude Code agents — smart assistants that can research, make decisions, control browsers, and execute workflows.

## What This Is

This template gives you a pre-wired foundation so you can focus on defining your agent's identity and purpose rather than building the infrastructure from scratch. Every agent you build starts here and gets specialized through the CLAUDE.md and custom skills you add.

## Folder Structure

```
your-agent/
├── CLAUDE.md                          ← Agent identity, goals, rules, learned rules
├── README.md                          ← This file
├── memory/
│   └── research/                      ← Agent saves research findings here
└── .claude/
    └── commands/                      ← Skills the agent knows how to execute
        ├── chrome.md                  ← Browser control via Chrome DevTools MCP
        ├── research.md                ← Research a topic and save to file
        ├── consensus.md               ← Multi-agent consensus for decisions
        ├── prompt-contract.md         ← Define task scope before executing
        ├── agent-review.md            ← Sub-agent verification of outputs
        ├── reverse-prompt.md          ← Clarifying questions before complex tasks
        ├── skill-creator.md           ← Create new skills from processes or knowledge
        ├── onboard.md                 ← Interview-style setup for new agents
        ├── prompt-master.md           ← Optimizes messy prompts before executing
        ├── humanizer.md               ← Removes AI writing tells from content
        └── fact-checker.md            ← Verifies factual accuracy of any text
```

## Quick Start

### Step 1 — Install Claude Code

**Windows (PowerShell):**
```powershell
irm https://claude.ai/install.ps1 | iex
```

If after install the `claude` command is not recognized, add it to PATH:
```powershell
[Environment]::SetEnvironmentVariable("PATH", "$env:PATH;$env:USERPROFILE\.local\bin", [EnvironmentVariableTarget]::User)
```

Then close and reopen your terminal.

You need a Claude Pro subscription ($20/month) to use Claude Code.

### Step 2 — Create Your Agent Folder

Copy this template folder and rename it to your agent's purpose (e.g. `social-media-agent`). Then open Claude Code inside it:

```cmd
cd your-agent-name
claude
```

### Step 3 — Fill In CLAUDE.md

Open `CLAUDE.md` and fill in the three sections:
- **Identity** — who this agent is and what it does
- **Goals** — what it is working toward
- **Context** — background knowledge it needs

The comments inside guide you on what to write. Keep it focused and specific — the more clearly you define the agent's purpose the better it performs.

### Step 4 — Connect Chrome DevTools MCP (Optional)

If you want the `/chrome` skill to work, follow these steps. Without it the agent can still use all other skills.

**Prerequisites:**
- Node.js installed — check with `node --version`. Download from nodejs.org if needed.
- Google Chrome installed.

**Install the MCP server** (run in terminal outside Claude Code):

```cmd
claude mcp add --scope user chrome-devtools npx -- -y chrome-devtools-mcp@latest
```

The `--scope user` flag makes it available across all your agents. You should see `Added stdio MCP server chrome-devtools... to user config`.

**Launch Chrome with remote debugging** before using browser control:

Windows:
```cmd
"C:\Program Files\Google\Chrome\Application\chrome.exe" --remote-debugging-port=9222
```

Mac:
```bash
/Applications/Google\ Chrome.app/Contents/MacOS/Google\ Chrome --remote-debugging-port=9222
```

**Restart Claude Code** then verify the connection:
```
list all open browser tabs
```

If it returns your open tabs, browser control is working.

### Step 5 — Start Talking to Your Agent

Claude Code reads CLAUDE.md at the start of every session. Your agent will know exactly who it is and what skills it has. Start giving it tasks.

## Pre-Built Skills

| Skill | Command | What It Does |
|---|---|---|
| Chrome Control | `/chrome` | Controls a browser to interact with any web app |
| Research | `/research` | Researches a topic and saves findings to memory/ |
| Consensus | `/consensus` | Spawns multiple agents for better decisions and ideation |
| Prompt Contract | `/prompt-contract` | Agrees on task scope before executing |
| Agent Review | `/agent-review` | Fresh sub-agent reviews completed work for quality |
| Reverse Prompt | `/reverse-prompt` | Asks clarifying questions before complex tasks |
| Skill Creator | `/skill-creator` | Creates a new skill from a process or uploaded knowledge |
| Onboard | `/onboard` | Interview-style setup that writes your agent's identity into CLAUDE.md |
| Prompt Master | `/prompt-master` | Optimizes messy prompts before executing for better output quality |
| Humanizer | `/humanizer` | Removes AI writing tells from any content before it goes out |
| Fact Checker | `/fact-checker` | Verifies factual accuracy of any text or claims |

## Adding Your Own Skills

Create a new `.md` file in `.claude/commands/`. Every skill needs:

```markdown
---
name: skill-name
description: What this skill does and when to use it.
triggers: keyword1, keyword2, keyword3
---

# Skill Title

## When to Use
[Describe trigger conditions]

## How to Execute
[Step by step instructions]

## Definition of Done
[Exact conditions that mean this task is complete]
```

Or just do a process manually with the agent and say "create a skill for what we just did" — the skill-creator skill will package it automatically.

## The Self-Improving Agent

The **Learned Rules** section at the bottom of `CLAUDE.md` grows automatically. When you correct the agent or it makes a mistake, it appends a new rule so the same thing never happens again. Over time your agent gets progressively better at understanding your preferences without you having to re-explain things.

## Specializing This Template

This template is intentionally blank on identity. To create a specialized agent:

1. Copy this folder and rename it to the agent's purpose
2. Fill in CLAUDE.md with identity, goals, and context
3. Add purpose-specific skills to `.claude/commands/`
4. Run it and let the Learned Rules section grow through use

The same template becomes a social media agent, a research agent, an n8n builder, or anything else — just by changing what goes into CLAUDE.md and which skills you add.
