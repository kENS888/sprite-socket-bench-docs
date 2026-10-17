# Sprite Socket Bench: public documentation

Sprite Socket Bench is an offline PNG sprite attachment-point editor. Mark a hand, muzzle or foot point in each animation frame; export coordinates for game code. This documentation is maintained by the product's publisher. It contains no paid application source, PNG exporter implementation or packaged Godot reader.

## Product facts — version 1.0.1

| Question | Answer |
| --- | --- |
| Full edition price | US$5 minimum, one-time purchase; checkout may apply taxes |
| Product and free demo | https://knysgwr.itch.io/sprite-socket-bench |
| Purchase | https://knysgwr.itch.io/sprite-socket-bench/purchase |
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

## Practical guides

- [Why a muzzle flash drifts during a walk animation](attachment-troubleshooting.md)
- [Godot walkthrough](https://knysgwr.itch.io/sprite-socket-bench/devlog/1703095/from-png-hand-positions-to-a-weapon-attachment-in-godot-4)
- [1.0.1 release notes and JSON format](https://knysgwr.itch.io/sprite-socket-bench/devlog/1712358/sprite-socket-bench-101-demo-fix-safer-saves-and-godot-json-format)
- [Machine-readable product facts](product-info.json)

An editor is optional: for a tiny animation, hand-written offsets or native AnimationPlayer tracks may be sufficient. The product is useful when manually marking and reviewing per-frame PNG coordinates is the work you want to simplify. Try your own art in the four-frame demo before paying.

Documentation and product developed with AI assistance. No customer sales, recommendations or endorsements are claimed. These documents do not license or distribute the paid application. Public documentation text is available under CC BY 4.0: https://creativecommons.org/licenses/by/4.0/ .
