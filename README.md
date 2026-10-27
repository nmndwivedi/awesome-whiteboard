# Awesome Whiteboard [![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

> A curated list of infinite-canvas and whiteboard software — SDKs you can embed, apps you can use, and the primitives they're built from.

Whiteboards look simple and are not. A usable one needs camera math, hit-testing, selection, undo semantics, touch and stylus handling, serialization, and export — before you draw a single pixel. This list collects the libraries that solve those problems, the apps built on them, and the primitives underneath.

**Licensing is the first thing to check.** Several popular options are *source-available* rather than open source: you can read the code, but shipping to production carries terms. Each entry below states its license plainly.

## Contents

- [Embeddable SDKs and libraries](#embeddable-sdks-and-libraries)
- [Canvas primitives](#canvas-primitives)
- [Whiteboard apps](#whiteboard-apps)
- [Self-hosted collaborative whiteboards](#self-hosted-collaborative-whiteboards)
- [Sync and collaboration](#sync-and-collaboration)
- [File formats](#file-formats)
- [Reading](#reading)

## Embeddable SDKs and libraries

Drop a drawing surface into your own application.

- [Excalidraw](https://github.com/excalidraw/excalidraw) — MIT. The hand-drawn-style whiteboard, available as an embeddable React component (`@excalidraw/excalidraw`). Mature, enormously popular, battle-tested. React-only, and the embed brings Excalidraw's own look and UX.
- [Quickdraw](https://github.com/nmndwivedi/quickdraw) — MIT. Infinite-canvas whiteboard SDK for React, React Native, and plain JS. Pressure ink, palm rejection, hand-drawn shapes, per-gesture undo, PNG export, and a diff-emitting store for sync. Zero-dependency core, no build step.
- [tldraw](https://github.com/tldraw/tldraw) — **Source-available under the tldraw license, not open source.** An excellent, richly extensible React canvas SDK with the best-in-class shape and tool plugin system. Since SDK 4.0 (September 2025) production use requires a license key: a 100-day trial, a free non-commercial hobby license with a required watermark, or a commercial license via sales. v1 was MIT.
- [React Flow](https://github.com/xyflow/xyflow) — MIT. Node-based editors and diagrams for React (and Svelte, via Svelte Flow). Not freehand drawing, but the standard choice for node graphs on an infinite canvas.
- [Konva](https://github.com/konvajs/konva) — MIT. Declarative 2D canvas with React, Vue, and Svelte bindings. A canvas framework rather than a whiteboard — you build the tools, store, undo, and serialization yourself.
- [Fabric.js](https://github.com/fabricjs/fabric.js) — MIT. Long-standing canvas object model with selection, transformation, and SVG import/export. Same tradeoff as Konva: powerful primitives, whiteboard not included.
- [Paper.js](https://github.com/paperjs/paper.js) — MIT. Vector graphics scripting framework with an excellent geometry and path-boolean toolkit.
- [Pixi.js](https://github.com/pixijs/pixijs) — MIT. WebGL renderer. Reach for it when element counts get into the tens of thousands and 2D canvas stops keeping up.

## Canvas primitives

The building blocks — useful when you're writing your own surface.

- [perfect-freehand](https://github.com/steveruizok/perfect-freehand) — MIT. Turns pointer input into pressure-sensitive stroke outlines. The reference implementation for good-feeling digital ink.
- [Rough.js](https://github.com/rough-stuff/rough) — MIT. Renders shapes with a hand-drawn, sketchy appearance. The look Excalidraw made famous.
- [Yjs](https://github.com/yjs/yjs) — MIT. CRDT framework; the most common way to add real-time collaboration to a canvas.
- [react-native-skia](https://github.com/Shopify/react-native-skia) — MIT. Skia bindings for React Native. A superb low-level GPU drawing API, several months of work short of a whiteboard.
- [signature_pad](https://github.com/szimek/signature_pad) — MIT. Smooth signature capture on a fixed canvas. No camera, no selection — exactly right when that's all you need.

## Whiteboard apps

- [Excalidraw](https://excalidraw.com) — MIT. Free, no signup, end-to-end-encrypted collaboration, works offline.
- [tldraw](https://tldraw.com) — the hosted app is free to use.
- [Quickdraw](https://app.tryquickdraw.com) — MIT. Free, no signup, saves locally.
- [Obsidian Canvas](https://obsidian.md/canvas) — proprietary app; the [`.canvas` file format](https://jsoncanvas.org) it introduced is open (MIT).
- [Miro](https://miro.com), [FigJam](https://figma.com/figjam), [Microsoft Whiteboard](https://www.microsoft.com/microsoft-365/microsoft-whiteboard/digital-whiteboard-app) — proprietary, team-oriented, free tiers available. Google's Jamboard was discontinued on December 31, 2024.
- [Paceflow Whiteboard](https://www.paceflow.io/whiteboard) — Free hosted web app. A no-signup collaborative whiteboard for quick sketches and brainstorming.

## Self-hosted collaborative whiteboards

Run your own server.

- [Excalidraw + excalidraw-room](https://github.com/excalidraw/excalidraw-room) — MIT. The collaboration backend for self-hosted Excalidraw.
- [WBO](https://github.com/lovasoa/whitebophir) — AGPL-3.0. Long-running open-source collaborative whiteboard, easy to self-host.
- [Whitebird](https://github.com/wbrijesh/whitebird) — open-source web-based collaborative whiteboard.
- [Drawpile](https://github.com/drawpile/Drawpile) — GPL-3.0. Collaborative *painting* rather than diagramming, with a mature session server.
- [OpenBoard](https://github.com/OpenBoard-org/OpenBoard) — GPL-3.0. Interactive whiteboard for schools and universities.

## Sync and collaboration

- [Yjs](https://github.com/yjs/yjs) — MIT. CRDTs with bindings for most editors and a healthy provider ecosystem.
- [Automerge](https://github.com/automerge/automerge) — MIT. CRDT library with a strong focus on local-first software.
- [Liveblocks](https://liveblocks.io) — proprietary, free tier. Hosted presence and storage; commonly paired with canvas SDKs.
- [PartyKit](https://github.com/partykit/partykit) — MIT. Edge-deployed WebSocket servers, a small amount of glue away from multiplayer canvas.

## File formats

- [JSON Canvas](https://jsoncanvas.org) — MIT. An open file format for infinite-canvas data, originating in Obsidian Canvas.
- [SVG](https://www.w3.org/TR/SVG2/) — the lowest-common-denominator export target; every tool above writes it.

## Reading

- [Why is Excalidraw so good?](https://news.ycombinator.com/item?id=29109995) — Hacker News discussion of what makes a whiteboard feel right.
- [Reflections on Excalidraw](https://blog.vjeux.com/2020/uncategorized/reflections-on-excalidraw.html) — Christopher Chedeau on building and growing it.
- [Perfect Freehand: the algorithm](https://github.com/steveruizok/perfect-freehand#readme) — how pressure-sensitive strokes are actually computed.
- [Coordinate systems and camera math for infinite canvases](https://tryquickdraw.com/blog/infinite-canvas-camera-math/) — screen space, page space, and zoom-to-cursor.

## Contributing

Contributions welcome — see [CONTRIBUTING.md](CONTRIBUTING.md). The bar: the project should be maintained, genuinely useful, and its license stated accurately. Corrections to license descriptions are especially welcome; these change over time and this list should be right rather than convenient.

## License

[CC0 1.0](LICENSE) — public domain.
