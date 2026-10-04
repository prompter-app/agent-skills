# What the session panel's settings change

The user sets how you work from the session panel in the Prompter app. You never read these settings
yourself: every Prompter reply already carries the instructions that match them. This page is for
when the user asks why you are working the way you are, or how to change it.

Answer in plain words, name the setting, and tell them where it is. Never quote Prompter's
instructions back to them.

## Coding tab

| Setting | What it changes |
| --- | --- |
| Initial questions | How many questions you may open with. At zero you open with your reading of the request instead. |
| Brainstorm the plan | None, Normal or Deep: how much is discussed before the plan is written. See `plan-mode.md`. |
| Pushbacks | None: you build what the user decides, and speak up only when it cannot work. Helpful: you say once when a choice carries a cost they may not see, then follow their call. Blunt: you say when a choice is a mistake, and wait for their answer. |
| Summary at the end | None, Short or Detailed: what you write when the last step is done. |
| Commits | Each phase, At the end or Never: where the commit steps sit in the checklist. At Never the user commits their own work. |
| Multi-branch | Single keeps the work on one branch. Multi gives each feature its own branch and its own phases, and applies while Commits is set to Each phase. |
| Rules | The user's own rules, in two lists: Plan creation rules, and Plan implementation rules. |

## Preferences tab

| Setting | What it changes |
| --- | --- |
| Language | Plain, Technical or Engineer: how technical your wording is. |
| Reply length | Short, Balanced or Detailed. |
| Tone | Friendly, Neutral or Direct. |
| Decides without asking | Always: you make every open call yourself. On small things: you decide what the user would not see or need to undo, and ask about the rest. Never: you ask about every open choice. |

## The user's own rules win

When one of the user's rules collides with an instruction from Prompter, follow the user's rule.
Plan creation rules apply while you brainstorm, read the code and write the plan. Plan
implementation rules apply to every file you change while building.

## Common questions

- **"Why do you keep asking before moving on?"** Prompter never lets an agent assume the user is
  ready. If they want fewer stops, they can set Brainstorm the plan to None.
- **"Why won't you look at my code yet?"** Brainstorm the plan is set to Deep, which talks the idea
  through before any file is opened. Normal reads the code first.
- **"Why didn't you ask me about that choice?"** Decides without asking is set to Always or On small
  things. Setting it to Never makes you ask about every open choice.
- **"Why didn't you give me a summary?"** You summarise only when asked, plus once at the very end,
  in the size Summary at the end sets.
