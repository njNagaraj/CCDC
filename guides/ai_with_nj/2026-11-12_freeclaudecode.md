# Free Claude Code: run Claude Code with free models (full guide, @ai_with_nj)

Free Claude Code (FCC) is an independent open-source (AGPL-3.0) app. It sits between the Claude Code app and an AI provider, so Claude Code can use free models from NVIDIA, Google Gemini, Groq, OpenRouter and others. It is not made or endorsed by Anthropic, and with free providers the thinking is done by those providers' models, not Anthropic's Claude.

Official repo: https://github.com/Alishahryar1/free-claude-code (README read 12 Nov 2026). Every command below is copied from it.

## Step 1: install

Windows (PowerShell):

```powershell
& ([scriptblock]::Create((irm "https://raw.githubusercontent.com/Alishahryar1/free-claude-code/main/scripts/install.ps1")))
```

Mac / Linux (Terminal):

```bash
curl -fsSL "https://raw.githubusercontent.com/Alishahryar1/free-claude-code/main/scripts/install.sh" | sh
```

When prompted, choose Claude Code as a coding agent (the installer installs it from Anthropic's official installer). You can also tick RTK and Headroom to save tokens.

## Step 2: start FCC and add a free key

- Windows / Mac: open "Free Claude Code" from the Start menu / Applications. Use the tray or menu-bar icon to open Admin.
- Linux: run `fcc-server` and keep that terminal open.

The Admin page opens. Then:

1. Create a free key at https://build.nvidia.com/settings/api-keys
2. In Admin, open Providers, then NVIDIA NIM, click Add key, paste it, Save.
3. Leave the model on the default `nvidia_nim/nvidia/nemotron-3-ultra-550b-a55b`, or pick another from the dropdown.
4. Click Apply.

Other free options in the provider list: OpenRouter (`open_router/openrouter/free`), Groq, and Google AI Studio (Gemini key from https://aistudio.google.com/apikey). Free limits are set by each provider and can change.

## Step 3: run Claude Code

In a new terminal:

```bash
fcc-claude
```

Try: "Explain this folder and suggest 3 fixes." Other apps work the same way: `fcc-codex`, `fcc-cline`, `fcc-opencode`.

## Bonus: use it from your phone (Telegram)

1. Create a bot with @BotFather and copy its token.
2. Get your numeric user ID from @userinfobot.
3. In Admin, Messaging: set Messaging Platform to telegram, enter the Bot Token, your User ID and an Allowed Directory (a full folder path).
4. Apply, restart if asked, then message your bot.

## Before you rely on it

- Your code is sent to the provider you choose. Keep private or client code off free providers.
- Free tiers have rate limits; FCC can fall back to another key or provider automatically.
- To protect the local proxy, turn on Proxy Authentication in Admin.
- Install only from the official GitHub repo above.
