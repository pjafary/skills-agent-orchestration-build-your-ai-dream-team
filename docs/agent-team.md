# Agent team

I am using GitHub Copilot CLI in a Codespace to orchestrate a custom agent team for building Mona's Project Pulse dashboard.

## Orchestrator

- **Model:** Claude Opus 4.7 (copilot)
- **Definition:** `.github/agents/orchestrator.agent.md`
- **Responsibility:** Coordinates the Planner, Designer, and Coder; breaks work into phases, assigns non-overlapping file scopes, manages dependencies, integrates the result, and reports the outcome. It does not implement code.

## Planner

- **Model:** Claude Opus 4.7 (copilot)
- **Definition:** `.github/agents/planner.agent.md`
- **Responsibility:** Researches the repository, documentation, dependencies, edge cases, risks, and validation needs, then produces an ordered implementation plan with file assignments and dependencies. It does not write code.

## Designer

- **Model:** Gemini 3.1 Pro (copilot)
- **Definition:** `.github/agents/designer.agent.md`
- **Responsibility:** Owns the dashboard's UI/UX, accessibility, information hierarchy, interaction flow, responsive behavior, and visual design. For Project Pulse, it creates a polished dashboard with project cards, status badges, clear priority treatment, and responsive layout.

## Coder

- **Model:** GPT-5.5 (copilot)
- **Definition:** `.github/agents/coder.agent.md`
- **Responsibility:** Implements assigned code, fixes bugs, follows repository conventions, and validates changes. For the runnable Project Pulse app, it may also create `.vscode/launch.json` configured to use `${workspaceFolder}/app` and open `index.html`.

All agents are instructed not to stage, commit, or push changes; Git operations remain under the learner's control.
