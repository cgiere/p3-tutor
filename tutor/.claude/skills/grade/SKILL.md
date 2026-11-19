---
name: grade
description: Grade a learner's submission to a quiz in this workspace - a verdict, a misconception id and short feedback for every answer, and a summary with the next step - written as FORMATS.md describes; use it whenever the learner hands in answers or asks for a submission to be graded.
argument-hint: "Which submission should I grade?"
---

# Grade

You grade the learner's answers to a quiz: a verdict on each answer, the misconception it shows if any, and feedback that helps them learn.
The grades are also your best evidence of what the learner knows, so they feed the learning records.

## The request

$ARGUMENTS

If the request above is empty, the request is the learner's latest message.
If the learner gave their answers in the chat, write them exactly as given to the next `submissions/sN.json`, as `FORMATS.md` shows, and grade that submission.
Do what the request asks now, and put any question for the learner at the end of your final message.

## Read first

The current directory is the workspace root.
Read `FORMATS.md` (the exact shape of the grades file), `PREFERENCES.md`, `MISSION.md`, `NOTES.md` and every file in `learning-records/`.
Then read the quiz, its key, the submission, and the lesson on the quiz's objective if there is one.
Read `.claude/skills/teach/references/GRADING.md`, the guide to verdicts, misconceptions and feedback, and follow it, except where this skill says otherwise below.
Never write anything under `.claude/`, and never edit `PREFERENCES.md`.

## Feedback of about 200 characters

The learner wants feedback that is concise but packed with meaning, so each item's `feedback` aims at about 200 characters, spaces included: 180 to 200 is the target, and a little over, up to about 220, is fine when the extra words carry meaning.
This replaces the guide's "two to four sentences".
Use the room for substance: after the verdict and the main point, add the detail that makes it stick, such as the reason behind the right answer, what the learner's choice would actually lead to, or how the idea connects to the next one.

- Make the verdict clear in the first few words, with no praise, but as the start of a real sentence ("That's right, because ...", "Not quite: you have ... but ...", "No, the model ..."), not a one-word label standing alone.
- Then the one thing that matters: for a correct answer, the insight that makes it stick; for a partial one, exactly what was off; for a wrong one, the right idea and why it holds, naming the wrong belief if a misconception is behind it.
- Write it as one or two complete, connected sentences that read aloud naturally, joining the ideas with words like "because", "so" and "but".
  No labels and fragments ("Descriptions part: right."), no strings of three-word sentences, no "+" or "=" in place of words, and no "yes" tacked on mid-sentence.
- Stay concise by choosing one point, not by dropping verbs and connectives: no restating the question, no repeating the learner's answer at length, no "great job".
- State every fact as a precise, absolute claim: name who does what and when ("the program runs each tool and sends its result back before the next call"), not a loose trailing phrase that leaves it vague ("while the program runs the tools in between").
  No hedges or soft words such as "kind of", "in between", "around", "sort of", "half of it" or "on its own"; if a claim needs a condition, state the condition exactly.
- Count the characters of each feedback before you write the file: extend any under 180 with a point of substance, never filler, and shorten any over about 220.

## Steps

1. Grade every item: a verdict (`correct`, `partial` or `wrong`) and a misconception id or `null`, as the guide says.
2. Write each item's feedback at about 200 characters, as above, and the `summary`: what the learner has down, the one thing to work on next, and a concrete next step.
3. Write `grades/NNNN-sN.json` exactly as `FORMATS.md` shows.
4. Write a learning record when the grades are evidence of real understanding or of a misconception to work on, in the format in `.claude/skills/teach/references/LEARNING-RECORD-FORMAT.md`, and update `NOTES.md`.
5. Finish in the chat with the summary and the one next step.
