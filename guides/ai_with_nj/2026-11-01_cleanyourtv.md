# CleanYourTV guide (from @ai_with_nj)

Checked against the official README on 1 Nov 2026: https://github.com/Gathin23/cleanyourtv · site: https://cleanyour.tv

## Will it work on my TV?

- Yes: any Android TV or Google TV. Tested lists cover 398 models from 104 brands (TCL 80, Sony 44, Xiaomi 37, Philips 21, Hisense 14, OnePlus 4, Redmi 3, Vu 3 and more).
- Fire TV: the cleanup works, the new home screen does not.
- No: Samsung (Tizen), LG (webOS), Roku, Vizio, Hisense VIDAA. See https://cleanyour.tv/not-android to switch off tracking with the remote.

## What it does

1. Backs up your installed app list and settings.
2. Disables ad services, telemetry, sponsored rows and preloaded apps with `pm disable-user`. Nothing is uninstalled.
3. Installs a small launcher as the new home screen.

No root, no cable, one-line restore.

## Step 1: on the TV

Settings > Device Preferences > About > press OK on Build seven times > back > Developer options > USB debugging ON. If you see Network or ADB debugging, turn that on too. Keep the TV on.

## Step 2, option A: phone only (about 5 minutes)

Use the free community app linked at https://cleanyour.tv/app (Android). It connects over Wi-Fi, shows a plan first, saves a restore point and only switches apps off.

## Step 2, option B: laptop + AI assistant (about 15 minutes)

You need: same Wi-Fi as the TV, Python 3, a JDK 17 to 22, Android SDK platform 34 with build-tools 34. Assistant: Claude Code, Codex, Gemini CLI or Antigravity CLI.

    git clone https://github.com/Gathin23/cleanyourtv

Open that folder in your assistant, paste PROMPT.md, fill in your TV model. Accept "Allow USB debugging?" on the TV. Answer its checklist: which apps you use, dock size and order, whether to keep the voice assistant, Chromecast and updates.

## Step 2, option C: by hand

All commands are in the README section "Doing it by hand".

## Undo

    TV_HOST=<tv ip> tools/restore.sh examples/<your tv>/debloat.txt

No computer? The TV's Settings > Apps page can re-enable apps. After a firmware update, re-run the script.

## Before you start

- It can void your warranty. Best on TVs out of warranty.
- Apply changes in small batches with the restore ready.
- Use only cleanyour.tv and github.com/Gathin23/cleanyourtv. Look-alike domains are not the project.
