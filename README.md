# Copilot Operations Manager

Lightweight VS Code GitHub Copilot agent for testing operations.

## V1: Jira Sprint Task Creation

1. Open this repository in VS Code with Copilot Agent mode and Jira MCP available.
2. Edit `inputs/sprint-planning.md` with tasks grouped by assignee.
3. Set known defaults in `config/jira-config.md` (unknown values can be resolved with Jira MCP).
4. Select the `operations-manager` custom agent.
5. Ask: **Read my sprint planning notes and prepare Jira testing tasks for review.**
6. Review the proposed Jira fields and descriptions. Explicitly approve before creation.
7. Ask the agent to verify and list the created Jira issues.

No Python or manual scripts required. Confluence progress updates are the next agreed P0 workflow, not part of this first foundation.
