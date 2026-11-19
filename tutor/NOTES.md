# Notes

## The learner

- Computer Science student in a course on coding with AI agents (CSCI 598E). Comfortable with the terminal, git and AI tools; some Python.
- Likes seeing code and having it explained; big picture first, then a concrete example; visual; short, dense, bullets; direct and casual; no praise (see `PREFERENCES.md`).
- Mission (2026-11-17): learning agents to build the P3 tutor; see `MISSION.md` and learning record 0001. Use P3 examples (skills, subagents, hooks, bench runs).

## Objectives

- O1: explain how an agent loop decides it is done, and read its stop signals (stop_reason, Agent SDK result subtypes, limits, Stop hooks). Lesson 0001, quiz 0001.

## Misconceptions

- M1: the agent stopping (end_turn, or a "done" message) means the task is actually complete. Open: shown in quiz 0002 q5.
- M2: any stop reason other than tool_use means success (ignores max_tokens, pause_turn, max-turns and budget limits).

## Working notes

- 2026-11-17: taught lesson 0001 (10 min) on O1. Quiz 0001 written, not yet taken.
- 2026-11-17: learner wants every quiz item to be multiple choice. Quiz 0002 = quiz 0001 with q3 rewritten as mcq; use 0002, not 0001.
- 2026-11-17: graded quiz 0002 s1, 3 of 5. Limits understood; M1 shown on q5; on q1 thought tool success drives the loop. See learning record 0002.
- 2026-11-17: asked to go over Layer 1 and Layer 3 of lesson 0001, then said they wanted a chat answer, not a new lesson. Prefer short chat explanations for re-teaching; offer a lesson rather than writing one unless asked plainly.
- Possible M3 (from quiz 0002 q1): believes tool success/failure decides whether the loop continues. Explained in chat 2026-11-17; not yet re-tested.
- 2026-11-17: M1 shown again in chat: picked "the reply came back with end_turn" as evidence the tutor's quiz file was written (right answer: the file exists and parses). M1 still open; keep re-testing it.
- 2026-11-17: chose the right Stop hook action (block with a reason) for a missing file. See learning record 0003. M1 improving, not yet confirmed.
- 2026-11-17: correctly said stop_hook_active true means Claude is continuing because a Stop hook already blocked it. Next: a fresh all-mcq quiz on Layer 1 and Layer 3 to re-test M1 and M3.
