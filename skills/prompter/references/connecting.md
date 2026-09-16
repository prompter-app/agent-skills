# Connecting Prompter to this coding tool

Two things have to happen, in this order. You do the first. Only the user can do the second.

## 1. Add the server to your own configuration

Add an MCP server to whatever configuration this coding tool uses, at **user scope** so it works in
every project rather than just the current folder:

- **Name:** `prompter`
- **Transport:** HTTP (streamable HTTP, not stdio, not SSE)
- **URL:** `https://ai-prompter-viqd.onrender.com/mcp`
- **Credentials:** none. There is no API key, token or header to set. Sign-in happens in a browser.

Use your own tool's normal way of adding an MCP server. If you are unsure of the exact file or
command for the tool you are running in, say so and ask the user to open Prompter's Settings →
Integrations, which lists the exact command for several tools.

Some tools need to be restarted, or the session reloaded, before a newly added server appears.

## 2. Ask the user to sign in

Adding the server does not sign anyone in. A browser has to open and the user has to confirm, so
this step is theirs — tell them what to do and then wait.

- **Claude Code:** type `/mcp`, choose Prompter, then choose Authenticate.
- **Codex:** run `codex mcp login prompter`.
- **Any other tool:** tell them the sign-in step for the tool you are actually running in.

Sign-in opens their browser and asks for the email address they use in the Prompter app. There is no
password and no personal access token. After they approve it, the connection stays signed in.

**Do not try to call any Prompter tool until the user tells you they have signed in.** Calling too
early produces an authorization error that looks like a broken product to them.

## When something is wrong

- **The tools do not appear after adding the server.** Restart the coding tool or reload the
  session, then look again.
- **A call comes back unauthorized.** The user has added the server but not finished signing in.
  Send them back to step 2.
- **The user has a second machine, or a second coding tool.** Both steps run again there. The
  connection belongs to that tool on that machine, not to their account alone.
- **The user asks whether they can skip this.** They can use the app to write prompts without it,
  but the plan and checklist only stay current while an agent is connected.

One connection covers every project the user works on. They never repeat this per project.
