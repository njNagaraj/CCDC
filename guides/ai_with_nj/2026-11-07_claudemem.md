# claude-mem: give Claude Code a memory (setup guide, @ai_with_nj)

claude-mem is a free, open-source (Apache-2.0) plugin. In its own words: "Your coding agent forgets everything between sessions. Claude-Mem remembers for it." After install, your second session in a project opens with memory from the first.

Official repo: https://github.com/thedotmack/claude-mem (README read 7 Nov 2026, v15.12.0). Docs: https://docs.claude-mem.ai

## Install (Windows, Mac, Linux)

You need Node.js (for npx) and Claude Code.

```bash
npx claude-mem install
```

Or from inside Claude Code:

```bash
/plugin marketplace add thedotmack/claude-mem
/plugin install claude-mem
```

Then restart Claude Code.

Do not use `npm install -g claude-mem`. That installs the SDK library only and does not set up the plugin.

## Choose who powers the memory (no paid trial needed)

The installer asks you to sign in and pick a memory provider:

- claude-mem observer: 30-day free trial, but the checkout asks for a payment method.
- Your own OpenRouter or Gemini key.
- Your Anthropic plan.

To skip the sign-in completely, run the installer with an explicit `--provider` flag or set `CLAUDE_MEM_ONLINE_OPTIN=false` (see `npx claude-mem --help` for provider names).

## Privacy settings to change on day 1

- Analytics are on by default. Turn them off: `npx claude-mem telemetry disable`
- Screenshots from tools are kept by default under `~/.claude-mem/media-v1/`. Turn off "Keep images" in Settings if you don't want that.
- Wrap anything sensitive in `<private>` ... `</private>` and it is never stored.
- Memory lives on your computer in `~/.claude-mem`. Cloud sync is opt-in.

## First searches to try

In a new Claude Code session in the same project, ask:

1. "What did we change in this project last session?"
2. "Search memory for the bug we fixed in the login flow."
3. "Which files did we touch for the payment feature?"

Open the viewer at the worker URL the installer prints (memory, sessions and settings are at `/viewer`).

## Other agents

`npx claude-mem install` also finds OpenCode, T3 Code (Codex and Claude Code), Antigravity CLI and more. Use `--ide <name>` to set up one directly, for example `npx claude-mem install --ide opencode`.

## Troubleshooting

- No memory in the new session: restart Claude Code after install, and work in the same project folder.
- Installed with npm -g by mistake: run `npx claude-mem install`.
- More fixes: the Troubleshooting section of the README.
