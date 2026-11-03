# Daily Testing Status — Input

Paste the exact JQL from each Jira dashboard/filter below. Replace the examples with your company's real queries. Each environment is queried independently.

## Report Settings

- Completed statuses: Done, Closed
- Completion formula: Completed / Total * 100
- Output: Markdown table with all Jira statuses, completed count, and completion percentage

## Environment: SIT

```jql
project = ETIVAI AND labels = SIT AND fixVersion = "Release 2.0"
```

## Environment: UAT

```jql
project = ETIVAI AND labels = UAT AND fixVersion = "Release 2.0"
```

## Environment: PPD

```jql
project = ETIVAI AND labels = PPD AND fixVersion = "Release 2.0"
```

<!-- Add or remove '## Environment: NAME' sections as needed. Queries above are examples, not validated company filters. -->
