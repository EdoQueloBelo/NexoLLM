# Changelog

Every release of NexoLLM, newest first. Versions follow [Semantic Versioning](https://semver.org).
NexoLLM is in beta: until 1.0 a minor version (0.x.0) can change behavior, a patch (0.x.y) only fixes things.
The build number in parentheses grows with every commit.

## [0.3.0] - 2026-10-30

### Better suggestions
Suggestions now start from the half-typed word instead of after it. Before, the model could only add
letters to what you had typed, so the obvious word was often out of reach and a rare, longer one came up
instead. The word you're typing also keeps its capitalization.

Spelling corrections follow the language of the sentence, use the sentence for context and only fix near
misses: one or two letters off, swapped letters or a missing accent. Names, acronyms and words you use
often are never corrected. Suggestions are no longer held back while a word is only half typed.

### Alternatives
⌥Tab lists other words for the one you're typing, or for the next one, at any point. Press it again to
switch to other ways of finishing the sentence. With a word selected it lists synonyms.

### Models
NexoLLM detects your Mac's chip and memory and recommends a model for when you're plugged in and one for
battery. Models can be downloaded from Settings (verified with SHA-256), imported from a GGUF file or
deleted to free the space. Bring your own key for OpenAI, Anthropic, Google Gemini or any
OpenAI-compatible service to use a cloud model instead; keys are stored in the Keychain.

### Interface
The floating button is gone. The menu bar icon shows the status, ⌃⌥M opens the menu at the cursor and a
short note confirms when you pause or resume. Setting descriptions moved into an ⓘ popover, texts are
shorter, and the app is English throughout, numbers and dates included. Light and dark appearance can
be chosen in Behavior. The About page has links to GitHub, bug reports and release notes. Saved texts
can be browsed, searched and deleted one by one, with their real size on disk.

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
