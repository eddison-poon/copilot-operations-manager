---
name: jira-task-creation
description: Prepare and create standardized Jira testing tasks from Markdown sprint planning notes using the company Jira Assistant skill.
---

# Jira Task Creation

1. Read `inputs/sprint-planning.md`, `config/jira-config.md`, and `templates/jira-task.md`.
2. Parse tasks by assignee and apply explicit metadata or configured defaults.
3. Use the attached `gaip-agenthub-skills-marketplace/skills/jira-assistant-skill` to search Jira, resolve project/issue type/assignees/sprint/epic, and check likely duplicates. Follow that skill's documented CLI instructions and site configuration. If the skill is unavailable, ask the user to attach it; do not pretend Jira access is available.
4. Draft descriptions from the template. Do not invent requirements; flag unknowns and potential overlaps.
5. Preview each proposed issue's summary, description, project, issue type, assignee, labels, and optional priority. Also display intended sprint and epic separately as **not supported by the current create script**.
6. Obtain explicit approval for the exact tickets and supported fields to create. Do not treat approval of a preview as permission to omit requested mandatory fields; disclose limitations first.
7. Let Copilot invoke the company skill's existing `scripts/upsert_jira_ticket.py create` workflow with its documented arguments. Do not write or modify Python scripts. Never attempt unsupported sprint/epic flags.
8. Read back each new Jira issue using the company skill's lookup workflow. Verify saved fields, return keys/links, and clearly list any sprint/epic assignments still outstanding.

Use only authorized company tooling. If the user requires sprint or epic to be set before considering a ticket complete, stop and ask whether to proceed without them or use a separately verified supported method. Do not silently substitute Jira MCP write calls.
