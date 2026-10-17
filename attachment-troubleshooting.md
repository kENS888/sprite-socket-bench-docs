# Godot muzzle flash drifts while walking?

**If your muzzle flash lines up while idle but floats above the gun when walking, first inspect the source pixels—not just the node hierarchy.** The gun or hand may move inside each PNG while the AnimatedSprite2D node itself stays put. Parenting a fixed Marker2D to that node does not make it track changing pixels.

This guide is published by the maker of Sprite Socket Bench. The diagnosis and manual alternatives below do not require a purchase.

## 1. Freeze two frames before changing code

- Stop playback and select frame 0. Write down the muzzle pixel relative to the top-left of the original PNG.

- Repeat for a visibly different walking frame, keeping the node transforms unchanged.

- If the point changes, you need per-frame attachment data or an animated marker. If it does not change, inspect the origin, hierarchy and transform instead.

For an original 24×24 PNG, suppose the muzzle is (20,10) in frame 0 and (19,9) in frame 1. With a centered, unflipped sprite and zero offset, these become local positions (8,-2) and (7,-3). A fixed (8,-2) marker will miss by one pixel on the second frame. At 4× display zoom, that one source pixel looks four screen pixels wide.

## 2. Choose the smallest workflow that fits

- **Situation** — Practical approach

- **Attachment pixel never changes** — Use a fixed child Marker2D or Node2D.

- **Only a few frames or points** — Record offsets manually and look up the point for the current frame.

- **You already drive frame changes with AnimationPlayer** — Keep marker-position tracks in that same timeline; avoid adding an independent timer just for synchronization.

- **Many PNG frames need manual marking and coordinate review** — A per-frame point editor can make the authoring and export workflow easier.

A lookup must use the current animation frame, not an independently counted physics tick. An exported point records a position; it does not decide when a weapon fires or how a projectile behaves.

## 3. Diagnose the pattern of the error

- **Symptom** — Check first

- **Correct at idle, wrong on certain walk frames** — Per-frame points and animation-frame ordering. Freeze each frame individually.

- **Roughly half a frame off on every frame** — Top-left image coordinates versus centered sprite-local coordinates.

- **Correct before enabling flip_h, wrong afterwards** — Sprite drawing flips and child-node transforms are different operations. Do not assume a child automatically mirrors a stored point.

- **Correct JSON before aligned-sheet export, wrong afterwards** — That JSON describes original frames. New cell padding and alignment change the pixel origin.

- **One frame works, the next uses the wrong point** — Frame count, ordering and dimensions match the exported originals. Check skipped/reordered import frames.

- **Half-pixel appearance** — Odd source dimensions can yield fractional centered coordinates. Do not round blindly without checking the art and intended alignment.

## 4. Verify with a four-frame test

Choose four original PNGs with visibly different hand or muzzle positions. Mark each point, step through the animation, and compare the point against the same source pixel. Save the editable project. Export the coordinate JSON separately. In the engine, stop at each frame and check the attachment before enabling playback. This separates bad point data from playback synchronization.

If all four frames are correct independently but playback drifts, inspect which event updates the attachment and which frame it reads. If every paused frame is wrong, fix coordinates and transforms first.

## Where Sprite Socket Bench fits

[Sprite Socket Bench](https://knysgwr.itch.io/sprite-socket-bench) is an offline PNG attachment-point editor: click named hand, weapon, muzzle or foot pixels per frame, preview coordinate markers, and export JSON/CSV. It does not render weapons or generate art.

**The free demo** supports 4 frames, 12 sockets, playback, JSON/CSV export and image-embedded editable saves. **The US$5 full edition** supports 128 frames and adds aligned PNG output and a minimal Godot reader. [Purchase link](https://knysgwr.itch.io/sprite-socket-bench/purchase). Try your own four frames before buying; for a tiny project, manual points may be enough.

The included reader was tested in Godot 4.3 and expects one centered, unflipped AnimatedSprite2D animation, zero offset, matching original frame order/dimensions and a direct child Node2D. It positions attachments only. Flip handling, rotation, multiple clips and projectile logic require project-specific work; the table above does not claim those features were added to the product.

Use **Save project** to preserve artwork for editing (up to 64 MB). Coordinate-only JSON and CSV cannot restore PNG images. Aligned PNG export is limited to 16 megapixels and 16384 pixels per side.

## References and next steps

- [Godot 4.3 AnimatedSprite2D reference](https://docs.godotengine.org/en/4.3/classes/class_animatedsprite2d.html): centered/offset/flip properties and the frame_changed signal.

- [Godot community discussion of named per-frame tracking points](https://forum.godotengine.org/t/feature-proposal-dynamic-tracking-points-on-animatedsprite2d/131985): a concrete example of the authoring need, not an endorsement of this tool.

- [Step-by-step export-to-Godot workflow](https://knysgwr.itch.io/sprite-socket-bench/devlog/1703095/from-png-hand-positions-to-a-weapon-attachment-in-godot-4).

- [Version 1.0.1 fixes and public JSON format](https://knysgwr.itch.io/sprite-socket-bench/devlog/1712358/sprite-socket-bench-101-demo-fix-safer-saves-and-godot-json-format).

Developed and written with AI assistance. No generative model runs inside the tool. This article describes an authoring workflow and diagnostic reasoning; it makes no claims of customer sales or independent endorsement.
