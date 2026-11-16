# Agent architecture Resources

## Knowledge

- [Article: "Effective context engineering for AI agents" (Anthropic Engineering)](https://www.anthropic.com/engineering/effective-context-engineering-for-ai-agents)
  Context, attention budget, compaction, note-taking, just-in-time retrieval, sub-agents. Use for: anything about what goes in context and how to keep it small.
- [Docs: Context windows (Claude Platform)](https://platform.claude.com/docs/en/build-with-claude/context-windows)
  What counts toward the window, context rot, compaction and clearing. Use for: exact definitions and token accounting.
- [Docs: Memory tool (Claude Platform)](https://platform.claude.com/docs/en/agents-and-tools/tool-use/memory-tool)
  Client-side file memory, the six commands, security duties. Use for: designing memory between sessions.
- [Docs: Compaction (Claude Platform)](https://platform.claude.com/docs/en/build-with-claude/compaction)
  Server-side summarizing of long conversations. Use for: long-running sessions.
- [Blog: "LLM Powered Autonomous Agents" by Lilian Weng](https://lilianweng.github.io/posts/2023-06-23-agent)
  Short-term versus long-term memory, external vector stores. Use for: vocabulary and the general picture of agent memory.

## Wisdom (Communities)

- Local: your team's design review, advisor and makerspace staff
  Use for: what the assistant should remember about students and what staff expect it to know.

## Gaps

- A high-trust source on retrieval quality (chunking, ranking, evaluation) for manuals; the next lesson on retrieval should find one.
- A reviewed online community for building agents; none verified yet.
