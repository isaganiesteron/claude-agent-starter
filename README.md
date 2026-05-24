# Claude Agent Starter Template

A general-purpose starter for building Claude Code agents — smart assistants that can research, make decisions, control browsers, and execute workflows.

## What This Is

This is a GitHub template repository. Every new agent you build starts from here — one click to create, then specialize it for its purpose. No setup from scratch, no copy-pasting files. Just clone, onboard, and go.

## Folder Structure

```
your-agent/
├── CLAUDE.md                          ← Agent identity, goals, rules, learned rules
├── README.md                          ← This file
├── memory/
│   ├── MEMORY.md                      ← Index of all accumulated knowledge
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

---

## Prerequisites

Before creating your first agent, do this once.

### 1 — Install Claude Code

**Windows (PowerShell):**

```powershell
irm https://claude.ai/install.ps1 | iex
```

If `claude` is not recognized after install, add it to PATH:

```powershell
[Environment]::SetEnvironmentVariable("PATH", "$env:PATH;$env:USERPROFILE\.local\bin", [EnvironmentVariableTarget]::User)
```

Close and reopen your terminal. You need a **Claude Pro subscription** ($20/month) to use Claude Code.

### 2 — Connect Chrome DevTools MCP (Optional)

Only needed if you want browser control via the `/chrome` skill. Skip if not needed — all other skills work without it.

**Requirements:** Node.js (`node --version` to check — download from nodejs.org if missing) and Google Chrome.

**Install the MCP server** (run once in terminal outside Claude Code):

```cmd
claude mcp add --scope user chrome-devtools npx -- -y chrome-devtools-mcp@latest
```

**Launch Chrome with remote debugging** every time you want to use browser control:

Windows:

```cmd
"C:\Program Files\Google\Chrome\Application\chrome.exe" --remote-debugging-port=9222
```

Mac:

```bash
/Applications/Google\ Chrome.app/Contents/MacOS/Google\ Chrome --remote-debugging-port=9222
```

Verify it works inside Claude Code by typing: `list all open browser tabs`

---

## Creating a New Agent

### Step 1 — Use This Template

On GitHub, click **"Use this template"** → **"Create a new repository"**. Name it after the agent's purpose (e.g. `social-media-agent`, `research-agent`, `n8n-builder`). Then clone it locally:

```cmd
git clone https://github.com/YOUR-USERNAME/your-agent-name.git
cd your-agent-name
```

### Step 2 — Open in Claude Code

```cmd
claude
```

Or open the folder in VS Code with the Claude Code extension installed.

### Step 3 — Run Onboarding

The agent will automatically detect it hasn't been set up yet and run `/onboard` on first launch. It will interview you like a new virtual assistant on their first day — asking about your business, the role, goals, working style, and tools.

Once you answer the questions the agent writes its own identity into `CLAUDE.md`. No manual file editing required.

You can also trigger it manually anytime:

```
/onboard
```

### Step 4 — Start Working

That's it. Your agent is ready. Start giving it tasks. It will:

- Use its skills automatically based on what you ask
- Save research to `memory/research/` and update the knowledge index
- Improve over time by appending learned rules when you correct it
- Check existing knowledge before re-researching anything

---

## Pre-Built Skills

| Skill           | Command            | What It Does                                                          |
| --------------- | ------------------ | --------------------------------------------------------------------- |
| Onboard         | `/onboard`         | Interview-style setup that writes the agent's identity into CLAUDE.md |
| Chrome Control  | `/chrome`          | Controls a browser to interact with any web app                       |
| Research        | `/research`        | Researches a topic and saves findings to memory/                      |
| Consensus       | `/consensus`       | Spawns multiple agents for better decisions and ideation              |
| Prompt Contract | `/prompt-contract` | Agrees on task scope before executing                                 |
| Agent Review    | `/agent-review`    | Fresh sub-agent reviews completed work for quality                    |
| Reverse Prompt  | `/reverse-prompt`  | Asks clarifying questions before complex tasks                        |
| Prompt Master   | `/prompt-master`   | Optimizes messy prompts before executing for better output quality    |
| Humanizer       | `/humanizer`       | Removes AI writing tells from any content before it goes out          |
| Fact Checker    | `/fact-checker`    | Verifies factual accuracy of any text or claims                       |
| Skill Creator   | `/skill-creator`   | Creates a new skill from a completed process or uploaded knowledge    |

---

## Adding Your Own Skills

The easiest way — do a process manually with the agent, then say:

```
create a skill for what we just did
```

The `/skill-creator` skill packages the whole process automatically.

Or create a `.md` file manually in `.claude/commands/`:

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

---

## How the Agent Improves Over Time

**Learned Rules** — The `Learned Rules` section at the bottom of `CLAUDE.md` grows automatically. Every time you correct the agent it appends a new rule so the same mistake never happens again.

**Knowledge Base** — Every research task saves findings to `memory/research/` and updates `memory/MEMORY.md`. Future sessions build on this knowledge rather than starting fresh.

**New Skills** — Any repeatable process you do manually can be packaged as a skill on the spot. Over time your agent accumulates skills for everything it regularly does.

The longer you use an agent the better it gets — at understanding your preferences, avoiding past mistakes, and executing recurring tasks without needing re-explanation.

---

## Examples of Agents You Can Build

- **Social Media Agent** — researches trends, writes content, builds content calendars
- **Research Agent** — deep dives on any topic, saves structured findings, synthesizes insights
- **n8n Builder** — controls the n8n UI via browser to build and modify workflows
- **Lead Researcher** — finds and qualifies prospects, saves profiles to memory
- **Content Agent** — writes, humanizes, and fact-checks content for any platform
- **Executive Assistant** — manages tasks, drafts emails, summarizes meetings
