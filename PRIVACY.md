# Privacy

NexoLLM is built so that what you write never leaves your Mac. This page says exactly what it reads, what it
keeps and where.

## Network

None. NexoLLM opens no network connections: no analytics, no crash reporting, no update checks, no account.
The language model runs on your Mac's GPU.

## What it reads

| Source | When | Kept |
|---|---|---|
| Text around the cursor in the focused field | While you type, in apps where NexoLLM is active | In memory while you write |
| Short fields of the same window (subject, recipients, titles) | When you start writing in a field | In memory for that field |
| The window on screen | Only if Screen Recording is allowed: when you press `⌃⌥S`, or automatically at a few moments if you chose Smart | Turned into text on the Mac, the image is dropped immediately. The text is kept in memory only |
| The clipboard | If "Use clipboard" is on | In memory |

Password fields and apps that turn on secure input are never read.

## What it stores

Everything lives in `~/Library/Application Support/NexoLLM`, a folder readable only by your macOS user.

| File | Content | Protection |
|---|---|---|
| `history.bin` | What you wrote, used to learn your style (only in apps where recording is on) | AES-256-GCM, key in your Keychain |
| `memory.bin` | Short notes about recent topics, which fade over days | AES-256-GCM, same key |
| `stats.json` | Word counts per day and per app | Owner-only file |
| `Models/` | The language model you installed | |

You can turn recording off for any app, clear the history and the memory in Settings, under Mind. Deleting
the folder removes everything.

## Logs

`~/Library/Logs/NexoLLM.log` holds technical events (model loaded, permissions). Detailed logging, which can
include short text fragments, is off unless you turn it on in Settings. The file is readable only by you.

## Questions

Open an issue at https://github.com/NexoLLM/NexoLLM/issues
