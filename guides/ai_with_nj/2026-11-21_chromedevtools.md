# Chrome DevTools for agents: let Claude Code find why your website is slow (@ai_with_nj)

Chrome DevTools for agents (`chrome-devtools-mcp`) is a free, open-source (Apache-2.0) tool from the Chrome DevTools team. It lets a coding agent such as Claude Code, Gemini CLI, Cursor or Copilot control and inspect a live Chrome browser: record performance traces, read network requests and console errors, take screenshots and automate clicks. Repo: https://github.com/ChromeDevTools/chrome-devtools-mcp (58,670 stars; +3,306 stars this week, #6 on GitHub weekly trending, 21 Nov 2026; v1.13.0 released 11 Nov 2026).

## What you need

- Google Chrome, current stable version: https://www.google.com/chrome/
- Node.js LTS (includes npm): https://nodejs.org/
- A coding agent. Claude Code needs a paid Claude plan (Pro or higher) or an API account; the free claude.ai plan does not include it. Gemini CLI, Cursor and Copilot also work.

## Step 1: install Claude Code

- Windows (PowerShell): `irm https://claude.ai/install.ps1 | iex`
- Mac: `curl -fsSL https://claude.ai/install.sh | bash`
- Open a new terminal, run `claude`, and log in in the browser.

Official docs: https://code.claude.com/docs/en/setup

## Step 2: add Chrome DevTools

Option A, one command in your terminal (MCP only):

```
claude mcp add chrome-devtools --scope user npx chrome-devtools-mcp@latest
```

Option B, plugin with the built-in skills (inside Claude Code):

```
/plugin marketplace add ChromeDevTools/chrome-devtools-mcp
/plugin install chrome-devtools-mcp@chrome-devtools-plugins
```

Restart Claude Code and check with `/skills`. Use one option, not both.

Gemini CLI:

```
gemini extensions install --auto-update https://github.com/ChromeDevTools/chrome-devtools-mcp
```

## Step 3: first prompt

Type: `Check the performance of https://developers.chrome.com`

Chrome opens by itself and records a performance trace. Then try your own site.

## 12 prompts to test your website

Speed
1. "Check the performance of https://mysite.com and list the 3 biggest problems."
2. "Why does my homepage load slowly? Fix the biggest problem in my code."
3. "Which images on this page are too large?"
4. "Check how this page loads on a slow phone connection."

Bugs
5. "Open https://mysite.com and list every error in the console."
6. "Which network requests on this page fail?"
7. "Why does my login keep logging me out?" (cookie-debugging skill)
8. "Fill the contact form with test data and tell me if it submits."

Quality
9. "Check this page for accessibility issues and fix them." (a11y-debugging skill)
10. "Take screenshots of my homepage on mobile and desktop."
11. "Check every link on this page and list broken ones."
12. "This page gets slower the longer it stays open. Find the memory leak." (memory-leak-debugging skill)

## Privacy settings to turn on

- The agent can see and change everything in the Chrome window it opens. Do not log in to personal or banking accounts there.
- Usage statistics go to Google by default. Opt out by adding `--no-usage-statistics`, for example:
  `claude mcp add chrome-devtools --scope user npx chrome-devtools-mcp@latest --no-usage-statistics`
- Performance tools may send page URLs to Google's CrUX API for real-user data. Turn off with `--no-performance-crux`.
- Turn off update checks with the environment variable `CHROME_DEVTOOLS_MCP_NO_UPDATE_CHECKS`.

## Troubleshooting

- `npx` not found: install Node.js LTS and reopen the terminal.
- Chrome does not open: make sure Google Chrome (not another Chromium browser) is installed and up to date.
- Plugin install fails with "Failed to clone repository": use Option A instead.
- See the official troubleshooting guide: https://github.com/ChromeDevTools/chrome-devtools-mcp/blob/main/docs/troubleshooting.md

Sources: github.com/ChromeDevTools/chrome-devtools-mcp README, docs/client-configurations.md and CHANGELOG.md (read 21 Nov 2026); code.claude.com/docs/en/setup.
