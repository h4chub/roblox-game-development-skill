# Coordination and integration

Read for a whole-game task or any feature crossing code, UI, world assets, animation, VFX, or audio.

## Establish the shared contract

Inspect what already exists. Write a compact task-specific contract covering only relevant items:
- Gameplay loop, authoritative state owner, inputs, success/failure conditions, and reset behavior.
- Existing module locations, public interfaces, remote-event payloads, instance paths/tags, and naming conventions.
- Avatar rig, movement values and runtime overrides, camera behavior, collision policy, and interaction distances.
- UI state/event contract, animation states/markers, effect attachment points, sound events, and asset identifiers once real IDs exist.
- Asset dimensions, axes, pivots, attachment naming, import destination, ownership/permissions, and source files.
- Test scenario and measurable acceptance criteria, with unresolved assumptions identified.

Treat proposed paths or interfaces as proposals until checked against the project. Do not require unrelated teams or systems to adopt a new architecture for a small feature.

## Parallel work without collisions

Divide by stable interfaces and nonoverlapping ownership, not simply by tool. Identify who owns each file, model, shared state interface, and integration step. Do not have several agents rewrite the same controller or mutate the same Studio model concurrently. Team Create autosync makes shared writes consequential even without publication.

Pass each worker the actual task, relevant project constraints, available tools, contract, source locations, and acceptance criteria. Explicitly state what must remain unchanged. Workers should report changed artifacts, evidence, assumptions, blockers, and integration requirements. Do not treat another worker's confidence as a substitute for test evidence.

Use placeholders with explicit names and tracked replacements while waiting on assets. Keep real asset IDs separate from placeholder labels; never insert invented numeric IDs. Do not duplicate full game state in every subsystem. Make UI, effects, and audio respond to the intended authoritative state or presentation events.

## Integrate a thin slice

A suitable sequence, adapted to the task:
1. Make the essential gameplay transition work with a simple existing test object.
2. Verify client/server responsibility and state transitions, including cancellation/reset.
3. Integrate one final-quality asset or animation through the real import path.
4. Add UI, effects, and audio to the same verified transitions.
5. Test the complete flow, then scale the pattern to remaining content.

For a carry/rescue feature, cover pickup consent/rules as defined by the game, server validation, carried state, attachment/positioning, input restrictions, animations, UI prompts, collision, doorway clearance, drop placement, death, reset, disconnection, and cleanup. Do not infer the user's intended game rules; use this as a dependency checklist.

## Validate the combined result

Test first entry, repeated use, interruption, cancellation, death/respawn, and cleanup where relevant. Check two players acting at once, late joining, or missing/delayed assets for networked features. Verify that UI, animation, VFX, and audio agree with the actual game state.

Re-run affected geometry checks when movement, rig size, carrying, furniture, or camera behavior changes. Re-run performance checks after combining effects and assets; individually inexpensive pieces can create expensive combined views.

Report component state precisely: authored, exported, imported, statically reviewed, rendered, runtime-tested, multiplayer-tested, or published. These are different milestones. List the next concrete action for each blocker. Do not call the entire game complete merely because all workers returned artifacts.
