# Riley believes the model runs the tools itself (M4), not yet corrected

In quiz 0001 (s1), Riley said the model opens the booking system and "runs the 3 tools itself" in one call (q2, q4). Riley does know what defines an agent and that a step limit is the safeguard against a stuck loop (q1, q3).

**Evidence:** q2 chose "opens the booking system on its own"; q4 answered 1 model call instead of 4; q6 also added that the model remembers tool choices across sessions (M3).

**Implications:** Teach the split between the model (writes a request) and the program (runs the tool, calls the model again) with a two-column diagram before moving on. Address M3 when teaching memory: the model keeps nothing between calls unless the program supplies it.
