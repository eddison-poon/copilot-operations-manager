---
name: jira-task-creation
description: Prepare and create standardized Jira testing tasks from Markdown sprint planning notes.
---

# Jira Task Creation

Use this skill when asked to create Jira testing tasks from sprint planning notes.

1. Read `inputs/sprint-planning.md`, `config/jira-config.md`, and `templates/jira-task.md`.
2. Parse tasks grouped by assignee. Use explicit task metadata when provided; otherwise use configured defaults.
3. Use Jira MCP to verify the project, active or named sprint, epic/parent relationship, assignees, issue type, and labels. Check for likely existing duplicates.
4. Use available Jira/Confluence context to enrich descriptions without inventing requirements. If essential details are unavailable, mark them for clarification.
5. Produce a preview table showing summary, assignee, sprint, epic/parent, labels, and any missing fields; include complete description drafts.
6. Wait for explicit approval. Create only approved issues through Jira MCP.
7. Read back created issues, verify requested fields, and report their keys/links and any errors.

Use the Jira instance's supported fields and relationship model; do not assume epic, sprint, or assignee fields are universally named or writable. Never create issues on the basis of a preview alone.
