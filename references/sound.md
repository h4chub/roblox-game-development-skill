# Sound

Read for gameplay cues, ambient audio, music, footsteps, UI sounds, or sound integration.

## Plan the listening experience

Identify the event/state, audience, spatial or nonspatial behavior, timing, loop boundaries, mix role, and interruption rules. Separate ambience, music, UI feedback, and critical gameplay cues so they do not compete unnecessarily.

Inspect existing audio architecture and current supported Roblox APIs rather than forcing a legacy or unfamiliar system into the project. Use sounds the user owns or is authorized to use. Record the source and license where applicable. Do not scrape or copy proprietary music/sound data from a reference video.

Optional external audio tools may help only if available and authorized. Do not assume a free generator, API, account, or sufficient license exists. Missing sound assets should remain explicit placeholders or blocked tasks, not fabricated asset IDs.

## Integrate deliberately

Test a representative asset through the actual upload/import and playback path. Verify experience ownership/access permissions and the returned asset identifier. Editing an audio file locally is not a completed upload, and a valid-looking ID is not evidence of playable access.

For spatial sound, verify the emitter follows the intended object, distance behavior is appropriate, and nearby/distant listeners hear what the design intends. For local UI audio, avoid broadcasting it to everyone. Use the project's intended replication/presentation pattern to prevent duplicate playback.

Balance volume and frequency with other sounds. Check loops for discontinuities, transitions for abrupt cuts, repeated effects for excessive stacking, and critical cues for masking. Provide or preserve user audio controls where relevant to the requested scope. Do not infer loudness quality from waveforms or metadata alone.

## Listen and verify

When audio playback/capture is actually available, listen to the integrated result, not only the source file. Test trigger timing, repeated use, concurrent sounds, player distance, state transitions, cancellation, respawn, and cleanup as applicable. Verify multiple listeners for networked spatial events when possible.

If the tools cannot produce an audible preview, explicitly mark listening/mix quality unverified. Static properties and successful playback calls do not prove that the user can hear the right asset, at the right level, under experience permissions. Provide the exact remaining listening and permission checks rather than claiming audio polish is complete.
