# aud_audio_ui_keyboard

[English](README.md) | Deutsch

[![CI](https://github.com/audaudio/aud_audio_ui_keyboard/actions/workflows/quick_check.yaml/badge.svg)](https://github.com/audaudio/aud_audio_ui_keyboard/actions/workflows/quick_check.yaml)

Multi-Touch-Klaviatur-Widget der Audanika Audio Engine, nach dem Vorbild von
AudioKit Keyboard. Reines Flutter, frei von der Engine; Teil der Audanika
Audio Engine, geplant in
[aud_audio_pm](https://github.com/audaudio/aud_audio_pm).

## Motivation

- Instrumente auf der Audanika Audio Engine brauchen eine Klaviatur, die mit
  mehreren Fingern auf Touchscreens und mit der Maus auf dem Desktop
  funktioniert, auf jeder Plattform, die Flutter unterstützt
- AudioKit Keyboard zeigt ein bewährtes, MIT-lizenziertes Modell mit Klavier-,
  isomorphem, Gitarren- und vertikalem Layout, Haltefunktion und Tasten, die
  von außen aufleuchten; das Paket portiert es, statt Neues zu erfinden
- Das Widget gibt Noten über ein Binding aus und hängt nicht von der Engine ab
  (Entscheidung ui-003), sodass eine App, ein Plugin-Editor und ein Test es
  gleichermaßen steuern

## Installation

Das Paket ist nicht auf pub.dev veröffentlicht; binde es über seine Git-Tags
ein:

```yaml
dependencies:
  aud_audio_ui_keyboard:
    git:
      url: git@github.com:audaudio/aud_audio_ui_keyboard.git
      tag_pattern: '{{version}}'
    version: ^0.0.3
```

## Verwendung

Das Paket ist ein Platzhalter: Das Widget folgt mit Schritt S17b des Plans der
Audanika Audio Engine (siehe [Stand](#stand)). Bis dahin exportiert es nur den
Boilerplate-Code der Flutter-Paketvorlage, mehr läuft also nicht:

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

## Grenzen

- Noch kein Widget; siehe [Stand](#stand)
- Das Widget wird nicht von der Engine abhängen (Entscheidung ui-003): Apps
  binden es über `aud_audio_ui_bindings`, Plugin-Editoren über das Protokoll
  ihrer Shell

## Dokumentation

- [Plan 17: Audanika Audio
  Engine](https://github.com/audaudio/aud_audio_pm/blob/main/doc/2026-Q4/tickets/2026-10-07-17-audanika-audio-engine.md),
  der das Paket als Schritt S17b plant
- Die Entscheidungen
  [ui-002](https://github.com/audaudio/aud_audio_pm/blob/main/doc/2026-Q4/concepts/decisions/ui-002.md)
  (die Klaviatur nach AudioKit Keyboard) und
  [ui-003](https://github.com/audaudio/aud_audio_pm/blob/main/doc/2026-Q4/concepts/decisions/ui-003.md)
  (die Engine-Adapter liegen in einem Binding-Paket)
- [AudioKit Keyboard](https://github.com/AudioKit/Keyboard), die Vorlage (MIT)
- Die Guides in [`doc/guides`](doc/guides) und die Blog-Posts in
  [`doc/blog`](doc/blog)

## Stand

Vor 1.0 — die API kann sich zwischen Minor-Versionen ändern. Das Repo enthält
nur den Boilerplate-Code eines Flutter-Pakets und seine Versionskonstante.
Schritt S17b baut `Keyboard` mit den fünf Layouts von AudioKit Keyboard, ein
`KeyboardModel` mit Multi-Touch, Haltefunktion und von außen aktivierten
Tasten, `KeyboardKey`, ein `MidiMonitorKeyboard` und ein `NoteBinding` in die
Event-Eingänge und den Sequencer der Engine, mit Golden-Tests und einer
Cookbook-Seite mit dem Sampler. Dafür hängt das Paket von `aud_audio` ab.

## Mitwirken

Tickets laufen durch den `gg`-Workflow: siehe den [Develop
Guide](doc/guides/develop-guide.md) und den [Review
Guide](doc/guides/for-ai/ai-review-guide.md).

## Lizenz

MIT — siehe [LICENSE](LICENSE).
