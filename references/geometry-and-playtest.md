# Geometry, traversal, and performance QA

Read before layout commitment and again for final acceptance. The furnished, collidable scene is the test subject, not only the original blockout.

## Establish the actual movement envelope

Inspect the current project and a running player when possible. Record the source and verification state of:
- Avatar rig, dimensions, scaling, collision behavior, and relevant controller type.
- Walk/sprint speeds, acceleration or custom locomotion, jump behavior, gravity, slope limits, and climbing or other traversal abilities.
- For a Humanoid-based controller, the relevant runtime values may include WalkSpeed, UseJumpPower, JumpPower or JumpHeight, HipHeight, and MaxSlopeAngle. Check whether project scripts override them and whether a custom controller makes them irrelevant.
- Camera mode, offset, zoom limits, and behavior near walls and ceilings.
- Intended device/input modes and any alternate supported avatars.

Do not silently use Roblox defaults or a remembered character size. If runtime values cannot be inspected, state each assumed value and its source. Mark dependent reachability conclusions as estimates, then test when access is restored.

## Carrying and combined-player clearance

When gameplay includes carrying, escort attachment, or another combined rig, measure the complete moving envelope: carrier, carried player, animated limbs, attachment offsets, collision configuration, and camera. Single-avatar clearance is insufficient. Verify doors, tight corners, stairs, ramps, ceilings, platform landings, and drop/release positions with the actual carrying state. Check both direction of travel and relevant turning poses, safe recovery after release, and behavior when carrying is interrupted. Record whether the combined state was runtime-tested or only estimated from geometry.

## Inspect geometry at useful precision

1. Inventory required destinations and connect them with intended routes. Include spawn, objectives, interactions, exits, and recovery paths. Direction matters: a reachable drop may not be climbable in reverse. Check standable tops and high ground, including roofs, furniture, and floating platforms: distinguish intentionally unreachable scenery from inaccessible intended destinations or unintended advantages. Test whether climbing or jumping permits access to off-limits areas.
2. Check each route in its furnished state for clear width, overhead space, corners, door openings, furniture protrusions, stairs, slopes, ledges, landing areas, and camera clearance. Measure the narrowest point, not just the room width. Where spacing matters, measure gaps and platform-to-platform distances against the actual movement envelope. Evaluate fall distances together with the game's fall damage, reset, and recovery behavior; a survivable drop can still strand the player.
3. Treat bounding boxes as broad screening. Rotated or concave meshes, collision decomposition, and decorative objects can make bounds misleading. Verify actual collision shape and controller behavior before calling a route blocked or safe.
4. Inspect intended sight lines from the player's camera and relevant approach angles. Consider walls, foliage, furniture, camera occlusion, and visibility of navigation cues or gameplay targets. Preserve intentional occlusion when it supports the brief.
5. Check intersections, floating objects, gaps, unwanted seams, and near-coplanar surfaces likely to flicker. Inspect from multiple angles and distances. Resolve duplicate faces or unintended overlap; use deliberate trim or a justified offset instead of arbitrary offsets that create new gaps.
6. Inspect collision and query configuration appropriate to the project. Check decorative collision, invisible blockers, thin/complex mesh collisions, collision groups, and moving or scripted elements. A raycast or bounds query is only as valid as its filters and the geometry it considers.

## Use calculations as estimates, not a certificate

For a simple ballistic jump with known upward launch speed v and positive gravity magnitude g, peak rise is approximately v²/(2g); return-to-launch-height flight time is approximately 2v/g. Horizontal distance is approximately horizontal speed multiplied by flight time only if that speed is maintained.

These estimates do not model controller-specific jump behavior, acceleration, moving platforms, differing landing heights, collision shape, head strikes, slopes, air control, or input timing. Do not derive launch speed from a configured height without confirming the active controller's behavior. Leave a practical margin appropriate to the game and verify the landing in play. Never make a required route depend on an untested maximum-range jump.

A pathfinding result may help identify route problems, but is not proof that the actual player controller can traverse them. It is also not a substitute for testing intended jumps or player-specific interactions.

## Playtest representative routes

Use a supported Play/Test workflow when available. Do not change working gameplay scripts solely to make the test easier. If temporary test objects or scripts are necessary and authorized, keep them scoped and remove or disable them afterward, verifying restoration.

At minimum, where relevant to the map:
- Spawn and reach each required destination using the real controls.
- Traverse tight turns, doors, stairs, slopes, jumps, and elevation transitions in both intended directions.
- Test furniture clearance, collision boundaries, landings, ceiling clearance, and the camera near walls.
- Exercise interaction spots from reachable positions, including required doors or moving geometry.
- Look for snagging, falling through, unintended shortcuts, off-limits access, inaccessible intended high ground, inescapable pockets between objects, and a way back from optional areas. Check floating platforms for intentional support/placement, reachable landings, and recovery after a missed jump.
- Repeat after collision or furnishing changes; a previous blockout pass does not certify the finished scene.

For inaccessible input modes, avatars, devices, multiplayer conditions, or runtime tools, report what remains untested. A static walkthrough or planned test list is not an executed playtest.

## Performance in context

Set targets from the user's devices and game requirements, or label temporary targets as assumptions. Avoid universal polygon/part budgets. Measure representative dense views and traversal, accounting for scripts and existing content rather than attributing every cost to meshes.

Inspect mesh and object counts, material/texture diversity, repeated asset reuse, transparency/overdraw, shadows and lights, collision complexity, physics activity, and streaming behavior when relevant. Use available Studio statistics or profiling tools to identify actual bottlenecks. Record the scene, device or test environment, camera location, and measurement conditions. Studio desktop results do not establish mobile performance.

Optimize what measurements or visible evidence justify: simplify unseen geometry/collision, reuse assets, reduce expensive overlapping transparent layers or unnecessary shadow casting, and preserve important silhouettes. Do not change game-wide streaming or rendering settings casually to disguise a local performance issue.

## Acceptance record

Keep a compact record with columns or bullets for **check, evidence, result, limitation, follow-up**. Use these states:
- **Observed/measured pass:** Checked in the stated conditions, with evidence.
- **Fail:** Reproducible issue, location, and practical fix.
- **Estimated:** Reasoned from dimensions, bounds, or assumptions; not verified in play.
- **Untested:** The required evidence is unavailable or the check was not run.

Cover these gates before claiming completion:
1. Required project state and working behavior preserved.
2. Requested art direction, furnishing, and scale assessed in actual rendered views.
3. Required routes, interactions, clearances, and intentional sight lines checked.
4. Collision, overlaps, z-fighting, seams, and camera clipping inspected.
5. Actual controller traversal and representative jumps/landings tested.
6. Performance assessed under stated conditions or explicitly left unverified.
7. Editable sources retained, imported assets identified, and temporary test artifacts cleaned up.

When a gate fails, repair and retest the affected paths and views. When a gate is untested, report the limitation rather than silently converting it into a pass.
