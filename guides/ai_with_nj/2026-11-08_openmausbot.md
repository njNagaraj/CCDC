# OpenMausBot: your own team of AI bots (setup guide, @ai_with_nj)

OpenMausBot is a free, open-source (Apache-2.0) desktop app. Every chat in it is a real AI agent with its own personality, model, computer and connected apps. It runs on the AI tools you already have (Claude Code, Codex or Grok) and keeps transcripts and keys on your computer in `~/.openmausbot`.

Official repo: https://github.com/milind-soni/OpenMausBot · site: https://www.openmausbot.com (README read 8 Nov 2026). It is an independent project, not made by xAI, Meta, OpenAI or Manus, and it has no crypto token.

## Step 1: get an AI engine on your computer

OpenMausBot needs at least one agent CLI installed and logged in:

- Claude Code (`claude`), with a Claude plan or API credits: https://claude.com/claude-code
- Codex (`codex`), with a ChatGPT login: https://github.com/openai/codex
- Grok CLI (`grok`): https://x.ai/cli

They show up in OpenMausBot's model picker automatically.

## Step 2: download the app

From https://github.com/milind-soni/OpenMausBot/releases/latest:

- Windows x64: `OpenMausBot-setup.exe`
- Mac Apple silicon: `OpenMausBot.dmg` (Intel: `OpenMausBot-intel.dmg`), signed and notarized
- Ubuntu 24.04 x64: `.deb` or AppImage (beta)

Download only from that releases page or openmausbot.com.

## Step 3: create 3 starter bots

Click + to make a bot, give it a name, a job and a model. Ideas to copy:

1. Inbox helper: "You sort my email each morning and list the 5 that need a reply." (connect Gmail)
2. Research buddy: "You find and summarise sources for any topic I send, with links."
3. Weekly planner: "Every Sunday you turn my notes into a plan for the week."

Each new bot asks what you mostly want help with: work, writing, life admin or a bit of everything.

## Optional extras (they can cost money)

- Connected apps (Gmail, Slack, GitHub, Notion and 500+ more) use a Composio key: see docs/composio.md in the repo.
- A cloud computer for a bot uses Boat, which is paid after its trial. A local VM is the free alternative.
- Voice uses ElevenLabs or Fish Audio keys; built-in Mac voices need no key.

## Keep costs low

- The app is free. Your Claude or ChatGPT plan is the main cost.
- Skip cloud computers until you need them.
- Start with one bot for one task.

## Privacy

- Data lives in `~/.openmausbot` on your computer.
- Usage analytics are optional and anonymous. Turn them off in Settings, General, Usage analytics.
- Letting a bot control your own computer is opt-in (macOS and Ubuntu Xorg). Use approvals for anything that sends or pays.
