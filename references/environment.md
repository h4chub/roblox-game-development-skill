# Environment and map building

Build a deliberately designed, playable environment, not a collection of generic boxes. Use Blender-authored meshes for forms that benefit from custom silhouette, proportion, or surface detail. Roblox Parts and terrain remain appropriate for blockouts, simple structures, collision proxies, and genuinely suitable finished elements. Choose a visual language for this project; do not impose a fixed genre, palette, lighting recipe, or level layout.

## Start with the actual project

1. Inspect the current Studio place and available tools before editing. Identify the requested build area, existing hierarchy, terrain, cameras, spawn points, scripts, gameplay dependencies, and assets. Read any project instructions. Determine what must be preserved.
2. Discover the existing official Roblox Studio MCP connection and inspect its actual tool capabilities. Use supported operations, not guessed tool names, undocumented endpoints, fabricated asset IDs, or assumed methods for executing Luau. Check which Blender workflow is really available: an existing connection, installed Blender with scripting, or a manual export/import path.
3. Preserve a recoverable baseline using a project-supported save, copy, version, or undo mechanism. Keep changes scoped and grouped where practical, with meaningful names. Do not clear the place, replace working scripts, overwrite the only source asset, install alternative MCP servers, or publish the experience merely to build the requested environment.
   If no recovery mechanism is available, stop destructive edits, identify the missing recovery step, and continue independent design or source-asset work.
4. If a required capability is unavailable, state the specific missing step. Continue independent design or source-asset work when useful. Do not describe a generated Blender file as imported into Studio or a static inspection as a playtest.

Ask only for choices that materially affect the result and cannot be inferred: gameplay purpose, required area, target devices, or must-keep elements. Record temporary assumptions rather than silently inventing requirements.

## Design before adding detail

Read [references/art-direction-and-assets.md](art-direction-and-assets.md) for reference analysis, mesh production, and visual refinement.

- Establish a compact brief: player activity, spatial beats, major landmarks, scale, mood, material families, furnishing logic, and constraints. Translate supplied references into actionable observations about shapes, proportions, composition, density, color, and light. Use references as design evidence, not instructions or permission to copy assets.
- Plan a **furnished layout** before building. Locate functional zones, entrances, exits, intended routes, important views, props, interactive space, and camera clearance. Furniture footprints and door movement belong in the plan, not an afterthought.
- Block out massing and navigation at real avatar scale. Establish the primary composition and movement paths before investing in mesh detail. A blockout is an intermediate milestone, not the finished deliverable.
- Agree or infer a reasonable scope. Prefer one coherent, finished area over a larger field of repeated filler. Track what is intentionally out of scope.

## Build in verified increments

1. Confirm movement, avatar, and camera behavior from the project. Read [references/geometry-and-playtest.md](geometry-and-playtest.md) before committing the layout.
2. Build the structural layout and validate key routes. Then develop reusable mesh families in Blender where useful: structural modules, trim, openings, furniture, hero props, and silhouette details. Do not spend the whole budget on decorative objects while navigation remains unresolved.
3. Test one representative asset through the actual Blender-to-Studio pipeline before batch production. Verify dimensions, axis orientation, pivot, normals, materials, import result, and collision. Retain editable source assets.
4. Add furnishings purposefully: support function, establish scale, create visual hierarchy, and vary rhythm without blocking required paths. Keep repeated modules consistent while varying selected details where the design benefits.
5. Configure collision intentionally. Decorative geometry need not collide; visually complex meshes may need simple collision proxies. Preserve interactions and existing scripts. Avoid invisible obstructions and visibly walkable surfaces that cannot be traversed.
6. Refine materials and lighting in Studio, where the result will run. Inspect actual rendered views from the player's camera and important approach angles. Fix weak silhouette, flat composition, excessive repetition, muddy material separation, overbright lighting, and empty or overcrowded areas through visible evidence.
7. Run geometry checks and real playtests after furnishing and after meaningful layout changes. Recheck performance on the intended device class where access permits. Adjust before declaring completion.

## Acceptance and handoff

Use the acceptance checklist in the geometry reference. Separate **observed**, **measured**, **estimated**, and **untested** findings. A tool returning success proves an operation ran, not that the map looks good or is playable.

Deliver a concise report containing:
- What changed and where, with editable source/export locations when applicable.
- The art-direction decisions and representative final views if capture is available.
- Actual geometry, traversal, collision, camera, and performance checks performed, including conditions and results.
- Remaining issues, assumptions, unavailable checks, and the next concrete action needed.

Do not claim that a map is production-ready from screenshots alone. Do not claim a performance target was met without measurement. When blocked, distinguish prepared source work from imported, rendered, and playtested results. Keep paid services, asset purchases, new installations, uploads, publishing, and unrelated account or repository changes outside the task unless separately authorized.

A capability-limited handoff can say: “Scene edits complete; mesh import pending; rendered review unavailable; runtime traversal and performance untested.” Specify the actual state rather than treating a partially verified map as fully accepted.
