# Requirements and provenance — ISMAR adjunct variant

## Paper-supported facts

Only the ISMAR abstract and public publication metadata were available for this variant. They state that a Final Draft screenplay is parsed into action, character, and dialogue paragraphs; learned, data-driven, and rule-based approaches generate physical motions and co-speech gestures; users view a 3D previz and capture played scenes into a storyboard. The later full journal paper was read only as shared-architecture context.

## Public implementation requirements

This repository parses `.fdx` XML and a structured-text fallback, produces a playback timeline, renders a schematic browser previz, and creates a storyboard from representative playback events. It intentionally stays within the early capture workflow rather than exposing the later journal's VR/360 multi-output scope.

## Explicit assumptions and substitutions

This is an independent educational reimplementation. Parenthetical emotion, gaze targeting, prop anchors, detailed action parsing, and the TF-IDF resolver are assumptions informed by the later journal architecture, rather than claims about the five-page ISMAR implementation. Durations, stage coordinates, SVG actors, and browser rendering are engineering choices. No Unity renderer, trained model, mocap, commercial TTS, 3D asset, institute code, or paper dataset is reproduced.
