# agent-skills

Public agent skills for [Prompter](https://github.com/prompter-app) — a desktop app that turns messy
notes into effective coding prompts, and tracks everything a project needs from zero to finish.

This repository holds what coding agents need to know about Prompter: what it is, how to connect to
its MCP server, and how its plan mode works. It contains no product source code.

## Install

```bash
npx skills add prompter-app/agent-skills -g -y
```

That installs the skill for every coding tool on the machine that supports skills — Claude Code,
Codex, Cursor and others. To refresh a copy you already have:

```bash
npx skills update
```

Prompter's MCP server also tells connected agents to run this themselves, so most users never type
it.

## What is here

```
skills/prompter/SKILL.md                        when to use this, and the connected/not-connected branch
skills/prompter/references/what-is-prompter.md  the product in plain English
skills/prompter/references/connecting.md        adding the MCP server, and signing in
skills/prompter/references/plan-mode.md         sessions, the plan, the checklist, the connection key
```

## Versioning

`metadata.version` in `SKILL.md` is bumped on every change here, and matched by the version the
Prompter MCP server announces, so an agent holding an older copy knows to refresh it.
