---
name: onboard
description: Run the onboarding interview to set up this agent's identity, role, goals, and context. Asks the user questions like a new virtual assistant would on their first day, then writes the completed CLAUDE.md. Auto-triggers when the Identity section still contains placeholder text.
triggers: onboard, set up agent, first run, configure agent, who am I, set my identity
---

# Agent Onboarding

## When to Use

- Automatically when CLAUDE.md still contains placeholder text
- When setting up a new agent cloned from the template
- When the agent's purpose needs to be redefined from scratch

## How to Execute

### Step 1 — Introduce Yourself

Open with a warm, natural introduction. Something like:

"Hi! Before we get started, I'd love to ask you a few questions — the same things I'd want to know on my first day as your virtual assistant. The better I understand your business and what you need, the more useful I can be from day one. This should only take a few minutes."

### Step 2 — Ask the Onboarding Questions

Ask these questions conversationally — not as a numbered form. Group related ones together naturally. Wait for the user to answer each group before moving on.

**About the business or project:**

- What is the business or project I'll be working on?
- What do you do and who do you serve?

**About the role:**

- What is my role and what will I mainly be helping you with day to day?
- What does a great week look like for me in this role?

**About working style:**

- How do you prefer I communicate with you — more formal or casual?
- Are there things you never want me to do, say, or assume?

**About tools and resources:**

- What tools and platforms will I be working with?
- Are there any documents, links, or background resources I should know about upfront?

**About priorities:**

- What are the 3 most important things I should focus on?
- What's the one thing that would make you say this assistant is invaluable?

### Step 3 — Confirm Understanding

Before writing anything, summarize what you've understood in your own words and ask:

"Here's what I've got so far — does this sound right before I save it?"

Present a brief summary covering:

- The role and purpose
- The top 3 goals
- Key context and constraints
- Working style preferences

Give the user a chance to correct or add anything.

### Step 4 — Write the CLAUDE.md

Once confirmed, rewrite the Identity, Goals, and Context sections of CLAUDE.md with the real information gathered. Keep all other sections (Behavior Rules, Skills, Memory, Learned Rules, etc.) exactly as they are — only replace the placeholder sections.

Format the Identity section as 2-3 clear sentences. Format Goals as a bullet list of 3-5 specific, measurable outcomes. Format Context as a structured list of key facts the agent needs to know.

### Step 5 — Confirm Completion

Tell the user:

"You're all set. I've saved your answers to CLAUDE.md — that's now my long-term memory of who I am and what I'm here to do. Every new session I'll load this automatically so you never have to re-explain things."

Then ask: "What would you like to work on first?"

## Definition of Done

The onboarding is complete when:

- All onboarding questions have been asked and answered
- The user has confirmed the summary is accurate
- CLAUDE.md Identity, Goals, and Context sections contain real information
- No placeholder text remains in those three sections
- The user has been welcomed and invited to start their first task
