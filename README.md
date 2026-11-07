# Roblox Game Development Skill

A portable instruction skill for Roblox development with Claude Code or another assistant that can load Markdown skills. It covers gameplay, multiplayer, UI, environments, 3D assets, R15 animation, VFX, sound, and integration. It expands the original environment-building guidance rather than discarding it.

## Install in Claude Code

Extract this folder into one of these locations:

- Project only: `<your-project>/.claude/skills/roblox-game-development/`
- Personal installation: `~/.claude/skills/roblox-game-development/`

The resulting entry point must be `roblox-game-development/SKILL.md`, with `references/` alongside it. Do not introduce an extra nested skill folder. Keep this README with the package for installation and workflow guidance.

Ask Claude Code to use the `roblox-game-development` skill for your task. If your version supports skill slash invocation, invoke `/roblox-game-development` and describe the task. Follow your installed Claude Code version's current skill-discovery instructions if needed.

For other assistants, load `SKILL.md` as task guidance and read only the referenced modules relevant to the request. Their installation formats and tool support may differ. The package does not grant tools or permissions.

## Prerequisites and boundaries

- An existing Roblox project or a clearly authorized new-project task.
- Roblox Studio and the existing official Studio MCP connection when live inspection/editing is desired. Check the tools actually exposed; playtesting, screenshots, importing, and uploading are not guaranteed.
- Blender only for workflows that need it. Use an installed accessible copy or an existing supported connection. No specific Blender MCP server is required or bundled.
- Permission for any uploads, publishing, new installations, purchases, or shared-project changes your task requires.

No API credentials, bundled creator scripts, paid subscriptions, external-generation services, executable checkers, or third-party assets are included or required by the package itself. Missing capabilities are reported instead of silently assumed. Specialized tasks may require tools or assets you choose to supply.

**Team Create warning:** Studio edits can autosync into a shared place without an explicit publish. Confirm the intended project, recovery path, and shared-edit scope before editing. Installing this skill does not create a safe sandbox.

## Example workflows

### Implement a multiplayer interaction

“Use this skill to add a carry/rescue interaction to this existing project. Inspect the current architecture first, preserve existing controls, and test both players and observers. Include carried-player doorway clearance and safe release.”

Start with coordination and gameplay/multiplayer. Add UI, R15 animation, effects, sound, and geometry modules only as needed. Build a thin end-to-end slice before polishing every asset.

### Create a playable environment

“Use these references to build a furnished rooftop area in my existing map. Use custom Blender meshes where they improve the forms. Verify movement values from the project, check high ground and fall recovery, and tell me which playtests you actually ran.”

Use the environment, art/asset, and geometry modules. The full original environment workflow remains in those references.

### Animate an R15 action

“Create and integrate an R15 carrying animation using the project's actual rig. Test a representative clip through import first and verify real R15 runtime playback before calling it finished.”

Use the R15 module plus coordination/gameplay where needed. If runtime testing is unavailable, the result must be explicitly labeled playback-unverified.

### Polish a game feature

“Improve the UI, VFX, and sound for this existing ability without changing its game rules. Verify all feedback follows the authoritative state, including cancellation and respawn.”

Use coordination and the relevant presentation modules. Report actual visual/listening tests and what remains unverified.

## Package layout

- `SKILL.md`: task routing, project safety, integration, and acceptance requirements.
- `references/coordination.md`: ownership and cross-discipline contracts.
- `references/gameplay-and-multiplayer.md`: Luau, state, networking, persistence, and runtime tests.
- `references/ui-and-input.md`: UI states, layout, input, and interaction validation.
- `references/environment.md`: original environment-building workflow.
- `references/art-direction-and-assets.md`: reference analysis, Blender meshes, import, and visual refinement.
- `references/geometry-and-playtest.md`: real movement, geometry, navigation, collision, and performance QA.
- `references/r15-animation.md`: real-rig animation production and validation.
- `references/vfx.md`: event-driven visual effects and cleanup.
- `references/sound.md`: asset provenance, playback, spatial audio, and mix checks.

## Sharing in a public repository

Commit the skill folder and its Markdown references only. Review changes for credentials, private project identifiers, proprietary code, and third-party asset data before sharing. This package contains workflow instructions, not permission to redistribute someone else's material.

Choose an appropriate repository license explicitly before advertising licensed reuse. No license has been selected on your behalf. Installing or sharing the files does not publish a Roblox experience or configure any external services.

## Verification limits

The package structure and references can be checked locally, but no Roblox game or asset is certified by installing this skill. Each task must distinguish authored, exported, imported, rendered, runtime-tested, multiplayer-tested, and published work. Real R15 playback, carried-player navigation, audio listening, and target-device performance require the corresponding actual test environment.
