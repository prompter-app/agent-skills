# How a Prompter session runs

## The session reference is the way in

A prompt built in Prompter ends with a session reference and one instruction: call `start_work` with
it before you reply. That reference is what ties the conversation you are in to the plan and
checklist the user sees on their screen.

Call `start_work` first, every time, even when you think you know what is going on. It answers with
where the work actually stands and what to do next, so you never land in the wrong place. Calling it
twice is harmless. Call it again whenever your context has been compacted.

## It moves in phases, and the user decides each one

The work moves forward in phases, and a phase opens only when the user has said yes. Never assume
they are ready. When nothing is left open, ask, and move on only after they answer yes, in whatever
words they use. The server tells you which phase you are in and what belongs to it; follow that
rather than working from memory.

If the user wants to move on while points are still open, do not argue and do not guess in silence.
List the assumptions you would make to close each open point, and ask whether they are happy with
those. Their yes is what lets you move on.

Every reply you get back names your next call and when to make it, so you are never guessing.

## The Brainstorm setting shapes the first phases

How much talking happens before the plan is written is the user's choice. They set it with
**Brainstorm the plan** on the Coding tab of the session panel in the Prompter app.

- **Deep.** Talk first, without opening the project's files. If one file would change the plan, name
  it, say what you expect it to change, and wait for the user's approval. Once they agree to move
  on, read the code the work touches, come back with what it changes, and talk again. Then ask
  whether to write the plan.
- **Normal.** Read the code the request touches, then have one discussion with that code in mind.
  When nothing is left open, list what was agreed and ask whether to write the plan.
- **None.** The user wants to answer a few questions, make the decisions that are theirs, and get
  straight to the plan. Ask only what their settings allow, read the code, and make the remaining
  choices yourself without listing them in chat. Then say you are ready, offer to show the decisions
  you made for them, and wait for the go-ahead. The plan lists those decisions under an Assumptions
  heading.

## Writing the plan and the checklist

Both documents live in Prompter, never as files in the project folder. You write a document by
saving it through `apply_change`: the plan first, then the checklist. When the checklist is saved,
Prompter has you tell the user both are in their session and ask whether to implement.

If a session already holds both documents and building has not started, the user's message decides
what happens next: implement the plan, or change it first. Read a document only when you need it.

## The tools

| Tool | When you call it |
| --- | --- |
| `start_work` | First, before replying to a message that carries a session reference, and after a compaction |
| `scope_agreed` | Deep brainstorm only: the user agreed to move on to reading the code |
| `write_plan` | The user said yes to writing the plan and the checklist |
| `implement_plan` | The user said yes to building |
| `read_plan`, `read_checklist` | You need to read one document again |
| `plan_rules`, `checklist_rules` | Before you change a document that already exists |
| `next_step` | A reply tells you to call it before starting your next step |
| `apply_change` | Every save |

## The plan and the checklist

The plan is what the user reads and approves before anything is built. The checklist is the plan
turned into ordered steps, grouped into phases, and it is the thing they watch while you work.

- Save each step as you finish it, not in a batch at the end. What they see should be true.
- Prompter numbers every phase and letters every step. Use those names, like `3c`, when you and the
  user talk about a step, and never write numbers or letters of your own.
- Some steps are the user's own, such as reviewing. Those belong to them; do not do them and do
  not tick them off on their behalf.
- A stopping point means stop and wait for them, not slow down.
- Finished steps are protected. If finished work needs more, add a new step.
- If the plan or the remaining steps need a change while you build, call `plan_rules` or
  `checklist_rules` first, then save the change.

Every save comes back with a short receipt naming your next step, and sometimes a notice: a step was
skipped, the next one is theirs, the next one is a stopping point, or the work is finished.

## Commits and branches

Prompter places the commit steps when the checklist is created, where the user's Commits setting
puts them, and each one names the branch its commit goes on. Commit only at a commit step. When a
phase opens, the reply names the branch for that phase; switch to it before changing any file.

- The user asks to work on another branch: switch, then record it with apply_change's `set_branch`
  operation.
- The user wants a commit step added to a phase, or one removed: `insert` a step with the tag
  `commit` and the text "Commit code changes", or `remove` it. Never move or edit one.
- The user wants no commits at all: remove the commit steps still to do. For future sessions, tell
  them the session panel's Coding tab in the Prompter app has a Commits slider; set it to Never and
  pin it.
- The reply says Prompter found no git branch in the folder: help the user install git or set up
  the repository, then ask which branch to use.

## The connection key

If the conversation has to move — a new session, a different coding tool, a machine restart — the
user copies a connection key from the Prompter app and hands it to the next agent. That key carries
the plan and the checklist across, so the new agent picks up exactly where the last one stopped.

If a user asks how to hand work over, tell them to look for the Connection key button under the
prompt in the Prompter app, copy it, and paste it to the agent taking over.

## If Prompter says it cannot save

Occasionally a save comes back unconfirmed. Send it once more exactly as it was; a repeat is
harmless. If it still cannot be confirmed, never report that work as saved. Keep working from the
checklist you hold, tell the user plainly that Prompter is not recording right now, and ask them not
to compact or clear the conversation until it is.
