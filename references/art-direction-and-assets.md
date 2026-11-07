# Art direction and asset production

Read when establishing the look, creating assets, importing meshes, or polishing the scene.

## Turn references into design decisions

Use the user's images, sketches, existing scene, and gameplay brief first. If more references are needed, use available authorized sources. Ask for a reference only when choosing without it would materially risk the wrong result.

Extract a small set of concrete observations:
- **Shape language:** rounded or angular forms, dominant silhouettes, mass-to-detail ratio, edge treatment, and intentional exaggeration.
- **Proportions:** room height versus width, opening size, furniture scale, thickness of structural elements, and scale relative to the avatar.
- **Composition:** focal point, foreground/midground/background, view framing, negative space, vertical hierarchy, and route legibility.
- **Materials and color:** distinct material families, value separation, accent placement, wear patterns, and consistency of surface detail.
- **Lighting:** source motivation, light/dark grouping, readable paths, interior/exterior contrast, and atmosphere.
- **Density:** where detail gathers and where the player needs visual rest or physical clearance.

Choose principles that suit the brief. A sparse stylized scene can be finished; a cluttered photorealistic scene is not automatically better. Do not substitute a stock neon, low-poly, medieval, or realistic style for the requested direction.

Define a few observable success criteria, such as a landmark reading from the entrance, the main route remaining legible, or furniture supporting the room's purpose. Avoid arbitrary numerical beauty scores.

## Plan functional spaces

Make a simple zone and adjacency plan. Record the role of each area, its access points, major props, and intended player views. Reserve clearance for the avatar, the camera, and interaction with objects. Mark doors, stairs, corners, low ceilings, transitions, and any intentionally constrained spaces.

Choose furnishing from the function of the area, not a random prop list. Arrange related objects into coherent groups. Use size and placement to build hierarchy. Check the design both from above and from the intended gameplay camera; a good aerial plan can conceal poor ground-level sight lines.

## Blender production

Use the installed version and tools actually available. For generated Blender scripts, check the corresponding Blender API/version and run the scripts in a disposable asset file before applying them to valuable source work. Never present speculative scripts as tested utilities.

- Build at a documented unit convention and verify imported dimensions in studs. Do not assume Blender units, export units, and Roblox studs map identically across every importer configuration.
- Use a small reusable kit where repetition is intentional. Model hero silhouettes separately when modular pieces would make them bland or awkward.
- Keep mesh density proportional to visible benefit, viewing distance, and target hardware. Use geometry for silhouette and important depth; use materials or texture detail when more geometry adds little.
- Check transforms, object origins, local axes, normals, backfaces, overlapping faces, degenerate geometry, and any modifier/export consequences. Keep clean source objects or source copies when applying destructive operations.
- Ensure the chosen material/texture workflow actually survives the supported export/import route. A Blender shader graph is not proof of a Roblox-compatible material. Check UVs, texture paths, tiling, seams, and imported appearance as applicable.
- Keep a readable asset inventory: source name, intended Studio object/location, export file, dimensions, pivot convention, materials/textures, and collision approach. Record origin and license for third-party assets. Do not copy a creator's private scripts or assets from a description of their workflow.

Before batch import, inspect and optimize the exported meshes: remove accidental duplicate or hidden geometry, apply suitable simplification, check normal/shading results, and ensure texture sizes and collision plans suit the intended devices. Compare silhouette and important detail before and after optimization; do not simplify blindly.

Export through a format supported by the current Studio import path and available tools. Test one asset before batch export. If the workflow requires asset upload or a manual Studio import, identify that step honestly and follow the user's permissions. Do not fabricate the resulting asset ID or imply publication happened locally.

## Evaluate the rendered scene

Capture or inspect consistent views so iterations can be compared:
- Entrance or spawn at the real player camera height.
- Main route and focal landmark.
- A furnished interior or dense area.
- Tight transitions, vertical changes, and any distant vista relevant to play.

Inspect the Roblox render, not only Blender's render. Check readability, scale, silhouette, material cohesion, repeated patterns, visible seams, flicker, clipping, and shadow/light artifacts. View from multiple angles and move the camera; one flattering still can hide intersections and blocked paths.

Make targeted revisions: state the visible problem, change the geometry/material/layout/light responsible, and inspect again. Do not hide layout problems with darkness, fog, excessive effects, or a camera angle the player will never use.
