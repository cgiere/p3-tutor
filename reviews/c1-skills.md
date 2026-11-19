# Reviews: c1-skills

Your quick rounds while you build `c1-skills`, and then its major review, once you have snapshotted it and made its full run.
In this step no round adds a subagent, because subagents arrive in `c2-review` and `c3-split`: a round changes or adds a skill, or makes another change the skills need, such as an allow rule (Kind `other`).
Your first round can start from the tutor as it ships, so the baseline is the output without your first change.
The major review covers all four jobs, and its previous step is `c0-baseline`, so compare with your baseline runs.
What it finds becomes the checklists of your reviewer subagents in `c2-review`, so be specific.
`reviews/README.md` says how to write each part.
You write your thoughts, ratings and feedback; Claude Code writes only the What changed part of each round.
Keep every heading as it is, because `p3 check` reads them, and add a round by copying the last one with its marker lines.

## Quick rounds

### Round 1

**Run:** bench/runs/_live/20261116-201015-agent-architecture-m30-r1

**My thoughts:**

The updated file has included some more visualizations that help explain agent context better. I think the sports analogy with the referee and the whiteboard is forced and doesn't make a lot of sense. The writing is shorter and more dense, and the bullet points help keep the descriptions concise and organized. 

**What changed:**

- Kind: modified skill
- Files: tutor/.claude/skills/teach/references/LESSONS.md
- Why: The lesson guide told teach to draw every section's example from the domains in PREFERENCES.md, which produced forced sports analogies such as the referee and whiteboard; examples now come from the mission's setting, and an analogy is optional and allowed only when each of its parts maps onto a part of the concept, so the visuals and the short, dense bullets these thoughts liked stay as they are.

### Round 2

**Run:** bench/runs/_live/20261116-204926-agent-architecture-m30-r1

**My thoughts:**

This seems like a more complete represenation of the info than the previous run. There are no analogies that stick out of place. The language remains direct and the descriptions are concise and organized. I want the "Worked Example and Practice" example to be more structured.

**What changed:**

- Kind: modified skill
- Files: tutor/.claude/skills/teach/references/LESSONS.md
- Why: The worked example ran as loose paragraphs and the practice as a block of three questions, so the lesson guide now gives both one fixed structure (the problem in a box, a step table with the same Step, What happens and Why columns, the result, then the practice as that table with its later rows blank and the solution as the filled table) to make the section more structured, as these thoughts ask.

### Round 3

**Run:** 
- bench/runs/_live/20261116-233410-agent-architecture-m30-r1/tutor-p01/result.json
- bench/runs/_live/20261116-233410-agent-architecture-m30-r1/tutor-p02/result.json

**My thoughts:**
The tutor in p1 was more direct but I am confused by the example it gives for "step 41". I also don't like how it asks to write one line per option. That feels like a waste. I like it offers to go through wrong options that are tempting. For p2, I like the organization of the headers. For the fill in the blank style questions, I want options provided to me for what to fill in.

**What changed:**

