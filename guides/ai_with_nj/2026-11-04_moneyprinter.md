# MoneyPrinterTurbo: make a Reel from one topic (free setup guide, @ai_with_nj)

MoneyPrinterTurbo is a free, open-source (MIT) AI short-video maker. Give it a topic and it writes the script, adds a voiceover, picks matching stock footage, adds subtitles and background music, and exports an HD video (portrait 9:16 at 1080x1920, landscape 16:9 or square 1:1).

Official repo: https://github.com/harry0703/MoneyPrinterTurbo (README read 4 Nov 2026, v1.3.9). Every command below comes from it.

## What you need

- A free Pexels API key for stock footage: https://www.pexels.com/api/ (Pixabay also works: https://pixabay.com/api/docs/)
- An AI model for the script: a Claude Code subscription, a ChatGPT plan (Codex sign-in), an API key (OpenAI, Claude, Gemini, DeepSeek and others), or free local Ollama
- A computer: 4 CPU cores and 4 GB RAM minimum, no GPU needed (8 GB RAM recommended)

## Route A: let Claude Code do everything (Mac and Windows)

Open Claude Code (or another agent that can read Skill files and run a terminal) and send:

```text
Use this Skill: https://raw.githubusercontent.com/harry0703/MoneyPrinterTurbo/main/docs/skill/SKILL.md
Create a video with the topic "How AI is changing everyday life."
```

The agent installs and configures MoneyPrinterTurbo, generates the video and gives you the file path. It only asks for API keys that are missing, such as your Pexels key.

Change the topic to your own, for example "3 money habits for first-job salaries in India".

## Route B: the free browser app

Windows one-click package:

1. Open https://github.com/harry0703/MoneyPrinterTurbo/releases/latest and download the `.7z` file under Assets (not "Source code").
2. Extract it, double-click `update.bat`, then `start.bat`.
3. The app opens in your browser (use Chrome or Edge if the page is blank).

Any OS with Python 3.11 (official package name is `mpt`):

```shell
python -m venv .venv
.venv\Scripts\Activate.ps1
python -m pip install mpt
mpt webui
```

(On Mac or Linux activate with `source .venv/bin/activate` and use `python3 -m venv .venv`.)

No install at all: the README has an "Open in Colab" button that runs it in Google Colab.

## Your first video in the app

1. Settings: paste your Pexels key and your AI model key (or choose Ollama).
2. Video Subject: type your topic. Click Generate Script & Keywords with AI.
3. Video Aspect Ratio: Portrait 9:16 for Reels.
4. Voiceover Service: Azure TTS V1 (Edge TTS, free, no key). Voice: pick a Hindi voice (Madhur or Swara) for Hindi scripts, or an English one.
5. Subtitles: keep them on; choose a font that supports your language.
6. Click Generate Video. Files are saved under `storage/tasks`.

## Safety and quality

- Install only from the official repo or the `mpt` package. The PyPI package called `MoneyPrinterTurbo` is run by a third party.
- Read and fact-check every AI script before posting. Edit it in the Video Script box.
- Stock footage comes from Pexels or Pixabay. Add your own clips and voice to make it yours.

## Troubleshooting

- Blank page after start: open it in Chrome or Edge.
- No footage found: the Pexels key is missing or wrong; the log now says why.
- `start.bat` missing: you downloaded "Source code"; get the `.7z` from Assets.
- Docker users: see docs/docker-config-note.md for the config.toml folder issue.
