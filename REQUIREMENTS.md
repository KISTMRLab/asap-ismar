# Requirements and provenance — ISMAR adjunct variant

## Paper-supported facts

Only the ISMAR abstract and public publication metadata were available for this variant. They state that a Final Draft screenplay is parsed into action, character, and dialogue paragraphs; learned, data-driven, and rule-based approaches generate physical motions and co-speech gestures; users view a 3D previz and capture played scenes into a storyboard. The later full journal paper was read only as shared-architecture context.

## Public implementation requirements

This repository parses `.fdx` XML and a structured-text fallback, produces a playback timeline, renders a schematic browser previz, and creates a storyboard from representative playback events. It intentionally stays within the early capture workflow rather than exposing the later journal's VR/360 multi-output scope.

## Explicit assumptions and substitutions

This is an independent educational reimplementation. Parenthetical emotion, gaze targeting, prop anchors, detailed action parsing, and the TF-IDF resolver are assumptions informed by the later journal architecture, rather than claims about the five-page ISMAR implementation. Durations, stage coordinates, SVG actors, and browser rendering are engineering choices. No Unity renderer, trained model, mocap, commercial TTS, 3D asset, institute code, or paper dataset is reproduced.

## Interactive implementation

The local demo compiles the actual parser/resolver output into an original procedural Three.js stage. It supports text/FDX upload, editable character/prop/action catalogs, timeline scrubbing, dialogue playback, PNG storyboard capture and timeline/storyboard export. Recompilation resets the stage. The lexical example requires no weights; semantic mode uses independently configurable local gesture/action encoders. Model files, motion libraries and vendor downloads remain outside Git. The journal's GestureCLR pose-matching lineage is documented as a research dependency; this compact renderer uses authored poses rather than claiming recovered motion capture. Early ASAP variants expose a subset of this component implementation and do not claim the later journal evaluation. Optional Kokoro and faster-whisper adapters replace browser speech/typed input; mouth motion is an approximate envelope, not aligned visemes.

## Bundled fictional avatar substitution

Two newly generated fictional CC0 humanoids replace the original avatar assets in the browser demo. They provide a 53-bone rig and named ARKit/viseme targets. Motion retargeting adapts source joints to their bind pose; speaking envelopes approximate mouth motion rather than phoneme alignment. The optional recorded BEAT companion inspects public motion, face and audio files prepared locally, independently of the paper's learned algorithm. No dataset recordings or trained weights are bundled.
