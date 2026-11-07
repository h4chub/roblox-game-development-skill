# Gameplay, Luau, and multiplayer

Read for game systems, debugging, player interactions, or networked behavior.

## Inspect architecture before editing

Find the existing server/client entry points, shared modules, event patterns, state ownership, controller scripts, and dependencies. Determine whether source is managed in Studio or synchronized from files. Preserve project conventions and existing script behavior. Verify current Roblox API signatures and behavior in official documentation when uncertain rather than inventing convenience APIs.

Define the smallest observable change. For a bug, reproduce or obtain the exact symptom, expected behavior, context, and logs. Distinguish a confirmed cause from a hypothesis. Avoid broad rewrites before a targeted diagnosis.

## Separate authority and presentation

The server should validate consequential gameplay actions and state: eligibility, ownership, distance, resources, cooldowns, target validity, and state transitions. Treat client requests as requests, not facts. Check input types/ranges and rate-limit abuse-prone requests as appropriate to the feature. A responsive client animation does not prove the authoritative action succeeded.

Keep input, camera, UI, and local presentation on the appropriate client side. Use the existing replication pattern; do not create unnecessary remotes or broadcast frequent cosmetic updates to all clients. Never move secrets into shared/client-readable modules.

For physics interactions, inspect actual network ownership, collision groups, assemblies, and server correction behavior. Do not assume a welded model or a locally moved part behaves identically for other players. Avoid arbitrary per-frame position writes that fight the existing controller or physics.

## Make state transitions explicit

Define valid states and transition conditions. Handle repeated requests, simultaneous actors, cancellation, death, respawn, disconnect, target removal, and cleanup. Disconnect event listeners and clean up temporary objects/tasks when their owner or action ends. Prefer event-driven updates to unbounded polling when suitable.

For carrying or interacting with another player:
- Validate both actors and the intended game rules on the server.
- Prevent contradictory states such as two carriers claiming one target.
- Preserve and restore movement, collision, animation, and control settings deliberately; avoid restoring guessed defaults over current configuration. Do not restore a stale snapshot over sprint, buffs, debuffs, or other changes made during carrying. Respect the existing modifier ownership system or recompute the effective state when the carry ends.
- Test combined rig placement and camera behavior, then coordinate doorway/corner/platform clearance with environment QA.
- Validate safe drop/release placement and recovery after interruption, death, or departure.

## Persistence and existing data

Use existing persistence infrastructure when present. Inspect keys, schemas, migrations, retry/error behavior, concurrency, and save boundaries. Test changes against isolated test data or an authorized test environment. Do not enable Studio access to live services, overwrite live player data, or migrate production data merely to test a feature.

If persistence testing is unavailable, review logic and mark real service behavior unverified. Handle service failures without pretending a save succeeded. Do not hardcode credentials or place private data in public examples.

## Test in increasing realism

Use available linters, type checks, or unit tests only when they actually exist or have been implemented and run. Record their commands and results. Then test the real Studio flow: input → validation → state change → replicated behavior → presentation → cleanup.

For multiplayer, run a supported server with multiple clients and inspect both actor and observer perspectives. Test contention, late joining, interruption, repeated activation, and disconnect behavior relevant to the feature. Simulated latency tests are useful when available; do not invent them or claim a single-client run proves network correctness.

Inspect output/errors and meaningful state, not only whether the script loaded. Deliver what passed, the conditions, and remaining uncertainty. Static review, mocked tests, solo Studio testing, and real multi-client testing must remain distinguishable.
