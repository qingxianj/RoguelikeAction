# Agent instructions

These rules apply to every AI coding agent working in this repo (Codex, Claude Code, or others).
`CLAUDE.md` imports this file, so keep project rules here, in one place.

## About the project

A top-down 3D action roguelite in Unity: melee combos and skills, room-by-room runs, pick one of
three upgrades, a two-phase boss, meta progression, plus an editor tool that uses an LLM to
generate upgrade/skill configs. It is the owner's portfolio project for game client job
interviews. The owner is new to Unity, knows Java well, and must be able to explain every
system in this repo in an interview. Optimize for the owner's understanding, not for speed.

## Talking to the owner

- Talk to the owner in Chinese.
- Code, code comments, identifiers, commit messages, and repo docs are in English.

## Tech stack (do not change without asking)

- Unity 2022.3.62f3c1 (Unity China build), Universal Render Pipeline 14
- Input System 1.7, Active Input Handling = Both
- AI Navigation 1.1 (NavMesh)
- Do not upgrade Unity or packages, and do not add packages, without the owner's OK.

## Where things go

- Own code and content: `Assets/_Project/`
  - Runtime code: `Assets/_Project/Scripts/` (asmdef `RoguelikeAction`, namespace `RoguelikeAction.*`)
  - Editor-only code: `Assets/_Project/Scripts/Editor/` (asmdef `RoguelikeAction.Editor`)
  - Folder layout is described in `README.md`. Follow it.
- Third-party assets: `Assets/ThirdParty/<AssetName>/`, kept as imported. Do not edit them in
  place; copy what you need into `Assets/_Project/` and change the copy.
- Every third-party asset gets a row in the README asset table (name, source URL, license).
- Always commit `.meta` files together with their assets. Never delete or regenerate a `.meta`
  file by hand (that breaks references).

## Who writes what

Core systems are designed and first-drafted by the owner. For these, the agent reviews,
explains, asks guiding questions, and points out bugs. It does not write the system outright,
even when asked to "just do it"; offer hints, pseudocode, or a small isolated example instead.

Core systems:

1. Player state machine (states, transitions, combo and input buffer)
2. Hit detection and damage (hitboxes, hurtboxes, damage pipeline)
3. Upgrade system (upgrade pool, pick-1-of-3, how upgrades modify stats and skills)

Everything else (UI wiring, tooling, editor scripts, save/load, utilities, shaders, tests) may be
AI-written, but the agent must explain what it wrote: what each part does, why it is designed
that way, and what Unity concepts it relies on. Prefer small, readable code over clever code.

## Secrets

- Never commit API keys or tokens. Keys live in environment variables, `.env`, or `*.local.json`
  files, which are git-ignored.
- Never print a key in chat, logs, or commit messages. If a key shows up in a diff, stop and tell
  the owner.

## Git

- Small, focused commits with English messages in the imperative mood
  (e.g. `Add idle/run animator for knight`).
- Commit only files you changed for the current task. Review `git status` and `git diff` first.
- Do not commit `Library/`, `Temp/`, `Logs/`, `UserSettings/`, or IDE files (see `.gitignore`).
- Do not push, force-push, rewrite history, or change branches unless the owner asks.

## Working alongside other agents

The owner may run Codex and Claude Code on this repo at the same time.

- Never edit the same files another agent (or the owner) is editing at the same time. Before
  starting, agree on which files or folders each one owns for the task.
- Unity scenes, prefabs, and `.asset` files are YAML and merge badly. Only one agent (or the
  owner) touches a given scene or prefab at a time.
- If you find unexpected changes in files you did not touch, do not revert them; ask the owner.

## AI collaboration log

After any non-trivial AI-assisted task, add an entry to `docs/AI_COLLAB_LOG.md`: date, task,
which AI, what it produced, what was wrong, and how it was verified or fixed. This log is
interview material; be honest about mistakes.
