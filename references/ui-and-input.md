# UI and input

Read when designing or implementing menus, HUDs, prompts, inventories, status displays, or onboarding.

## Design the actual player flow

Inspect existing UI hierarchy, styling, state management, camera overlays, and input bindings. Identify the screen's purpose and the next action it should make clear. Plan necessary states: loading, empty, active, selected, disabled, error, success, and dismissal as applicable. Do not create a polished static mockup and call the interaction complete.

Use the project's visual direction rather than a generic dashboard aesthetic. Establish readable hierarchy, restrained type roles, spacing, contrast, and consistent icon/action language. Keep important gameplay visible and avoid covering critical touch controls or navigation cues.

## Implement responsively

Use supported Roblox UI layout and sizing tools appropriate to the existing project. Check aspect ratios, safe insets, text length/wrapping, scrollable content, and scale behavior. Avoid assuming one desktop viewport represents all supported devices.

Choose deliberate input behavior for keyboard/mouse, touch, and gamepad only where those modes are supported or requested. Verify focus/selection order, button hit areas, back/cancel, modal input capture, and prompt text for the active input mode. Do not let a hidden or covered control remain accidentally actionable.

Drive UI from defined game state and events. Display authoritative results for consequential actions; local optimistic feedback must reconcile failure or rejection. Debounce repeated requests where appropriate and provide visible pending/error states. Clean up bindings and screen instances on close, reset, or scene changes.

Avoid relying solely on color, tiny text, or motion to communicate critical state. Provide readable labels and appropriately restrained feedback. Respect reduced-motion or accessibility behavior already present in the game.

## Verify function and appearance

Inspect actual rendered UI at representative viewport sizes. Test open/close, confirm/cancel, repeat activation, state changes, and return to gameplay. Check overflow, clipping, alignment, overlapping layers, input capture, focus, and camera/control restoration.

For a multiplayer feature, verify that each player sees the correct private/local state and shared status, especially when interactions are rejected or interrupted. Test respawn and re-entry where UI must rebuild.

Report which viewports and input modes were actually tested. An emulator helps check layout but does not establish physical-device performance or every real input behavior. If only design files or code were prepared, say so explicitly.
