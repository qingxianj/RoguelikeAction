# AI collaboration log

A record of how AI tools were used on this project: what they produced, what they got wrong,
and how the result was checked. Newest entries on top.

Rules of thumb:

- One entry per non-trivial task (a feature, a tool, a tricky bug), not per prompt.
- "What was wrong" is the most useful field. If nothing was wrong, say how you know.
- Core systems (player state machine, hit detection, upgrade system) are designed and
  first-drafted by hand; log the AI's review comments for those instead.

## Template

Copy this block for each new entry.

```markdown
### YYYY-MM-DD: <task in a few words>

- **AI:** <Claude Code / Codex / other, and model if known>
- **Task:** <what I asked for, and why>
- **Produced:** <files, functions, or advice it gave>
- **What was wrong:** <bugs, wrong assumptions, outdated APIs, over-engineering; or "nothing found">
- **Verified / fixed by:** <how I tested it, what I changed by hand>
```

## Entries

### 2026-11-26: Agent rules and collaboration log

- **AI:** Claude Code (Claude Opus)
- **Task:** Set up shared rules for AI agents (`AGENTS.md`, `CLAUDE.md`) and this log, so Codex and
  Claude follow the same project conventions.
- **Produced:** `AGENTS.md`, `CLAUDE.md`, `docs/AI_COLLAB_LOG.md`, README link.
- **What was wrong:** Nothing found yet; rules will be revised as the project grows.
- **Verified / fixed by:** Read through and approved by me before commit.
