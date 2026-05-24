---
name: chrome
description: Control a Chrome browser to navigate websites, interact with web apps, fill forms, click elements, scrape content, and automate browser-based tasks. Use when the task requires interacting with a website or web application that has no API.
triggers: open browser, go to website, navigate to, click, fill form, scrape, browse, chrome, control browser
---

# Chrome Browser Control

## Requirements
This skill requires the Chrome DevTools MCP server to be connected. If it is not connected, tell the user to add it before proceeding.

## When to Use
- Interacting with web apps that have no API (n8n, Make.com, HighLevel, etc.)
- Filling out forms on websites
- Scraping content from pages that require JavaScript rendering
- Automating repetitive browser-based tasks
- Researching by navigating and reading live web pages

## How to Execute

### Step 1 — Understand the Task
Before touching the browser, clearly define:
- What website or web app are we going to
- What actions need to be taken
- What the definition of done looks like
- What data needs to be extracted or what state needs to be achieved

### Step 2 — Launch and Navigate
- Launch Chrome via the Chrome DevTools MCP
- Navigate to the target URL
- Take a screenshot to confirm the page loaded correctly
- If the page looks unexpected, pause and report to the user before continuing

### Step 3 — Execute Actions
- Take a screenshot before each major action to confirm current state
- Click, fill, scroll, and interact with elements as needed
- After each significant action take another screenshot to confirm result
- If a CAPTCHA or bot detection appears, stop and inform the user

### Step 4 — Handle Errors
- If an element is not found, take a screenshot and try to identify why
- If the page layout differs from expectation, adapt rather than fail
- If authentication is required, ask the user for credentials — never guess
- Report any blockers clearly rather than silently failing

### Step 5 — Report Results
- Summarize what was accomplished
- Note anything that required deviation from the plan
- Save any extracted data to memory/research/ if relevant
- Flag anything that needs human follow-up

## Definition of Done
The task is complete when:
- The intended action has been successfully executed on the target website
- A final screenshot confirms the expected end state
- Any extracted data has been saved if required
- The user has been informed of the outcome
