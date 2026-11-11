# Claude Code + Anthropic's Office skills: setup and 12 prompts (@ai_with_nj)

Anthropic publishes its Agent Skills at https://github.com/anthropics/skills. The Word (docx), Excel (xlsx), PowerPoint (pptx) and PDF skills are the ones that power Claude's own document features, and on 6 Nov 2026 Anthropic moved them to the free Apache 2.0 licence. All commands below come from the repo README (read 9 Nov 2026).

## What you need

- Claude Code on Windows, Mac or Linux, with a Claude plan or API credits (Claude Code is not free).
- On Claude.ai (web and app) these skills are already built in on paid plans; nothing to install there.

## Install in Claude Code (2 commands)

Inside Claude Code:

```
/plugin marketplace add anthropics/skills
/plugin install document-skills@anthropic-agent-skills
```

For the creative and developer skills too:

```
/plugin install example-skills@anthropic-agent-skills
```

Or use the menu: Browse and install plugins, then anthropic-agent-skills, then document-skills, then Install now.

## How to use

Just mention the job. Anthropic's own example: "Use the PDF skill to extract the form fields from path/to/some-file.pdf".

## 12 prompts to copy

PowerPoint
1. "Turn report.pdf into a 10-slide deck for my manager, one idea per slide."
2. "Read old_deck.pptx and give me the text of every slide as a summary."
3. "Make a 6-slide pitch deck for my tiffin business from these notes."

Excel
4. "Clean this bank statement CSV, add a Category column and chart my monthly spend."
5. "Build a monthly budget sheet with formulas for income, rent, EMI and savings."
6. "Fix the broken formulas in sales.xlsx and explain what was wrong."

Word
7. "Write my offer-letter reply using this Word template."
8. "Turn these meeting notes into a formatted Word report with headings and a table."
9. "Make a one-page resume in Word from my LinkedIn PDF."

PDF
10. "Merge these 5 PDFs into one, in date order."
11. "Fill the form fields in application.pdf with my details from details.txt."
12. "Extract the tables from this PDF into an Excel sheet."

Always open and check the file before you send it.

## Make your own skill

A skill is a folder with a SKILL.md file. The frontmatter needs only `name` and `description`; the rest is your instructions. Start from the template in the repo, or install example-skills and ask: "Use skill-creator to make a skill for my weekly report format."

## Good to know

- Anthropic says these skills are for demonstration and education; test them before critical work.
- 19 skills are in the repo, including canvas-design (posters), frontend-design (websites), slack-gif-creator and webapp-testing.
