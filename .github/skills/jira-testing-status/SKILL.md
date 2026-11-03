---
name: jira-testing-status
description: Collect Jira issue status counts for testing environments from user-provided JQL and produce a daily Markdown progress table.
---

# Jira Testing Status

Use this skill when asked for a testing status or daily testing progress report. This is read-only: never create, edit, or transition Jira issues.

1. Read `inputs/testing-status.md`. Each environment section contains a JQL code block; treat the supplied JQL as authoritative. Do not silently rewrite its filters or add status restrictions.
2. Read the report settings in the same file, including which Jira statuses count as completed. The default is `Done` and `Closed`; match status names case-insensitively.
3. Use the attached company `gaip-agenthub-skills-marketplace/skills/jira-assistant-skill` and follow its `SKILL.md` and documented `scripts/search_jira.py` lookup workflow. Copilot runs the existing company script; the user should not need to execute it manually. Do not assume Jira MCP is installed. If the company skill is not attached or cannot execute the JQL, explain the blocker rather than invent results.
4. Run each environment's exact JQL independently. Obtain every matching issue and its Jira status, following all pages when results are paginated. Use a verified total/status aggregation if the company tool provides one. Never treat the first page as the complete result.
5. Count issues by their actual Jira status. Preserve distinct status names in the output; include a column for every status seen across the environments. Calculate `Completed = sum(counts for configured completed statuses)` and `Completion % = Completed / Total * 100` (use `N/A` when Total is zero).
6. Return a Markdown table with environment, total, all discovered status counts, completed, and completion %. Add a totals row summing per-environment counts, and show the retrieval date/time, completion definition, and any query failures or partial results.
7. Only show a complete consolidated total if all environment queries completed successfully. If some failed, mark the report partial and do not present partial numbers as complete.

An issue may match more than one environment JQL. The totals row sums environment results and may double-count those issues; label it `Sum of environments (not deduplicated)`. Do not interpret Jira issue completion as test execution pass rate. Never fabricate counts, infer statuses from dashboard visuals, or modify the company's scripts. Improve reporting rules through Markdown configuration.
