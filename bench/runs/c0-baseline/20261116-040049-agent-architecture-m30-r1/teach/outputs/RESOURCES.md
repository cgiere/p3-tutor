# Agent architecture Resources

## Knowledge

- [Article: "Effective context engineering for AI agents" (Anthropic Engineering)](https://anthropic.com/engineering/effective-context-engineering-for-ai-agents)
  Context rot, the attention budget, up-front versus just-in-time retrieval, compaction, note-taking and sub-agents. Use for: what to keep in context, what to save, how an agent finds things in a large body of text.
- [Docs: "Context windows" (Claude Platform docs)](https://platform.claude.com/docs/en/build-with-claude/context-windows)
  What counts toward the window, how it grows each turn, context rot, compaction and context editing. Use for: exact facts about what the window holds and how to manage it.
- [Docs: Memory tool (Claude Platform docs)](https://platform.claude.com/docs/en/agents-and-tools/tool-use/memory-tool)
  The file-based memory tool for saving information between sessions. Linked from the context windows page; not yet read in full. Use for: a concrete design for saving a student's training status.

## Wisdom (Communities)

No community has been vetted yet. Gap: a moderated forum where people discuss agent design (to be found in a later session).

## Gaps

- A community for testing agent-design judgment.
- A source with measured cost figures for retrieval-based assistants.
