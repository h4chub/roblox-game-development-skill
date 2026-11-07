---
name: roblox-game-development
description: Build, debug, and polish Roblox games across Luau gameplay, multiplayer, UI, environments, Blender meshes, R15 animation, VFX, and sound using the project's actual Studio and development tools. Use for complete game workflows or focused Roblox feature and asset tasks.
---

# Roblox Game Development

Develop a coherent, playable game rather than isolated impressive assets or disconnected scripts. Support the user's requested scope, whether a focused feature, an environment, or an integrated game. This skill provides workflow guidance, not a preinstalled automation framework, asset collection, or replacement for Studio.

## Inspect, preserve, and plan

1. Inspect project instructions, source structure, the current Studio place, existing systems, connected tools, and the requested task. Identify the source of truth: Studio, a filesystem project, a synchronization workflow, or a combination. Do not overwrite one with stale copies from another.
2. Discover the existing official Roblox Studio MCP connection and its exposed capabilities. Use only tools and APIs actually available. Check installed Blender and other tools as needed. An installed app does not imply remote control, export, upload, preview, or playtesting support. Do not invent tool names, asset IDs, paid/free service availability, or creator scripts mentioned but not provided.
3. Preserve a recoverable baseline before destructive changes. Check **Team Create/live collaboration and autosync before editing**: changes may become visible to collaborators or persist without an explicit publish. Do not assume a shared place is a private sandbox. Determine the intended change scope and recovery path; use an authorized copy or staging place when appropriate. If safety of the target is unclear, ask before shared/destructive edits. Do not disable collaboration, change permissions, or publish merely to complete local work.
4. Establish the smallest useful brief: player loop, requested outcome, target inputs/devices, multiplayer expectations, visual/audio direction, existing constraints, and acceptance criteria. Record assumptions and their sources. Avoid imposing a fixed aesthetic or turning a small task into an entire game rewrite.
5. Select only the modules relevant to the task. For cross-discipline work, first read coordination and define shared contracts before parallel changes.

## Modules

- [Coordination and integration](references/coordination.md): feature planning, parallel ownership, state and asset contracts, integration order, and completion evidence.
- [Gameplay, Luau, and multiplayer](references/gameplay-and-multiplayer.md): inspect existing architecture, implement behavior, validate server/client boundaries, persistence, and networked interactions.
- [UI and input](references/ui-and-input.md): functional screen flows, responsive layout, input support, readable feedback, and state-driven UI.
- [Environment and map building](references/environment.md): reference-led layouts, furnished worlds, Blender-based forms, and preserving an existing place.
- [Art direction and 3D assets](references/art-direction-and-assets.md): references, mesh creation/optimization, pivots, materials, and a verified export/import path.
- [Geometry and playtest QA](references/geometry-and-playtest.md): movement provenance, paths, collision, sight lines, high ground, fall recovery, and performance.
- [R15 animation](references/r15-animation.md): real rig inspection, clip creation, import, ownership, state integration, and actual R15 playback validation.
- [VFX](references/vfx.md): readable effects tied to events, network behavior, placement, lifecycle, and measured cost.
- [Sound](references/sound.md): licensed audio, event mapping, spatial behavior, mix, ownership, and verified in-game playback.

## Work in integrated increments

Build one thin end-to-end slice before expanding: input or trigger → authoritative game behavior → replicated state → relevant UI, animation, VFX, and sound → reset/cleanup. Choose the components actually needed for the requested task. Preserve working behavior and existing conventions.

Use temporary placeholders honestly while dependencies are missing. They are not final assets. Test one representative imported asset, animated rig, or networked interaction before repeating the production pattern. Reconcile movement and camera changes with environment clearances; include the **combined carried-player envelope** when carrying is part of gameplay.

Inspect the actual result through available Studio views and playtests. Screenshots can support visual review but cannot establish runtime behavior. Static code inspection and mocked tests do not establish real multiplayer replication, animation playback, asset permission, or device performance.

## Acceptance and truthful handoff

For each relevant discipline, record **check, evidence, result, limitation, next action**. Separate observed/measured passes, failures, estimates, and untested checks. State exact test conditions, including client count, rig, input mode, and runtime availability where relevant.

Before final acceptance:
- Verify the intended player flow and existing critical behavior, not only isolated new assets.
- For networked features, test actual multi-client behavior when possible; label it untested otherwise.
- For R15 animation work, verify on an actual R15 rig in Studio/runtime before calling the animation finished. If unavailable, deliver it as prepared/imported but playback-unverified.
- Recheck furnished geometry, carried-player traversal if applicable, UI state transitions, effect/audio cleanup, and representative performance.
- Retain editable sources and identify changed files/instances, imported assets, and incomplete steps. Remove or disable authorized temporary test artifacts and verify restoration.

Do not claim production readiness, successful publication, automated checks, or target-device performance without evidence. This package includes no executable validators. Create task-specific helpers only when useful, inspect them, run them in a safe context, and describe exactly what they verify.

Keep purchases, account changes, credentials, new tool installations, uploads, publication, and unrelated repository changes outside scope unless authorized. Never put credentials, private project data, or third-party proprietary assets/scripts into a public skill or repository. Missing tools should lead to a specific blocker and useful partial work, not invented results.
