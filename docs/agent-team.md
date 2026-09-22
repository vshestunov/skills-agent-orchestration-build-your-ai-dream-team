# Agent team

I will use GitHub Copilot CLI in a Codespace to orchestrate the work through the custom agents in `.github/agents/`.

- **Orchestrator** uses **Claude Opus 4.7 (copilot)** and coordinates the team, breaking the dashboard work into phases, assigning non-overlapping file scopes, managing dependencies, and verifying the integrated result. Definition: `.github/agents/orchestrator.agent.md`.
- **Planner** uses **Claude Opus 4.7 (copilot)** and researches the repository, dependencies, risks, edge cases, implementation phases, file ownership, and validation expectations. Definition: `.github/agents/planner.agent.md`.
- **Designer** uses **Gemini 3.1 Pro (copilot)** and guides the Project Pulse dashboard's UI/UX, information hierarchy, accessibility, responsive behavior, visual styling, project cards, status badges, and readable spacing. Definition: `.github/agents/designer.agent.md`.
- **Coder** uses **GPT-5.5 (copilot)** and implements the assigned static dashboard files with clear, deterministic, testable code, including `.vscode/launch.json` when assigned. Definition: `.github/agents/coder.agent.md`.

The Orchestrator delegates planning first, then coordinates the Designer and Coder according to the Planner's file assignments and dependencies. The agents do not stage, commit, or push changes; I control Git operations through Copilot CLI.
