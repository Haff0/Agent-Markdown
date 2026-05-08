---
name: summarize-git-workflow-change
description: Turn git diffs or code changes into PM/BA-friendly summaries of workflow and business-logic changes. Use when asked to review git changes, pull requests, commits, or diffs and explain only how the workflow, user flow, rules, states, inputs, outputs, or business behavior changed.
---

# Summarize Git Workflow Change

## Purpose

Use this skill to translate code changes into clear business language. Focus on what changed in the workflow, not on implementation details.

## Process

1. Read the diff and identify the changed workflow, decision, or business rule.
2. Trace the path from trigger to outcome: input, validation, branching, action, result.
3. Compare before vs after behavior.
4. Summarize the business impact in plain language.
5. Ignore refactors, formatting, renames, and code movement unless they change behavior.

## Output Rules

- Write for PM and BA readers.
- Use plain language, short sentences, and concrete behavior changes.
- Prefer before/after comparisons.
- Group by workflow or business flow, not by file.
- Mention only changes that affect logic, rules, states, approvals, calculations, or user experience.
- If no workflow changed, say that clearly.
- If something is inferred from the diff, label it as an inference.

## Suggested Format

- Summary
- What changed
- Before vs after
- Business impact
- Risks or notes

See [references/workflow-summary.md](references/workflow-summary.md) for the review checklist and response template.

## Resources (optional)

### scripts/
Not required.

### references/
Use for the checklist, inclusion rules, exclusion rules, and response template.

### assets/
Not required.
