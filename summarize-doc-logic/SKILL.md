---
name: summarize-doc-logic
description: Summarize documents in E:\D\Git\uat\Codex\docs into PM/BA-friendly workflow logic and change-impact notes. Use when analyzing a docs file in that folder and you need to compare the documented workflow with source code behavior before summarizing.
---

# Summarize Doc Logic

## Overview

Turn a technical doc into a concise business-facing explanation of how the workflow works, what changes across the flow, and why it matters to PMs and BAs.

## Workflow

1. Identify the doc being summarized and the code repo(s) it depends on from entry points, paths, and dependencies.
2. Inspect the relevant source code behavior needed to validate the doc.
3. Compare the doc against the code and check whether the workflow, states, side effects, or branching logic differ.
4. If the doc and code match, continue with the summary.
5. If the doc and code differ, stop and report the mismatch instead of summarizing.

## Stop Condition

Only block when the source code and the doc describe different logic.

Report:

- Which doc was checked
- Which code areas or files were compared
- The specific mismatch in workflow, state, side effect, or decision logic
- What needs to be updated in the doc or code

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

