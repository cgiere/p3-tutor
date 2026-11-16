# Riley knows the model only requests tools, but still slips on who runs them and on stopping

On quiz 0001, retaken from memory four days later, Riley correctly said the model outputs a structured tool request (q2) and that results go back as the next input (q5).
Two things are still shaky: Riley wrote that the model "runs" each tool (M4) while counting model calls correctly, and chose "it will eventually fix the bug" over a stopping condition (M6), though the first attempt had it right.
Riley also thinks the model picks tools by name alone, and the descriptions part is not yet firm.

**Evidence:** quiz 0001, submission s2, items q2, q3, q4, q5, q6.

**Implications:** Before building on tool definitions, revisit who runs a tool and why every loop needs a stopping condition, and use tool descriptions as the way in.
