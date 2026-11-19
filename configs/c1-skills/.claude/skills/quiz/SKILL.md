---
name: quiz
description: Write a quiz and its answer key on a learning objective for the learner in this workspace, every item multiple choice, as FORMATS.md describes; use it whenever the learner asks for a quiz or to be tested.
argument-hint: "Which objective should the quiz cover, and how many items?"
---

# Quiz

You write quizzes and their answer keys for the learner in this workspace.
A quiz is retrieval practice that also shows the learner where they stand: each item tests one thing that matters for the objective, at the learner's level, with exactly one defensible answer.

## The request

$ARGUMENTS

If the request above is empty, the request is the learner's latest message.
Do what it asks now, and put any question for the learner at the end of your final message.

## Read first

The current directory is the workspace root.
Read `FORMATS.md` (the exact shape of the quiz and key files), `PREFERENCES.md`, `MISSION.md`, `NOTES.md` and every file in `learning-records/`.
Then read the lessons on the objective in `lessons/`, and the earlier quizzes, keys and grades, for what the learner has been taught and the misconceptions they have shown.
Read `.claude/skills/teach/references/QUIZZES.md`, the guide to writing good items and keys, and follow it, except where this skill says otherwise below.
Never write anything under `.claude/`, and never edit `PREFERENCES.md`.

## Every item is multiple choice

The learner wants every item to be `mcq`, so write no `numeric` or `short` items, even when the objective involves a quantity or a definition.

- A quantity becomes four numeric options with their unit, each distractor the result of a typical error (a wrong formula, a unit slip, a missed step).
- A definition or an idea the learner should produce becomes four statements of it, one right and three that each encode a misconception.
- Four options per item, ids `a` to `d`, the same length and grammar, with the correct option's position varied across the quiz.
- Map each distractor that encodes a misconception to its id in the key's `distractors`, reusing the workspace's ids.

## Steps

1. Pin down the objective, its id, and the number of items asked for (four or five when none is given).
2. Find the objective's core in its lessons or, when there are none, in a high-trust source you search for and read; cover the core first.
3. Take the next number in `quizzes/`, and write the quiz to `quizzes/NNNN.json` and its key to `keys/NNNN.json`, exactly as `FORMATS.md` shows.
4. Check: answer every item yourself from its stem alone, without the key, and rewrite any item where you hesitate or where a second option could be defended; confirm every item is `mcq` and carries the objective's id, and that the quiz file holds no answers.
5. Finish with a short message: the quiz's path, how many items, and that the learner can take it in the chat or hand in answers to be graded. Never put an answer in the message.

## Giving a quiz in the chat

When the learner wants to take a quiz in the chat, show its title and each item's stem and options, never anything from `keys/`, and collect their answers.
Write them exactly as given to the next `submissions/sN.json`, as `FORMATS.md` shows, and tell the learner the submission is ready to grade.
