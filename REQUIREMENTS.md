# Requirements and provenance — ISMAR adjunct variant

## Paper-supported facts

Only the ISMAR abstract and public publication metadata were available for this variant. They state that a Final Draft screenplay is parsed into action, character, and dialogue paragraphs; learned, data-driven, and rule-based approaches generate physical motions and co-speech gestures; users view a 3D previz and capture played scenes into a storyboard. The later full journal paper was read only as shared-architecture context.

## Public implementation requirements

This repository parses `.fdx` XML and a structured-text fallback, produces a playback timeline, renders a self-contained schematic HTML previz and a 3D browser previz, and creates a storyboard from representative playback events. The ISMAR paper's own scope is the early capture workflow; the browser demo's journal-derived outputs are labelled as web-demo extras below.

## Explicit assumptions and substitutions

This is an independent educational reimplementation. The following are assumptions informed by the later journal architecture, rather than claims about the five-page ISMAR implementation: seven-emotion parenthetical scoring with three levels and manual overrides; gaze targeting; prop instances with stand points; subject extraction; plausible action–object–position matching with rejection; and the stemmed TF-IDF and optional local Sentence-BERT matching. Durations, stage coordinates, SVG actors, and browser rendering are engineering choices. No Unity renderer, trained model, mocap, commercial TTS, 3D asset, institute code, or paper dataset is reproduced.

## Interactive implementation

The local demo compiles the actual parser/resolver output into a Three.js stage with bundled fictional CC0 avatars. It supports text/FDX upload, editable character/prop/action catalogs, timeline scrubbing, dialogue playback, PNG storyboard capture and timeline/storyboard export. Recompilation resets the stage. The lexical example requires no weights; semantic mode uses independently configurable local gesture/action encoders. The small official BEAT sample and fitted retrieval artifacts stay in ignored local outputs; pinned renderer modules are downloaded into ignored vendor storage. The journal's GestureCLR pose-matching lineage is documented as a research dependency; the browser uses locally prepared BEAT body-motion clips for dialogue while keeping authored action poses; it does not claim to reproduce institute motion capture or GestureCLR weights. Early ASAP variants expose a subset of this component implementation and do not claim the later journal evaluation. Optional Kokoro and faster-whisper adapters replace browser speech/typed input; mouth shapes come from the shared rule-based text-to-viseme track, not forced phoneme alignment.

Web-demo extras carried over from the later journal paper (owner-approved Tier D scope; not described by the ISMAR paper): multi-camera presets with an auto-cut camera track derived from the compiled events; WebM recording of the stage canvas with MediaRecorder, which includes local Kokoro audio through WebAudio but cannot capture browser `speechSynthesis`; and an immersive WebXR VR view that reports when WebXR or a headset is unavailable. Props animate their action `effect` (light, glow, curtains, door). Walking follows a grid A* path (octile heuristic, no corner cutting) around inflated prop footprints. The reaching hand is placed with two-bone IK at the prop's interaction point, and sitting uses the prop's `seat_height`. Storyboard frames have editable descriptions exported as HTML or JSON. The camera shot rules, A* grid, body radius, effect timing and procedural props and room are implementation assumptions, not paper details.

Not reproduced in the web demo: 360-degree video, because spherical-video metadata must be injected outside the browser even when an equirectangular frame can be rendered; and casting or environments beyond the two bundled fictional CC0 avatars and a basic procedural room authored in code.

## Bundled fictional avatar substitution

Two newly generated fictional CC0 humanoids replace the original avatar assets in the browser demo. They provide a 53-bone rig and named ARKit/viseme targets. Motion retargeting adapts source joints to their bind pose; mouth shapes follow a rule-based text-to-phoneme-to-viseme track timed to speech playback, an approximation rather than forced phoneme alignment. The optional recorded BEAT companion inspects public motion, face and audio files prepared locally, independently of the paper's learned algorithm. No dataset recordings or trained weights are bundled.

## Local recorded co-speech integration

The browser application retrieves prepared BEAT body-motion clips with `automatic` mode: a current public-demo adapter; the ISMAR paper does not identify this dependency. The first `python scripts/start_demo.py` run fetches a small official BVH/TextGrid sample, constructs a nine-clip bank, and fits the local retrieval artifact under ignored `outputs/beat-library/`. Install `scripts/requirements-demo.txt` first. Preparation code and method dependencies are vendored in this repository; no sibling clone, original institute library, full dataset, or pretrained weights are bundled. The screenplay parser, action resolver, scene timeline, and storyboard capture remain this application's core. The separate recorded-motion companion remains available for local motion/face/audio inspection.
