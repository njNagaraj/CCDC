# ffmpeg-skill: let Claude Code edit your Reels (@ai_with_nj)

ffmpeg-skill is a free, open-source (MIT) add-on that gives Claude Code, Codex or Cursor 42 video tools built on FFmpeg. Everything runs on your laptop: no cloud, no API keys, your videos are never uploaded. It checks its own output before it says "done". Repo: https://github.com/kajisho5/ffmpeg-skill (trending on GitHub, 16 Nov 2026).

## Setup

You need Claude Code (or Codex / Cursor) already installed, plus Node.js for `npx`.

1. Install FFmpeg once.
   - Windows: `winget install Gyan.FFmpeg`
   - Mac: `brew install ffmpeg-full` (the plain `ffmpeg` formula lacks the caption filters; see the README Install section for putting it on PATH)
   - Ubuntu: `sudo apt install ffmpeg`
2. Add the skill: `npx ffmpeg-skill` (Codex: `npx ffmpeg-skill --codex`, Cursor: `--cursor`, all three: `--all`)
3. Check your machine: `npx ffmpeg-skill doctor`
4. Open Claude Code in the folder that has your videos and ask in plain words.

## 15 edit prompts to copy

1. "Take interview.mp4, keep 0:45 to 3:10 and 5:00 to 6:30, and make it exactly 60 seconds for Reels."
2. "Cut the silent parts from vlog.mp4."
3. "Make this 16:9 YouTube video vertical 9:16 for Reels."
4. "Make it vertical but use a blurred background instead of cropping."
5. "Fix the volume of podcast.mp4 for Instagram."
6. "Burn the captions from subs.srt into the video, big and readable."
7. "Burn my Hindi captions from hindi.srt." (it picks a font that covers Hindi)
8. "Join clip1.mp4, clip2.mp4 and clip3.mp4 into one video."
9. "Speed up talk.mp4 so it fits in 90 seconds."
10. "Make a version for Reels, one for YouTube Shorts and one for LinkedIn."
11. "Show me a contact sheet of this video so I can pick a cover frame."
12. "Remove the first 5 seconds and the last 10 seconds."
13. "Make the colours look less dull."
14. "Shrink this video so I can send it on WhatsApp."
15. "Check if final.mp4 is OK to upload to Instagram Reels."

## Hindi captions from your voice

Auto captions need a local speech engine. The simplest: `pip install faster-whisper`. The first run downloads its model; your audio never leaves your laptop. Then ask: "Make Hindi captions for reel.mp4 from my speech and burn them in." Always read the captions before posting; speech engines make mistakes.

## Know before you start

- Watch the final video before posting. The README says caption placement is not automatically verified.
- `npx ffmpeg-skill doctor` tells you if a filter is missing (for example the subtitles filter on a plain Mac install).
- Re-run `npx ffmpeg-skill` to update; it does not update by itself.

Source: github.com/kajisho5/ffmpeg-skill README (v3.10.1).