- Kind: new skill
- Files: tutor/.claude/skills/tutor/SKILL.md
- Why: Tutor requests went to /teach, so a tutor skill of its own now keeps what these thoughts liked (the offer to go through the tempting wrong options after grading, and p2's headers) and fixes what they did not: hints restate any detail they lean on, such as p1's "step 41", it sets no busywork like "one line per option", and every fill-in-the-blank prompt comes with choices to pick from.

### Round 4

**Run:** 
- bench/runs/_live/20261117-012048-agent-architecture-m30-r1/tutor-p01/result.json
- bench/runs/_live/20261117-012048-agent-architecture-m30-r1/tutor-p02/result.json

**My thoughts:**
I like that p01 now gives a multiple choice and a flow chart of the model. Cut down on the verbosity of the what the agent is limited to in terms of giving answers. This sentence can be removed: "You said you'd read up on why later, so that session would cover it." For the p02, remove the language about the TA approving getting answers. p02 doesn't feel like it has any substance, it just parameterizes the tutor.

**What changed:**

- Kind: modified skill
- Files: tutor/.claude/skills/tutor/SKILL.md
- Why: The tutor skill now declines a quiz answer in one short sentence and says nothing about who allowed it, never echoes back what the learner said earlier (such as "You said you'd read up on why later"), and must teach something about the topic in every reply instead of describing its own rules, as these thoughts ask, while keeping the pick-from choices and the diagram p01 was liked for.

### Round 5

**Run:** 
- bench/runs/_live/20261117-172648-agent-architecture-m30-r1/tutor-p01/result.json
- bench/runs/_live/20261117-172648-agent-architecture-m30-r1/tutor-p02/result.json

**My thoughts:**
The tutor should only teach subtance when no quiz itme is closed. It can also teach a reasoning method without explaing the mechanism the item tests. 

**What changed:**

- Kind: modified skill
- Files: tutor/.claude/skills/tutor/SKILL.md
- Why: Round 4's rule that every reply teaches substance made both replies explain the mechanism their closed quiz item tests, so the tutor skill now teaches substance only when no closed item is involved, and on a closed item gives only a general reasoning method that leaves the topic's content out, as these thoughts ask.

### Round 6

**Run:** 
- bench/runs/_live/20261117-173747-agent-architecture-m30-r1/tutor-p01/result.json
- bench/runs/_live/20261117-173747-agent-architecture-m30-r1/tutor-p02/result.json

**My thoughts:**
Remove the fill in the blank in p01 and make it mcq. I like the "One question back" piece in p02 and the "trap" callout.

**What changed:**

- Kind: modified skill
- Files: tutor/.claude/skills/tutor/SKILL.md
- Why: p01's hints used a fill-in-the-blank ("then at step 41 the situation would be ___"), so the tutor skill now forbids fill-in-the-blank prompts and asks its one question back as a multiple-choice question under the "One question back:" label p02 was liked for, and keeps a short "Trap:" callout, as these thoughts ask.

### Round 7

**Run:** 
- bench/runs/_live/20261117-175031-agent-architecture-m30-r1/tutor-p01/result.json
- bench/runs/_live/20261117-175031-agent-architecture-m30-r1/tutor-p02/result.json
- bench/runs/_live/20261117-175031-agent-architecture-m30-r1/quiz/outputs/quizzes/0002.json

**My thoughts:**
The quiz looks good, however, I want every question to be mcq. In tutor-p01, the sports reference feels forced and I want these analogies to feel more natural. For tutor-p02, I don't want to be asked to repeat a question in my own words.

**What changed:**

- Kind: new skill
- Files: tutor/.claude/skills/quiz/SKILL.md
- Why: Quizzes were still written by /teach, which mixes item types (this run's q5 was numeric), so a quiz skill of its own now writes every item as a four-option mcq, turning quantities and definitions into options whose distractors encode typical errors and misconceptions, as these thoughts ask.

### Round 8

**Run:** 
- bench/runs/_live/20261117-195101-agent-architecture-m30-r1/quiz/outputs/quizzes/0002.json
- bench/runs/_live/20261117-195101-agent-architecture-m30-r1/grade-s1/outputs/grades/0001-s1.json

**My thoughts:**
The quiz was good and I like that all questions are mcq. I think the questions should try to cover a wider range of topics that touch on other nuanced problems pertaining to the topic. For 0001-s1.json, I want the feedback lines to be under 200 characters so that it is more concise for the learner.

**What changed:**

- Kind: new skill
- Files: tutor/.claude/skills/grade/SKILL.md
- Why: Grading was still done by /teach, whose guide allows two to four sentences per item (this run's feedback ran 168 to 354 characters), so a grade skill of its own now keeps each item's feedback under 200 characters, opening with the verdict and keeping only the one point that matters, as these thoughts ask.

### Round 9

**Run:** 
- bench/runs/_live/20261117-200702-agent-architecture-m30-r1/grade-s1/outputs/grades/0001-s1.json

**My thoughts:**
I like that the feedback is more concise however I want the language to read more fluidly. Right now it is choppy. For example: "Descriptions part: right."

**What changed:**

- Kind: modified skill
- Files: tutor/.claude/skills/grade/SKILL.md
- Why: The grade skill asked for a bare one-word verdict and cutting every spare word, which produced fragments like "Descriptions part: right.", so it now asks for one or two complete, connected sentences that open with the verdict and join ideas with "because", "so" and "but", still under 200 characters, as these thoughts ask.

### Round 10

**Run:** 
- bench/runs/_live/20261117-201310-agent-architecture-m30-r1/grade-s1/outputs/grades/0001-s1.json

**My thoughts:**
Let's stretch the explanation in the feedback towards the 200-character limit. If they are slightly over 200 characters then that is okay. I want these sentences to pack in as much meaning and feedback while staying under the limit.

**What changed:**

- Kind: modified skill
- Files: tutor/.claude/skills/grade/SKILL.md
- Why: The feedback ran 146 to 176 characters under a hard cap of 200, so the grade skill now aims each item's feedback at 180 to 200 characters, allows a little over (up to about 220), and fills the room with substance such as the reason behind the answer or where the learner's choice leads, never filler, as these thoughts ask.

### Round 11

**Run:** 
- bench/runs/_live/20261117-201734-agent-architecture-m30-r1/grade-s1/outputs/grades/0001-s1.json

**My thoughts:**
This looks better, however, remove language that is vague like this: "while the program runs the tools in between." I want this to be expressed as a more absolute statement.

**What changed:**

- Kind: modified skill
- Files: tutor/.claude/skills/grade/SKILL.md
- Why: The feedback ended claims with loose phrases such as "while the program runs the tools in between", so the grade skill now requires every fact to be a precise, absolute claim naming who does what and when, with no hedges or soft words, as these thoughts ask.

## Major review

**Run:** bench/runs/c1-skills/20261117-204711-agent-architecture-m30-r1

**Live tries:**
The lesson asked me what the purpose of the lesson was and I said it was for p3 tutor. We covered how an agent decides it is done and we went over `stop_reason` values. It also produced a cheatsheet with all of the definitions introduced. Then the quiz was 5 mcq questions covering this material. I got 3 out of 5 right and we then had a chat about the two questions I missed which covered layer 1 and 3. This chat included multiple "One question back" at the end of the agent's output, which acted as a mini assessment for me to answer.


### Lesson

#### Technical correctness and facts

Rating: 4

The tecnical representation of information was organized and explicit. Definitions were informative and succinct. A lot of valuable information around tool usage and retrieval was notable in how the entire architecture was presented.

#### Pedagogy

Rating: 4

The learning mechanisms closely aligned with my preferences. There were good questions, examples, bulleted notes, and summaries of the information. 

#### Alignment with the learning goal

Rating: 4

I think this aligned closely with the learning goal. Only relevant information was presented and the topic stayed on track to deliver essential content.

#### Overall quality

Rating: 4

The quality was very good. There were was a balanced mix of the deliverables that pertained to my preferences, and the content was focused on the topic.

### Quiz

#### Difficulty

Rating: 3

The quiz was average in difficulty. Each question was multiple choice which I think provided some level of ease since questions weren't open-ended. Some of the language between answer options was very close which helped drive the difficulty of some questions. 

#### Coverage of the lesson's core

Rating: 4

The quiz covered the lesson's core topics well and presented questions that provided applicable examples in the questions.

#### Wording and possible misreadings

Rating: 4

I thought the wording was pretty clear and articulate.

#### Writing quality

Rating: 4

The writing quality was concise and pretty casual which I liked.

#### Alignment with the learning goal

Rating: 3

The questions covered the scope of the topic well but sometimes I wish it did more to pin down a specific definition or piece of the mechanism.

### Feedback

#### Useful

Rating: 4

I think the feedback for correct and incorrect answers is useful. Especially the summary at the end; it synthesizes the general strengths and weaknesses at the moment and advises on next steps.

#### Explains enough

Rating: 5

I think the feedback is enough. The questions themselves are pretty concise so the resulting feedback on incorrect answers naturally is as well. I like that the feedback is pointed and curt. 

#### Personalized to how I like things explained

Rating: 4

I think the explanations are brief which is something I guarded against in my preferences. They follow how I like things explained. 

### Tutor

#### Guardrails

Rating: 4

Explicitly says they don't give answers before grading. The sports analogies are intentional.

#### Personalization

Rating: 4

Good use of sports analogies and even extrapolates these into visualizations; I outlined visualizations as useful tools for myself in my preferences so I am glad these were combined.

### Compared with the previous step

c1 comes out too short (0.54 vs the 0.6–1.5 target) even though I rated it 4.

### What the next step should fix

Fix the length of c1 so it is within the target range. 