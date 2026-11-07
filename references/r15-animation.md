# R15 animation

Read for R15 character animation, Blender rig animation, import, or animation-state integration.

## Verify the real target rig

Inspect the project's actual avatar configuration and a real target rig. Confirm it is R15, not an R6 or arbitrary similarly named skeleton. Check proportions/scaling, joint hierarchy, rest pose, root orientation, attachment expectations, controller/Animator setup, and any custom rig differences. A file named “R15” is not proof of compatibility.

Use an existing verified rig or an authorized supported rig-generation/export workflow. Do not fabricate a compatible skeleton from approximate body-part names. Inspect the actual Blender-to-Roblox mapping/import capabilities before authoring a large animation set.

## Plan and create clips

Define each clip's gameplay purpose, entry/exit state, duration, looping, contact points, and intended root/body motion. Match style to the game's art direction and movement. Use references for motion principles without copying unlicensed animation data.

For Blender work, preserve the source rig and animation actions, confirm axes/scale/rest pose, and check any export baking or constraint limitations. Verify joint motion, keyframe timing, planted contacts, continuity, and silhouettes from several views. Avoid unintended translation, sliding feet, joint flips, hyperextension, and discontinuities at loop boundaries.

For paired or carried-player animations, verify relative actor orientation, attachment alignment, hand/body contact, and transitions with both actual rigs. Avoid designing one clip in isolation and assuming it aligns with the second actor or collision setup.

## Prove the pipeline early

Send one short representative clip through the actual supported export/import workflow before creating the full set. Verify the resulting clip on the target R15 rig. Inspect retargeting, joint mapping, orientation, frame timing, looping, and any discarded data.

Publishing/importing and permission configuration are separate steps. Use only real returned asset IDs. Verify the asset can be used by the intended experience owner/group under the actual permission model. Do not assume an animation visible in an editor is playable by the live experience. Do not upload or publish without the relevant authorization.

## Integrate with real gameplay

Use the project's existing animation-controller conventions and supported APIs. Verify where the Animator is created and who owns/starts playback for the actual rig arrangement; confirm the applicable replication rules rather than assuming a locally visible track reaches other clients. Check animation priority, blending, looping, transitions, interruption, and conflicts with idle/walk/jump or other actions. Trigger gameplay through authoritative state rather than trusting a cosmetic clip. If markers drive presentation, verify their existence, timing, and cleanup; do not invent marker names as if they were embedded.

Test from the actor's view and another client's view when replication matters. Confirm death, respawn, cancel/drop, repeated actions, and leaving the state stop or transition the track correctly. Restore existing animation behavior rather than replacing the entire controller unnecessarily.

## Final R15 gate

Before calling animation work finished, inspect actual playback on a real R15 rig in Studio/runtime under the intended action. Verify pose quality, timing, contacts, scaling, state transitions, and relevant multi-client visibility. Blender playback alone is insufficient.

If unavailable, deliver editable source and exports or imported clips with an explicit status: “R15 runtime playback unverified.” State the missing tool/manual action and provide a concrete test sequence. Do not call a skeleton inspection, exported file, or successful import a completed runtime validation.
