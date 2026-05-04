---
name: ticket-code-research
description: Research code paths for a Jira ticket brief or read-jira-ticket summary. Always read relevant docs in E:\\D\\Git\\uat\\Codex\\docs first, then trace impacted files, entry points, flows, dependencies, tests, risks, or unknowns before implementation.
---

# Ticket Code Research

## Purpose

Turn a Jira ticket brief into code-level evidence. Use the ticket summary from `read-jira-ticket` as the starting point, then inspect the repository to find the real code paths that matter.

## Workflow

1. Read docs first.
   - Check `E:\D\Git\uat\Codex\docs` for docs that match the ticket, feature, module, or flow.
   - Read the most relevant docs before opening source code.
   - If docs are present, use them to understand prior findings, naming, boundaries, and known behavior.
2. Extract the core request from the ticket brief.
   - Identify the goal, affected area, expected behavior, and any constraints.
   - Keep the original ticket language for business terms and naming.
3. Find likely code entry points.
   - Search for feature nouns, endpoints, job names, config flags, UI labels, error messages, and related tests.
   - Start from controllers, handlers, services, jobs, repositories, models, and shared utilities.
4. Trace the code path.
   - Follow calls outward from the entry point to the first meaningful side effects.
   - Map data flow, branching, validation, persistence, network calls, and event emission.
5. Collect evidence.
   - Record exact file paths, symbol names, and the behavior each file contributes.
   - Prefer confirmed facts from code over assumptions.
6. Separate facts from inference.
   - Mark anything not proven by code as an inference or open question.
   - Call out missing acceptance criteria, hidden dependencies, and likely edge cases.
7. Close with an action-oriented summary.
   - State the likely change surface, the main risks, and the next best file or test to inspect.

## Output Format

Use this structure unless the user asks for something else:

```md
## Quick Summary
- ...

## Docs Reviewed
- ...

## Ticket-to-Code Map
- Ticket intent:
- Relevant code paths:
- Key files:

## What the Code Does
- ...

## Risks / Gaps
- ...

## Tests / Verification
- ...

## Next Step
- ...
```

## Writing Rules

- Write concise, practical findings.
- Reference exact file paths and symbol names when possible.
- Distinguish confirmed behavior from inferred behavior.
- If the repo does not support a claim, say so explicitly.
- Write in the user's language; default to Vietnamese when the request is Vietnamese.

## Good Triggers

- "Research the code for this ticket."
- "Map the implementation surface from this Jira summary."
- "Find the files and flow behind this ticket before coding."
