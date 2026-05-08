---
name: review-git-change
description: Review git diffs and changed code, summarize the logic and scope, identify what was completed versus not completed, and call out likely bugs, regressions, or gaps. Use when the user asks to check git changes, review modified code, explain implementation logic, or assess risks in a code change.
---

# Review Git Change

## Overview

Use this skill to inspect changed files in a git diff or working tree and produce a practical review. Focus on what changed, why it changed, what is finished, what is still missing, and what could break.
Write the final response in Vietnamese. Keep internal analysis and review notes in English if that is more natural.

## Workflow

1. Check the change surface first.
   - Read `git status`, then inspect the diff for staged and unstaged files.
   - Separate new files, modified files, deleted files, and rename-only changes.

2. Understand the intent of each change.
   - Trace the main code path, data flow, and control flow that the edit affects.
   - Summarize the logic in plain language.
   - If a change is incomplete, identify the missing step rather than guessing.

3. Review the implementation against the likely goal.
   - Verify naming, branching, validation, error handling, and side effects.
   - Check whether the change is consistent with nearby patterns in the codebase.
   - Note any tests, docs, or migrations that should exist but are missing.

4. Report completion status clearly.
   - State what was done.
   - State what was not done or remains partial.
   - Distinguish confirmed facts from inference.

5. Call out likely failures.
   - Mention bugs that could appear from the edit itself.
   - Mention regression risks, edge cases, and integration breaks.
   - Highlight cases where the code may compile but behave incorrectly.

## Output Format

Use this structure:

- `Tong quan`: what the change appears to do.
- `Logic`: the implemented flow or behavior.
- `Da lam`: concrete completed items.
- `Chua lam`: missing pieces, unfinished work, or limits.
- `Rui ro`: likely bugs, regressions, or failure modes.

Keep the summary concise, specific, and grounded in the actual diff. If the user wants a stronger review, prioritize bugs and risks over restating the code.
