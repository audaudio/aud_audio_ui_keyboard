# aud_audio_ui_keyboard

English | [Deutsch](README.de.md)

[![CI](https://github.com/audaudio/aud_audio_ui_keyboard/actions/workflows/quick_check.yaml/badge.svg)](https://github.com/audaudio/aud_audio_ui_keyboard/actions/workflows/quick_check.yaml)

Multi-touch musical keyboard widget of the Audanika Audio Engine, modeled on
AudioKit Keyboard. Pure Flutter, free of the engine; part of the Audanika
Audio Engine, planned in
[aud_audio_pm](https://github.com/audaudio/aud_audio_pm).

## Motivation

- Instruments built on the Audanika Audio Engine need a keyboard that works
  with several fingers on touch screens and with the mouse on the desktop, on
  every platform Flutter supports
- AudioKit Keyboard shows a proven, MIT-licensed model with piano, isomorphic,
  guitar and vertical layouts, latching and keys that light up from outside;
  the package ports it instead of inventing a new one
- The widget emits notes through a binding and does not depend on the engine
  (decision ui-003), so an app, a plugin editor and a test drive it alike

## Installation

The package is not published to pub.dev; add it from its git tags:

```yaml
dependencies:
  aud_audio_ui_keyboard:
    git:
      url: git@github.com:audaudio/aud_audio_ui_keyboard.git
      tag_pattern: '{{version}}'
    version: ^0.0.3
```

## Usage

The package is a placeholder: the widget follows with step S17b of the plan of
the Audanika Audio Engine (see [Status](#status)). Until then it exports
nothing but the boilerplate of the Flutter package template, so this is all
that runs:

```dart
import 'package:aud_audio_ui_keyboard/aud_audio_ui_keyboard.dart';

void main() {
  // The widget is not built yet; the package exports the boilerplate
  // Calculator of the Flutter package template until it arrives.
  print(Calculator().addOne(1));
}
```

```text
2
```

## Limitations

- No widget yet; see [Status](#status)
- The widget will not depend on the engine (decision ui-003): apps bind it
  through `aud_audio_ui_bindings`, plugin editors through their shell's
  protocol

## Documentation

- [Plan 17: Audanika Audio
  Engine](https://github.com/audaudio/aud_audio_pm/blob/main/doc/2026-Q4/tickets/2026-10-07-17-audanika-audio-engine.md),
  which plans the package as step S17b
- The decisions
  [ui-002](https://github.com/audaudio/aud_audio_pm/blob/main/doc/2026-Q4/concepts/decisions/ui-002.md)
  (the keyboard after AudioKit Keyboard) and
  [ui-003](https://github.com/audaudio/aud_audio_pm/blob/main/doc/2026-Q4/concepts/decisions/ui-003.md)
  (the engine adapters live in a binding package)
- [AudioKit Keyboard](https://github.com/AudioKit/Keyboard), the template
  (MIT)
- The guides in [`doc/guides`](doc/guides) and the blog posts in
  [`doc/blog`](doc/blog)

## Status

Before 1.0 — the API may change between minor versions. The repo holds the
boilerplate of a Flutter package and its version constant only. Step S17b
builds `Keyboard` with the five layouts of AudioKit Keyboard, a
`KeyboardModel` with multi-touch, latching and externally activated keys,
`KeyboardKey`, a `MidiMonitorKeyboard` and a `NoteBinding` into the event
inlets and the sequencer of the engine, with golden tests and a cookbook page
with the sampler. The package depends on `aud_audio` for that.

## Contributing

Tickets run through the `gg` workflow: see the [Develop
Guide](doc/guides/develop-guide.md) and the [Review
Guide](doc/guides/for-ai/ai-review-guide.md).

## License

MIT — see [LICENSE](LICENSE).
