# VFX

Read for particles, trails, beams, impact effects, environmental effects, or ability feedback.

## Define the effect's job

Identify the event, viewer, world/local attachment, duration, intended visual message, and cleanup trigger. Distinguish cosmetic feedback from gameplay hit detection or state. A visually convincing hit effect must not become the authority for damage or success.

Match the existing art direction: shape language, color hierarchy, timing, scale, density, and contrast. Ensure the effect is readable from the actual gameplay camera without obscuring targets, UI, or required navigation. Use reference principles rather than copying proprietary textures or effects.

## Build with available assets and tools

Inspect supported Studio objects and current APIs before implementing. Use existing licensed textures/assets when suitable; generate or import new material only through available authorized tools. Do not promise free external generation services or invent texture IDs.

Confirm attachment positions, local/world orientation, lifetime, emission timing, transparency, size, and light interaction as relevant. Test moving characters and objects, not only stationary placement. For a burst versus a persistent effect, choose a lifecycle that actually matches the action.

Use the game's existing event pattern. Decide whether each client should render the effect and how activation is replicated. Avoid broadcasting large per-frame cosmetic state unnecessarily or duplicating effects when server and client both trigger them.

## Verify timing, cleanup, and cost

Test activation, repeated use, simultaneous actors, cancellation, death, target removal, and scene unload where relevant. Clean up temporary emitters, attachments, listeners, and scheduled work. Test loops and interrupted effects for leaks or stranded visuals.

Inspect the effect in the real Studio render under representative lighting and camera distances. Check overdraw, excessive transparency layers, particle counts, lights/shadows, and concurrent bursts. Profile representative combined use rather than relying on an isolated effect looking smooth.

Report observed appearance separately from runtime timing, replication, cleanup, and performance. If the connection cannot render or playtest, state those checks are unverified and deliver only the source/scene work actually completed.
