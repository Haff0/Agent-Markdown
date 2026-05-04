---
name: ticket-fix-proposal
description: Use after read-jira-ticket and ticket-code-research to turn their outputs into concrete code-fix proposals, recommended implementation options, impact analysis, and test ideas before editing code.
---

# Ticket Fix Proposal

## Goal

Use this skill after you already have:
- output from `read-jira-ticket`
- output from `ticket-code-research`

This skill turns those two outputs into concrete code-fix options that can be selected for implementation.

## Workflow

1. Re-read:
   - ticket goal
   - in-scope / out-of-scope boundaries
   - files, symbols, flows, tests, and risks already identified
2. Separate clearly:
   - fact: something confirmed by the ticket or code
   - inference: something derived from the code
   - gap: missing information that still needs validation
3. Propose 2-3 code-fix options:
   - minimal option
   - balanced option
   - safe / long-term option if needed
4. For each option, include:
   - which files / modules change
   - which logic changes
   - side effects
   - risks
   - tests to add or rerun
5. Choose one recommended option:
   - prefer the smallest scope
   - prefer the lowest risk
   - match acceptance criteria best
   - avoid breaking the existing flow
6. End with a very concrete next step:
   - the first file to change
   - the first test to run
   - any question that still needs confirmation if the gap is large

## Output Format

```md
## Quick Summary
- ...

## Input Data
- Ticket:
- Code research:

## Analysis
- Facts:
- Inferences:
- Gaps:

## Code-Fix Options
### Option 1 - ...
- Changes:
- Pros:
- Cons:
- Risks:
- Tests:

### Option 2 - ...
- ...

## Recommendation
- Choose option ...
- Why:

## Next Step
- ...
```

## Rules

- Always write the final output in Vietnamese.
- Do not invent details beyond the previous outputs unless there is evidence.
- If the data is not enough to choose an option, state the gap clearly and stop at proposal level.
- Prefer the option that changes the fewest files while still satisfying the requirement.
- If the ticket is a bug, include recovery and regression testing ideas.
- If the ticket is a feature or refactor, include backward-compatibility considerations.

## When to Use

Use this skill when the user asks to:
- turn the outputs of the two research steps into code-fix options
- choose an implementation direction before coding
- compare fix approaches
- propose a patch plan from the ticket and code research
