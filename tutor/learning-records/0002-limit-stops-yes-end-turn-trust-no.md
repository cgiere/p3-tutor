# Reads limit stops correctly; still trusts end_turn as proof of done (M1)

The learner correctly read max_tokens as a truncated answer, pause_turn as unfinished server-tool work, and the max_turns count (tool turns plus one for the final answer).
They have not yet separated "the agent stopped" from "the task is done": they treated end_turn as confirming success (M1) and thought a tool error, not stop_reason tool_use, decides whether the loop continues.

**Evidence:** quiz 0002, submission s1: q2, q3, q4 correct; q1 wrong (picked "the last tool call returned no error"); q5 wrong (picked "nothing, since end_turn confirms the task succeeded", M1).

**Implications:** Do not re-teach limits except as retrieval. Next work: what drives the loop (stop_reason tool_use, tool errors go back as results) and verifying "done" with ground truth and Stop hooks, using P3 examples.
