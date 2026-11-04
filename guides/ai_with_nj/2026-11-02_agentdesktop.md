# agent-desktop: let your AI agent use your apps (free setup guide, @ai_with_nj)

agent-desktop is a free, open-source (Apache-2.0) tool from Vercel Labs. It lets an AI agent such as Claude Code, Codex or Cursor read and use desktop apps on Mac, Windows and Linux: it lists an app's buttons and fields, clicks or types, then checks again.

Official repo: https://github.com/vercel-labs/agent-desktop (commands below come from its README and docs/install.md, read 2 Nov 2026, version 1.0.2).

## What you need

- Node.js with npm (for the install command)
- An AI agent that can run terminal commands: Claude Code, Codex, Cursor or similar. The tool is free; the agent may need a paid plan.
- Mac, Windows, or Linux with a graphical desktop

## Step 1: install

```bash
npm install -g agent-desktop
agent-desktop version
```

Windows note: the program is unsigned. A browser download can trigger SmartScreen or antivirus, and Smart App Control on a clean Windows 11 install blocks it. Installing through npm does not trigger SmartScreen, so use the command above.

## Step 2: give permission

- Mac: run `agent-desktop permissions --guide`. It opens System Settings at the missing permission (Accessibility, for the app you run it from, such as Terminal or VS Code). Screenshots also need Screen Recording.
- Windows: no extra permission for normal apps. An app running as administrator can be read but only controlled by an agent that is also running as administrator.
- Linux: needs your desktop session with `at-spi2-core`.

## Step 3: teach your agent

Install the skill (works for agents listed on skills.sh, including Claude Code, Codex and Cursor):

```bash
npx skills add https://github.com/vercel-labs/agent-desktop --skill agent-desktop
```

Or add these lines to your project's `AGENTS.md`:

```markdown
Use `agent-desktop` to see and operate desktop apps. Before the first use, run
`agent-desktop skills get desktop` and `agent-desktop skills get platform`, and follow them.
```

## Step 4: test it yourself first

```bash
agent-desktop list-apps
agent-desktop snapshot --app Finder -i
```

On Windows PowerShell, put refs in quotes, for example `agent-desktop click '@s8f3k2p9:e8'`.

## 5 first tasks to try (safe apps only)

1. "Open Notes (or Notepad) and type my shopping list: milk, eggs, bread."
2. "List the apps that are open right now."
3. "Read my notifications and tell me which ones are from today."
4. "Take a screenshot of the Calculator window."
5. "Copy the text from this Notes page to the clipboard."

## Safety

- Snapshots, clipboard reads, screenshots and logs can contain private things from your screen. Keep them out of public posts and uploads.
- Start with harmless apps. Do not point it at banking, email sending or payment screens until you trust the setup.
- It works in the background by default (no mouse movement). Physical mouse and keyboard input only happens with `--headed`.
- Only install from the official npm package or the vercel-labs GitHub repo.

## Troubleshooting

- Mac says permission missing: rerun `agent-desktop permissions --guide` and grant it to the app that launched the command.
- `STALE_REF` error: the app changed. Take a new snapshot and use the new refs.
- `AMBIGUOUS_TARGET`: several windows are open. Pass one with `--window-id` from the error details.
- Windows antivirus removed it: reinstall with `npm install -g agent-desktop`.
