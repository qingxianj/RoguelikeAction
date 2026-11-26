# RoguelikeAction (working title)

A top-down 3D action roguelite built in Unity: melee combos and skills, room-by-room runs, pick one of three upgrades after each room, a two-phase boss, and meta progression between runs. It also includes a Unity editor tool that uses an LLM to generate upgrade and skill configs from a plain-language description.

> Status: early development. Target for the first playable build: 2027-02-28.

## Tech

- Unity 2022.3 LTS (2022.3.62f3c1, Unity China build), Universal Render Pipeline 14 (template: Universal 3D)
- Input System 1.7 (keyboard/mouse and gamepad; touch later). Active input handling is set to "Both" so legacy-input samples still run.
- AI Navigation 1.1 (NavMesh) for enemy pathfinding
- Planned: Cinemachine for the camera

## Project layout

```
Assets/
  _Project/
    Scripts/          RoguelikeAction.asmdef (runtime code)
      Core/           event bus, utilities, game flow
      Input/          input handling
      Player/         player controller and state machine
      Combat/         hitboxes, hurtboxes, damage, hit feedback
      Enemies/        enemy AI and boss behavior tree
      Roguelike/      room flow, upgrade pool, run state
      UI/             menus, HUD, upgrade selection
      Save/           save/load (JSON)
      Data/           ScriptableObject definitions
      Editor/         RoguelikeAction.Editor.asmdef (editor-only code)
        AITools/      LLM config generator
    Data/             ScriptableObject assets (skills, enemies, buffs)
    Prefabs/  Scenes/  Animations/  Art/  Audio/
  ThirdParty/         imported third-party assets, untouched
```

## Design notes

Each system gets a short write-up here once it works: how it is designed, why, what went wrong, and how it was fixed.

- Player state machine: _TBD_
- Combo and input buffer: _TBD_
- Hit detection and damage: _TBD_
- Enemy AI and boss behavior tree: _TBD_
- Upgrade system: _TBD_
- Object pooling and profiling results: _TBD_
- AI config generator: _TBD_

## Third-party assets

| Asset | Source | License |
| --- | --- | --- |
| _none yet_ | | |

## Working with AI

AI tools (Claude Code, Codex) help with this project. Core gameplay systems are designed and
first-drafted by hand; AI reviews them. Rules for agents are in [AGENTS.md](AGENTS.md), and
[docs/AI_COLLAB_LOG.md](docs/AI_COLLAB_LOG.md) records what each AI produced, what it got wrong,
and how it was verified.

## API keys

The AI config generator reads its API key from an environment variable or a `*.local.json` file. Both are git-ignored. Never commit keys.
