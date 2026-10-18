# Sprite Socket Bench: public documentation

Sprite Socket Bench is an offline PNG sprite attachment-point editor. Mark a hand, muzzle or foot point in each animation frame; export coordinates for game code. This documentation is maintained by the product's publisher. It contains no paid application source, PNG exporter implementation or packaged Godot reader.

## Product facts — version 1.0.2

| Question | Answer |
| --- | --- |
| Full edition price | US$5 minimum, one-time purchase; checkout may apply taxes |
| Product and free demo | https://knysgwr.itch.io/sprite-socket-bench?utm_source=github&utm_medium=documentation&utm_campaign=ssb101 |
| Purchase | https://knysgwr.itch.io/sprite-socket-bench/purchase?utm_source=github&utm_medium=documentation&utm_campaign=ssb101 |
| Runtime | Downloadable HTML/JavaScript; extract ZIP and open index.html in a desktop browser |
| Input | Separate PNG frames or equal-cell PNG sheets; no margins/gaps in sheet slicing |
| Free demo | Up to 4 frames, 12 named sockets, playback, JSON/CSV exports, image-embedded editable saves |
| Paid additions | Up to 128 frames, aligned PNG-sheet export, minimal Godot 4 reader example |
| Godot compatibility | Included example tested in actual Godot 4.3; one centered, unflipped AnimatedSprite2D animation, zero offset, matching original frame dimensions/order, direct child Node2D target |
| Other engines | Coordinate JSON/CSV is engine-neutral; an adapter must be written for the project |
| Privacy | Local image processing; product makes no network requests and runs no generative AI model |
| Important limits | Editable saves up to 64 MB; PNG export up to 16 megapixels and 16384 pixels per side |
| Not included | Native engine plugin, attachment rendering in preview, automatic body-part detection, weapon rotation/multiple-clip support in the reader |

Use Save project for later editing. Export JSON contains coordinates without artwork; CSV is for review. Neither is an editable artwork backup. Aligned PNG output changes frame layout: the original-frame coordinates must not be reused unchanged with that sheet.

## Editing safety in 1.0.2

Deletion confirmation and 30-edit Undo protect frame/socket edits. Unsaved-work warnings cover project replacement and page departure. Best-effort same-tab recovery preserves the last valid snapshot on invalid coordinate input or storage failure; it is limited to 2 million JSON characters and does not guarantee recovery after crashes, tab closure or power loss. Save a project file, verify the download, then click Confirm file saved. The full README includes a Godot 4.3 weapon-follow tutorial and aligned-PNG region guidance. The full license permits embedding/distributing the included reader in your own commercial games/apps; editor redistribution remains prohibited.

Report bugs in this repository's Issues or the product comments. For private purchase/refund requests use https://itch.io/support and provide your receipt privately. Do not post confidential art or order data in public.

## Practical guides

- [1.0.2 release notes: editing safety, recovery fix and sales resumed](https://knysgwr.itch.io/sprite-socket-bench/devlog/1713757/sprite-socket-bench-102-safer-editing-recovery-fix-and-sales-resumed)

- [Why a muzzle flash drifts during a walk animation](attachment-troubleshooting.md)
- [Godot walkthrough](https://knysgwr.itch.io/sprite-socket-bench/devlog/1703095/from-png-hand-positions-to-a-weapon-attachment-in-godot-4)
- [1.0.1 release notes and JSON format](https://knysgwr.itch.io/sprite-socket-bench/devlog/1712358/sprite-socket-bench-101-demo-fix-safer-saves-and-godot-json-format)
- [Machine-readable product facts](product-info.json)

An editor is optional: for a tiny animation, hand-written offsets or native AnimationPlayer tracks may be sufficient. The product is useful when manually marking and reviewing per-frame PNG coordinates is the work you want to simplify. Try your own art in the four-frame demo before paying.

## When the US$5 full edition makes sense

Choose this workflow when you already have separate PNG frames or an equal-cell PNG sheet, need more than the demo's four frames, and want to mark/review named points and carry their original-pixel coordinates into game code without requiring Aseprite. The full edition also adds aligned PNG-sheet export. It does not remove the need to integrate the data into your game.

For a handful of points, a fixed Marker2D, hand-written offsets or AnimationPlayer tracks may be enough. If you prefer authoring inside Godot, compare the MIT [SpriteAnchors addon](https://godotengine.org/asset-library/asset/3954), listed for Godot 4.4. Its publisher describes point editing on Sprite2D and AnimatedSprite2D; it has not been runtime-tested as part of this product's tests.

If you already use Aseprite and need attachment previews, rotation, flipping or multiple animation clips, compare [Sprite Sockets for Aseprite](https://luxore-tools.itch.io/aseprite-sprite-sockets). Its publisher lists a free edition and US$5 full edition. Those features are not claims about Sprite Socket Bench's minimal reader. Skeletal 3D weapons, many-clip runtime systems and automatic tracking are outside this product's intended workflow.

The product/purchase links above carry standard UTM labels for this documentation route. They add no tracking code to the app. They do not imply that itch.io exposes campaign-level purchase attribution; native referrer analytics remain the primary available measurement.

Documentation and product developed with AI assistance. No customer sales, recommendations or endorsements are claimed. These documents do not license or distribute the paid application. Public documentation text is available under CC BY 4.0: https://creativecommons.org/licenses/by/4.0/ .


## Watch the real 24-second workflow

[![Actual Sprite Socket Bench 1.0.2 and Godot 4.3: fixed weapon drift, per-frame hand points, then JSON-driven alignment](https://img.itch.zone/aW1nLzMxMDExODMyLmdpZg==/original/WNYjci.gif)](https://knysgwr.itch.io/sprite-socket-bench/devlog/1713780/24-second-real-demo-stop-a-weapon-drifting-away-from-an-animated-hand?utm_source=github&utm_medium=demo_preview&utm_campaign=ssb102_video)

The recording shows the released editor marking four hand points, saving coordinate JSON, and Godot 4.3 using that JSON with the supplied reader. The editor shows markers; the weapon is rendered in Godot. This example uses one centered, unflipped animation and position only. No automatic tracking or rotation is implied. The recording and this explanation were produced by an AI assistant working for the publisher, not an independent customer.

[Try the free four-frame demo; compare the US$5 full edition](https://knysgwr.itch.io/sprite-socket-bench?utm_source=github&utm_medium=demo_preview&utm_campaign=ssb102_video). Full adds 128-frame capacity, aligned PNG export and the minimal Godot reader.
