# diagram-design: let Claude Code draw clean diagrams for your slides (@ai_with_nj)

diagram-design is a free, open-source (MIT) skill for AI coding agents. Describe a diagram in plain words and the agent picks one of 51 diagram types and writes one HTML file you open with a double-click. No account, no server, no tracking. Repo: https://github.com/cathrynlavery/diagram-design (#9 on GitHub daily trending, 19 Nov 2026, 68,544 stars).

## What you need

- A coding agent. Claude Code needs a paid Claude plan (Pro or higher) or an API account; the free claude.ai plan does not include it. The skill also works in Cursor, Codex, GitHub Copilot, Gemini CLI, Cline and Windsurf.
- For `npx`: Node.js (https://nodejs.org).
- For PNG export only: Python plus Playwright (see below).

## Step 1: install Claude Code

- Windows (PowerShell): `irm https://claude.ai/install.ps1 | iex`
- Mac: `curl -fsSL https://claude.ai/install.sh | bash`
- Open a new terminal, run `claude`, and log in in the browser.

Official docs: https://code.claude.com/docs/en/setup

## Step 2: add diagram-design

Inside Claude Code:

```
/plugin marketplace add cathrynlavery/diagram-design
/plugin install diagram-design@diagram-design
```

Turn on updates: run `/plugin`, open Marketplaces, select diagram-design, choose Enable auto-update.

Using Cursor, Gemini CLI, Codex or Copilot instead? Run in your terminal:

```
npx skills add cathrynlavery/diagram-design
```

Update that copy later with `npx skills update diagram-design`.

## Step 3: your first diagram

Open Claude Code in any folder and ask. The agent says which type it picked, then writes an `.html` file. Double-click it to open in your browser.

## 15 diagram prompts to copy

Work
1. "Make a flowchart of our leave approval: employee applies, manager approves or rejects, HR updates records."
2. "I need a quadrant showing Q2 projects by impact vs effort." (from the README)
3. "Make a Gantt chart for a 6-week website launch: research, design, build, testing, launch."
4. "Draw our team's org chart: CEO, 3 heads, 2 people under each."
5. "Make a timeline of our company milestones from 2020 to 2026."
6. "Draw a swimlane of how a customer order moves from sales to warehouse to delivery."
7. "Make a pyramid of our priorities: mission at the top, goals, projects, daily tasks."

Class and study
8. "Draw a Venn diagram comparing plant and animal cells."
9. "Make a flowchart of how a bill becomes a law in India."
10. "Draw a timeline of the Indian freedom movement, 1857 to 1947."
11. "Make a process diagram of the water cycle."

Pitches and projects
12. "Draw the architecture of my app: frontend, backend, database, Redis cache." (from the README)
13. "Make a customer journey for a food delivery app: discover, order, wait, receive, review."
14. "Draw a Venn of desirable, feasible and viable for my startup idea."
15. "Make this whiteboard sketch presentable." (attach an Excalidraw file; from the README)

## Export PNG for slides

One-time setup: `pip install playwright && playwright install chromium`

Then in Claude Code: `/diagram-design:export-diagram my-diagram.html --png-only`, or just ask "Save my-diagram.html as PNG." PNG is rendered at 2x. Ask for SVG if you want to edit it in Figma.

## Match your brand

Ask: "onboard diagram-design to https://yoursite.com". It reads your site's colours and fonts, shows the change, and after you say "yes, apply it" every new diagram uses them.

## Redraw old diagrams

It redraws draw.io, Mermaid, Excalidraw and PlantUML files in its own style. Example: `/diagram-design:import-drawio platform.drawio --size=slide-16x9`

## Know before you start

- The same prompt can give a different layout each time. Ask again or say what to change.
- The result is not a drag-and-drop canvas. Change it by asking the agent or editing the SVG.
- For diagrams that live in code and change every week, the README says Mermaid is still the better fit.
- Diagrams load fonts from Google Fonts when opened. Ask for system fonts if you need it fully offline.

Sources: github.com/cathrynlavery/diagram-design README and PRIVACY.md (read 19 Nov 2026); code.claude.com/docs/en/setup.
