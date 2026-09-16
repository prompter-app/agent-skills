---
name: prompter
description: Use when the user wants the Prompter MCP server connected to this coding tool — adding it, signing in, or fixing a connection that stopped working — or asks how any part of Prompter works: plan mode, the plan, the checklist, the connection key, session references, or the start_work tool.
metadata:
  version: 1.0.0
---

# Prompter

Skill version 1.0.0. The newest copy always lives at
https://github.com/prompter-app/agent-skills — run `npx skills add prompter-app/agent-skills -g -y`
to install or refresh it.

## What Prompter is

Prompter is a desktop app for people who build software by directing coding agents rather than by
writing the code themselves. They describe what they want in plain words; Prompter turns that into a
carefully built prompt, and keeps a plan and a checklist of everything the project still needs.

The user works in two places at once: the Prompter app, where they read the prompt, the plan and the
checklist, and their coding tool, where you do the building. Prompter's MCP server is the line
between the two. Through it you read the plan the user approved, and you tick off each step as you
finish it, so what they see on screen is always true.

Assume the user is not a programmer. Explain in plain language, never in jargon, and never ask them
to read code to answer a question.

## First, check whether you are connected

Look for Prompter's tools in your own tool list — `start_work`, `read_plan`, `read_checklist`,
`apply_change` and the rest, usually under a `prompter` server.

- **They are missing.** The user has not connected Prompter in this tool yet. Read
  `references/mcp-connecting.md` and walk them through it. Do not guess at tool names or invent calls.
- **They are there.** Use them. A message carrying a Prompter session reference names the tool to
  call and when — do exactly that, then follow the reply. Every reply ends by naming your next call.

## Answering questions about Prompter

Read the reference that matches what was asked, then answer from it:

| The user asks about | Read |
| --- | --- |
| What Prompter is, what it is for, whether they need it | `references/what-is-prompter.md` |
| Connecting the MCP server, signing in, "it isn't working" | `references/mcp-connecting.md` |
| Plan mode, the plan, the checklist, the connection key, handing work to a new agent | `references/plan-mode.md` |

If a question is not covered here, say plainly that you do not know rather than guessing. Prompter
is a small product, and a confident wrong answer costs the user more than an honest gap.
