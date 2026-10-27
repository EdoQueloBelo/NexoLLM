# Changelog

Every release of NexoLLM, newest first. Versions follow [Semantic Versioning](https://semver.org).
NexoLLM is in beta: until 1.0 a minor version (0.x.0) can change behavior, a patch (0.x.y) only fixes things.
The build number in parentheses grows with every commit.

## [0.2.0] - 2026-10-27

The first release under the NexoLLM name.

### Suggestions
Ghost text now finds the caret reliably in apps that report a wrong box for an empty selection (Safari,
Mail, Electron apps): every position is cross-checked with the character before the caret and with the
field, so the suggestion no longer jumps to a corner of the window.

A new suggestion appears with a tiny 120 ms fade and a 2 pt drift. Text that shrinks while you type or
accept it doesn't animate again. Reduce Motion turns the effect off.

### Interface
The floating button has a fixed home: inside the right end of a one-line field, in the bottom-right
corner of a larger one (top-right while you're typing down there). It hides on whole-page canvases and
never floats away from the field.

The menu bar and button menus are the same short menu: status, the app in front, a Pause submenu,
Read the Screen Now, Settings.

Settings pages switch with a short fade, and the tab pill slides to the selected section.

### Privacy and security
The data folder is readable only by your user (0700, files 0600), stored files are size-checked before
they're read, and inserted text is stripped of control and bidi-override characters.
The encryption key is read once per launch and kept in memory.

### Distribution
Builds are compiled without debug info, stripped and signed with the hardened runtime.
`./build.sh dist` produces the DMG and ZIP for GitHub Releases with their SHA-256 checksums.
llama.cpp downloads are verified against a pinned checksum.

### Fixed
CI failed on Swift 6.0 (`weak let` in ScreenContext).

## [0.1.0] - 2026-10-26

First preview.

Completions in any app, at the end of a line or inside text, accepted word by word (`Tab`) or whole.
Punctuation always takes its own `Tab`, so you decide where a sentence stops. Smart Tab keeps indenting
after list markers. Autocorrect bubbles, emoji (`:word`), alternatives and synonyms on demand.

Context from the other fields of the window (subject, recipients, titles) with exact facts copied from
them, optional screen reading (smart or only on `⌃⌥S`), an episodic memory of recent topics and a writing
style profile learned per app.

Works with Pages, Keynote and Numbers, adapts the ghost text color to the page under the cursor, uses 0%
CPU when idle and switches to a smaller model on battery.
