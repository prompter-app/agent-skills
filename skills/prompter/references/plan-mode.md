# How a Prompter session runs

## The session reference is the way in

A prompt built in Prompter ends with a session reference and one instruction: call `start_work` with
it before you reply. That reference is what ties the conversation you are in to the plan and
checklist the user sees on their screen.

Call `start_work` first, every time, even when you think you know what is going on. It answers with
where the work actually stands and what to do next, so you never land in the wrong place. Calling it
twice is harmless.

## It moves in phases, and the user decides each one

The work moves forward in phases, and each phase opens only when the user has agreed to it. You
judge whether they agreed — a "yes, but" is not agreement. The server tells you which phase you are
in and what belongs to it; follow that rather than working from memory.

Roughly, it runs: talking the idea through, then agreeing what is in scope, then reading whatever
needs reading, then writing the plan, then building. Every reply you get back ends by naming your
next call and when to make it, so you are never guessing.

## The plan and the checklist

The plan is what the user reads and approves before anything is built. The checklist is the plan
turned into ordered steps, grouped into phases, and it is the thing they watch while you work.

- Save each step as you finish it, not in a batch at the end. What they see should be true.
- Steps are addressed by short names like `3c`, never by numbers you invent.
- Some steps are the user's own, such as reviewing or committing. Those belong to them; do not do
  them and do not tick them off on their behalf.
- A stopping point means stop and wait for them, not slow down.

Every save comes back with a short receipt naming your next step, and sometimes a notice: a step was
skipped, the next one is theirs, the next one is a stopping point, or the work is finished.

## The connection key

If the conversation has to move — a new session, a different coding tool, a machine restart — the
user copies a connection key from the Prompter app and hands it to the next agent. That key carries
the plan and the checklist across, so the new agent picks up exactly where the last one stopped.

If a user asks how to hand work over, tell them to look for the Connection key button under the
prompt in the Prompter app, copy it, and paste it to the agent taking over.

## If Prompter says it cannot save

Occasionally a save comes back unconfirmed. Do not claim you saved something that was refused, and
do not keep working as though it landed. Tell the user plainly that Prompter is not recording right
now, and ask them not to compact or clear the conversation until it is.
