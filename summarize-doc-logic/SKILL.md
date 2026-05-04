---
name: summarize-doc-logic
description: Summarize documents in E:\D\Git\uat\Codex\docs into PM/BA-friendly workflow logic and change-impact notes. Use when analyzing a docs file in that folder and you must first check the related code for uncommitted changes; if the code is dirty, stop and report the changed files instead of summarizing.
---

# Summarize Doc Logic

## Overview

Turn a technical doc into a concise business-facing explanation of how the workflow works, what changes across the flow, and why it matters to PMs and BAs.

## Workflow

1. Identify the doc being summarized and the code repo(s) it depends on from entry points, paths, and dependencies.
2. Check the relevant repo(s) for uncommitted changes before doing any summary work.
3. If any modified, deleted, added, or untracked files exist, stop immediately and report the changed paths.
4. If the code is clean, read the doc and extract the workflow in business terms.
5. Summarize the logic with emphasis on triggers, branches, state changes, side effects, edge cases, and workflow differences.

## Stop Condition

If code is changed, do not summarize the doc.

Report only:

- Which source code not mapped to the doc, required updates, or is unclear in the doc

## Summary Style

- Write for PM/BA readers first, not developers.
- Explain the intent of the workflow before the implementation details.
- Use simple language for the main explanation, then mention function or file names only as anchors.
- Prefer "before / after" behavior, decision points, and state transitions over line-by-line code detail.
- Call out data written, statuses updated, notifications sent, retries, failures, and dependencies.
- Keep the summary short, structured, and actionable.

## Recommended Output Shape

- Purpose
- Entry points
- End-to-end flow
- Decision points
- State or data changes
- Side effects
- Edge cases
- Dependencies
- What changed across the workflow

