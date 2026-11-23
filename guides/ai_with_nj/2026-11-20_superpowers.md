# Superpowers: make Claude Code plan, test and check its own work (@ai_with_nj)

Superpowers is a free, open-source (MIT) set of skills for AI coding agents. Once installed, the skills switch on by themselves: before writing code the agent asks what you are really trying to do, writes a plan of small tasks, writes a failing test first, builds until the test passes, and reviews each task. Repo: https://github.com/obra/superpowers (#2 on GitHub daily trending, 20 Nov 2026, 322,747 stars; v7.0.2 released 3 Nov 2026).

## What you need

- A coding agent. Claude Code needs a paid Claude plan (Pro or higher) or an API account; the free claude.ai plan does not include it. Superpowers also works in Cursor, Codex, Gemini CLI, GitHub Copilot CLI and others.
- A project folder (it can be empty).

## Step 1: install Claude Code

- Windows (PowerShell): `irm https://claude.ai/install.ps1 | iex`
- Mac: `curl -fsSL https://claude.ai/install.sh | bash`
- Open a new terminal, run `claude`, and log in in the browser.

Official docs: https://code.claude.com/docs/en/setup

## Step 2: install Superpowers

Claude Code (official Anthropic marketplace):

```
/plugin install superpowers@claude-plugins-official
```

Cursor (in Agent chat): `/add-plugin superpowers`

Gemini CLI (in your terminal):

```
gemini extensions install https://github.com/obra/superpowers
```

Update Gemini CLI later with `gemini extensions update superpowers`.

## Step 3: your first project

1. Make a new folder, open a terminal in it and run `claude`.
2. Say what you want, e.g. "Build me a simple habit tracker web app."
3. It asks why you want it and what matters. Answer in plain words.
4. It shows the design in short chunks. Read each one and say OK or correct it.
5. It writes a plan of small tasks (2 to 5 minutes each). Say "go".
6. It works task by task: test first, then code, then a review. Critical issues stop the work until fixed.
7. When all tasks pass, it asks whether to merge, open a PR, keep or discard the branch.

## Good first requests

- "Build a to-do list web page that saves to my browser."
- "Make a script that renames all photos in this folder by date."
- "Add a dark mode to this website."
- "Fix the bug where the login button does nothing." (it uses its debugging skill to find the root cause)

## When something goes wrong

Ask: "figure out what went wrong with superpowers in this session". It reads the session, shows what happened with evidence, and can package a scrubbed bug report.

## Know before you start

- It is slower at the start on purpose: it asks questions before building.
- It is made for building software, not for everyday chat questions.
- Optional usage ping: the visual companion loads a logo that reports only the Superpowers version. Turn it off by setting `SUPERPOWERS_DISABLE_TELEMETRY` to true. It also honours Claude Code's `DISABLE_TELEMETRY`.
- Always read the plan before you say "go".

Sources: github.com/obra/superpowers README and RELEASE-NOTES.md (read 20 Nov 2026); code.claude.com/docs/en/setup.
