<div align="center">

<img src="assets/icon.png" width="112" alt="NexoLLM icon">

# NexoLLM

**Your Mac finishes your sentences. Nothing leaves it.**

<p>
  <img src="https://img.shields.io/badge/macOS-14%2B-111111?style=flat-square&logo=apple&logoColor=white" alt="macOS 14+">
  <img src="https://img.shields.io/badge/Apple%20Silicon-native-5A6BF2?style=flat-square" alt="Apple Silicon">
  <img src="https://img.shields.io/badge/runs-100%25%20offline-2FB37F?style=flat-square" alt="Offline">
  <img src="https://img.shields.io/github/v/release/NexoLLM/NexoLLM?include_prereleases&style=flat-square&label=beta&color=F29E33" alt="Latest beta">
  <img src="https://img.shields.io/github/downloads/NexoLLM/NexoLLM/total?style=flat-square&color=5A6BF2" alt="Downloads">
</p>

[Download](https://github.com/NexoLLM/NexoLLM/releases/latest) · [Changelog](CHANGELOG.md) · [Privacy](PRIVACY.md) · [Report a bug](https://github.com/NexoLLM/NexoLLM/issues/new/choose)

English | [Italiano](README-IT.md)

<br>

<img src="assets/overview.png" width="820" alt="NexoLLM settings window">

</div>

<br>

## What it is

NexoLLM is a writing engine that lives in your menu bar. While you type in Mail, Messages, WhatsApp, Notes,
Pages, Safari, Slack or Obsidian, it suggests how the sentence goes on, in grey, right after the cursor.
Press `Tab` to take the next word, keep typing to ignore it.

The language model runs on the Apple Silicon GPU of your Mac. There is no account, no subscription and no
server: your text, your history and whatever the app learns about you stay on your disk, encrypted.

It pays attention to the moment. Write "dal 19 al 23" in the subject of an email and start the same phrase
in the body: NexoLLM completes it with 23, because it read the subject, not because it guessed.

<br>

## How it works

Every suggestion goes through the same four steps, in a few tenths of a second.

<table>
  <tr>
    <td width="70" align="center"><b>01</b></td>
    <td><b>Reading the moment</b><br>The text around the cursor and the short fields next to it (subject,
    recipients, the title of a note), read through macOS Accessibility. If you want, also the window
    itself: by pressing <code>⌃⌥S</code>, or automatically only when it helps. Screens are turned into text on
    device and never saved.</td>
  </tr>
  <tr>
    <td align="center"><b>02</b></td>
    <td><b>Remembering you</b><br>How you write in each app (formal in Mail, short in chats), the expressions
    you use, how you open and close a message, and a small memory of the topics of the last few days that
    fades by itself.</td>
  </tr>
  <tr>
    <td align="center"><b>03</b></td>
    <td><b>Thinking on device</b><br>Gemma 4 (E4B, or E2B on battery) through llama.cpp on Metal. The prompt
    cache is reused while you type, numbers and names from the context are copied exactly, and when the
    model isn't sure it simply says less.</td>
  </tr>
  <tr>
    <td align="center"><b>04</b></td>
    <td><b>Writing only what you accept</b><br>One <code>Tab</code> per word. Punctuation needs its own press, so a
    comma you didn't want never lands in your text. The grey adapts to the page under the cursor, so it
    stays readable on white web pages in dark mode.</td>
  </tr>
</table>

<br>

## See it

<div align="center">
<img src="assets/overlays.png" width="560" alt="Suggestion, correction, emoji and alternatives">
</div>

<br>

## Install

| | |
|---|---|
| **1. Download** | Get `NexoLLM-<version>.dmg` from [Releases](https://github.com/NexoLLM/NexoLLM/releases/latest) and drag the app to Applications. |
| **2. First launch** | The beta isn't notarized yet. Right click the app, choose Open, then confirm. You only do this once. |
| **3. Permissions** | Accessibility is required to read and insert text. Screen Recording is optional and only used for screen context. |
| **4. Model** | Put a Gemma 4 GGUF model (E4B or E2B, Q4_K_M) in `~/Library/Application Support/NexoLLM/Models`. The Overview page tells you if something is missing. |

Requirements: macOS 14 or later on Apple Silicon, 8 GB of memory (16 GB recommended for E4B).

<br>

## Keys

| Action | Key |
|---|---|
| Take the next word (punctuation is its own press) | `Tab` |
| Take the whole suggestion | the key above `Tab` |
| Dismiss | `Esc` |
| Ask for a suggestion now | `⌃` + the key above `Tab` |
| Read the screen now | `⌃⌥S` |
| Alternatives, or synonyms of the selected word | `⌥Tab` |
| Pause in the current app | `⌃⌥⌘` + the key above `Tab` |

Everything can be changed in Settings, under Input.

<br>

## Privacy

NexoLLM makes no network connections. The typing history and the memory are encrypted with AES-256-GCM
using a key kept in your Keychain, inside a folder only your user can read. Password fields and secure
input are never read. The details are in [PRIVACY.md](PRIVACY.md).

<br>

## Status

NexoLLM is a beta and still far from 1.0. Things will change between versions, and your bug reports
shape what comes next: tell me what you were typing and in which app, and I'll look at it.

<br>

## License

NexoLLM is free to use and proprietary. The source code isn't published and the app may not be
redistributed or modified. See [LICENSE](LICENSE). It includes llama.cpp, released under the MIT license.

<div align="center">
<br>
Made by <b>EdevS</b>
</div>
