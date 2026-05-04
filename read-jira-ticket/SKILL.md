---
name: read-jira-ticket
description: Read a Jira issue or pasted ticket text and produce a concise summary, scope analysis, risks, dependencies, and clarification questions. Use when Codex needs to interpret a Jira ticket, understand implementation work, or turn ticket details into an actionable breakdown.
---

# Read Jira Ticket

## Goal

Turn a Jira ticket into a practical working brief: what it asks for, what is in scope, what is unclear, and what to do next.
Always answer in Vietnamese unless the user explicitly requests another language.

## Workflow

1. Read the ticket title, description, acceptance criteria, comments, status, priority, labels, assignee, linked issues, and any referenced Confluence pages.
2. Extract the core request:
   - goal
   - affected users or systems
   - current behavior
   - expected behavior
   - constraints or deadlines
3. Classify the ticket:
   - bug, feature, task, spike, refactor, or support
   - likely frontend, backend, infra, data, QA, or cross-functional
   - risk level and implementation complexity
4. Identify missing information:
   - unclear requirements
   - unstated assumptions
   - edge cases
   - dependencies on other teams, systems, or data
5. If linked docs or related tickets exist, use them to resolve ambiguity before concluding.
6. Produce a concise summary and a practical breakdown.

## Output Format

Use this structure unless the user asks for something else:

```md
## Quick Summary
- ...

## What the Ticket Is About
- ...

## Scope
- In scope:
- Out of scope:

## Risks / Gaps
- ...
- ...

## Dependencies
- ...

## Clarifying Questions
- ...
- ...

## Suggested Next Step
- ...
```

## Guidance

- Write the response in Vietnamese.
- Keep the summary short and concrete.
- Prefer exact ticket language when it is important.
- Call out missing acceptance criteria explicitly if they are absent or weak.
- If the ticket is ambiguous, state the ambiguity instead of guessing.
- If the ticket references related issues, summarize the relationship and whether they change scope.
- If the user only wants a quick read, compress the answer to 3 to 5 bullets.

## When to Use

Use this skill when the user asks to:
- read a Jira ticket
- summarize or analyze a Jira issue
- break down task scope
- extract acceptance criteria
- identify risks, dependencies, or missing info
- turn ticket text into an implementation brief
