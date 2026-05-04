# Markdown Output Template

Use this template for each file the skill produces.

```md
# <Feature or Function Name>

## Purpose
What the code does and why it exists.

## Entry Points
Relevant controllers, services, jobs, or public methods.

## Inputs
Parameters, request bodies, entity fields, or config values.

## Flow
Step-by-step behavior in the order the code executes.

## Key Logic
Important branches, rules, and transformations.

## Side Effects
Database writes, external calls, file generation, logs, or state changes.

## Edge Cases
Fallbacks, validation failures, null handling, and limitations.

## Dependencies
Internal modules, helpers, repositories, and external services.
```

## Split Guidance

- If a feature has multiple independently meaningful methods, create one file per method.
- If a method has major branches with different business meaning, document each branch in its own file when helpful.
- If the user wants one file only, collapse the split but keep the same headings.
