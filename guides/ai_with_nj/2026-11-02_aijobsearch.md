# AI Job Search with Claude Code: free setup guide (@ai_with_nj)

AI Job Search is a free, open-source (MIT) set of Claude Code commands for a job hunt: build your profile, find jobs, shortlist them, write a tailored CV and cover letter, prep interviews and track replies. It is an independent project, not made by Anthropic.

Official repo: https://github.com/ai-job-search-dev/ai-job-search (all commands below come from its README and SETUP.md, read 2 Nov 2026).

## What you need

- Claude Code with a paid Claude plan (Pro, Max or Team) or Anthropic API credits. There is no free tier. Docs: https://docs.anthropic.com/en/docs/claude-code
- Python 3.10 or newer
- Bun (runs the job search tools)
- LaTeX (turns the CV and cover letter into PDFs): MiKTeX on Windows, MacTeX on Mac
- About 30 to 60 minutes for the first setup

## Step 1: install the tools

Windows (PowerShell):

```powershell
py --version
powershell -ExecutionPolicy Bypass -c "irm https://bun.sh/install.ps1 | iex"
```

Then install MiKTeX from https://miktex.org/download. If you chose the small "Basic MiKTeX", switch on silent package installs once, or the build stops on pop-ups:

```powershell
initexmf --set-config-value=[MPM]AutoInstall=1
```

Mac (Terminal):

```bash
python3 --version
curl -fsSL https://bun.sh/install | bash
```

Then install MacTeX from https://tug.org/mactex/.

Claude Code (both):

```bash
npm install -g @anthropic-ai/claude-code
```

## Step 2: get the repo and keep it private

A GitHub fork of a public repo is always public, and `/setup` writes your name, contact details, work history and salary expectations into the project files. So do not push your copy to a public fork. The simplest safe way is to clone it and never push:

```bash
git clone https://github.com/ai-job-search-dev/ai-job-search.git
cd ai-job-search
```

If you want an online backup, push it to a new private repository of your own and add the original as `upstream` (SETUP.md section 8 has the exact steps).

## Step 3: install the job search tools

```bash
python tools/install_portal_clis.py
```

(On Mac use `python3`.)

## Step 4: build your profile

```bash
claude
```

Inside Claude Code:

```
/setup
```

It can read a `documents/` folder (CV PDF, LinkedIn profile PDF, certificates), a CV pasted in chat, or interview you. Answer honestly: the tool only uses what is in your profile and never invents skills.

## Step 5: find jobs in India

`/scrape` searches the job boards set up in your profile. The ready-made boards are Danish, plus two that work anywhere: LinkedIn search and freehire.me. LinkedIn takes any city, for example "Bengaluru, Karnataka, India" or "Mumbai, Maharashtra, India". Tell `/setup` your Indian city when it asks about locations.

LinkedIn search is for personal use only (automated access is against LinkedIn's terms), so keep it to a few searches a day.

Want another job board? Run `/add-portal` and give it the board's URL. It checks the site and builds a search tool for it. It refuses boards that need a login.

## Step 6: your first tailored application

```
/apply <paste the job link here>
```

If the site blocks it, paste the full job description instead. Claude scores your fit, drafts the CV and cover letter, a second Claude agent reviews them, Claude revises, then it builds the PDFs (CV exactly 2 pages, cover letter 1 page) and checks the text an ATS will read.

Read every file before you send it. The tool drafts, you apply.

## More commands

| Command | What it does |
|---|---|
| `/rank` | Scores all scraped jobs and gives a shortlist |
| `/interview` | Prep pack and a mock interview for a booked interview |
| `/outcome` | Records results, drafts follow-ups (never sends them) |
| `/html-report` | Offline dashboard of your applications |
| `/upskill` | Your skill gaps and a learning plan |

## Safety

- Keep your copy private (step 2).
- Job posts are treated as untrusted text, but this is not a sandbox. On an unfamiliar job site, check what was fetched before you send anything.
- The creator's own result (69 applications, 20 first interviews, 1 job) is their report, not a promise.

## Troubleshooting

- `lualatex` or `xelatex` not found: LaTeX is not on your PATH. Reopen the terminal after installing MiKTeX or MacTeX.
- CV build fails on fonts: the CV uses `lualatex` and the cover letter `xelatex`; make sure the `moderncv` package is installed (MiKTeX auto-install from step 1 handles it).
- Job search tools fail: check Bun is installed and rerun step 3.
- Old clone with `.claude/settings.local.json`: delete that file (SETUP.md, Troubleshooting).
