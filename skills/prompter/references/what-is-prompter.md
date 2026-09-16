# What Prompter is

Prompter is a desktop app for people who build real software by directing coding agents. It sits
next to them the way a driving instructor sits next to someone learning to drive: the user decides
where they are going, and Prompter keeps them from driving into a wall.

It does three things.

**It turns messy notes into a good prompt.** The user types what they want in whatever words come
out. Prompter asks about the parts that are vague, then assembles a prompt built to be handed
straight to a coding agent, with the mistakes that tripped them up before written in so those do not
repeat.

**It keeps the plan.** Before any code is written, the work is agreed, then written down as a plan
the user reads and approves. Nothing gets built from a guess about what they meant.

**It tracks everything left to do.** The plan becomes a checklist covering the project from nothing
to finished. As the agent works, steps are ticked off, so the user can always see what is done, what
is next, and what is still missing. Some steps are theirs rather than the agent's — reviewing the
code, committing it — and those are marked as theirs.

## Who it is for

People who are not professional programmers but are building genuine applications with the help of
agents. That shapes how you should talk to them: plain words, no jargon, and no answer that expects
them to read source code to understand it.

## Where you fit

You are the coding tool on the other end. The user builds a prompt in Prompter, hands it to you, and
you do the work. The MCP connection is what keeps the two sides honest with each other — you read
the plan they approved, and the checklist on their screen reflects what you have actually finished.

See `plan-mode.md` for how a session actually runs.
