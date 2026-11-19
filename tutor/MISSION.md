# Mission: How coding agents work, for building the P3 tutor

## Why
Build Project 3 for CSCI 598E: a tutor that runs inside Claude Code (skills, subagents, hooks) and is measured by the course bench. Understanding how agents run, decide, and stop is what lets the learner make the tutor behave well and read why a bench run went the way it did.

## Success looks like
- Read a bench run or session and say why it ended: the model, a limit, or a check.
- Decide what belongs in a skill, a subagent, or a hook, and explain why.
- Write a hook (such as the final step's guard) and know when it fires.

## Constraints
- Course deadlines for P3.
- Bench runs use the learner's own Claude subscription, so cheap experiments come first.
- Short, dense lessons with code and diagrams (see `PREFERENCES.md`).

## Out of scope
- Agent frameworks and APIs beyond what Claude Code and the P3 bench use.
