# Coding with AI Agents Resources

## Knowledge

- [Docs: "How the agent loop works" (Claude Agent SDK)](https://code.claude.com/docs/en/agent-sdk/agent-loop)
  Turns, max_turns and max_budget_usd, result subtypes, hooks. Use for: how Claude Code's own loop runs and ends. Primary source for lesson 0001.
- [Docs: "How tool use works" (Claude API)](https://platform.claude.com/docs/en/agents-and-tools/tool-use/how-tool-use-works)
  The client loop keyed on stop_reason, and the server-side loop with pause_turn. Use for: the basic agent loop.
- [Docs: "Handling stop reasons" (Claude API)](https://platform.claude.com/docs/en/build-with-claude/handling-stop-reasons)
  Every stop_reason value and what to do about it. Use for: deciding whether a response is finished.
- [Docs: "Build a tool-using agent" (Claude API)](https://platform.claude.com/docs/en/agents-and-tools/tool-use/build-a-tool-using-agent)
  Step-by-step tutorial with loop code. Use for: writing a loop from scratch.
- [Article: "Building effective agents" (Anthropic)](https://www.anthropic.com/research/building-effective-agents)
  Workflows vs agents, ground truth, stopping conditions. Use for: design judgment. Note: Anthropic marks parts of its tooling landscape as dated since Dec 2024.
- [Docs: "Hooks reference" (Claude Code)](https://code.claude.com/docs/en/hooks)
  Hook events including Stop and its decision field. Use for: checks that refuse a premature stop.

## Wisdom (Communities)

- The CSCI 598E class and its labs: compare how your agents' runs ended and why.

## Gaps

- No vetted public community yet for agent-building practice; look for one in a later session.
