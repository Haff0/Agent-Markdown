---
name: feature-md-docs
description: Document a requested feature or function from code into Markdown. Use when the user names a specific feature, method, or flow and wants separate `.md` docs for each subfeature, endpoint, branch, or function.
---

# Feature MD Docs

## Purpose

Read the requested code path, understand how it works, and write one Markdown file per meaningful feature or function.

## Output Location

- Write generated docs to `E:\D\Git\uat\Codex\docs` by default.
- Create the directory if it does not exist.
- Only use another destination if the user explicitly asks for it.

## Use When

- The user names a feature, function, or flow to document.
- The user wants output split into separate `.md` files.
- The goal is analysis plus documentation, not code changes.

## Workflow

1. Check existing docs first.
   - Read relevant docs from `E:\D\Git\uat\Codex\docs` before opening source code.
   - Use docs to understand prior findings, naming, and flow boundaries.
2. Narrow the scope.
   - Confirm the exact feature/function name from the user request.
   - Identify the repo area and the primary entry points.
3. Read the code path.
   - Start from controllers, services, jobs, handlers, or public methods.
   - Follow the calls into helpers, repositories, and models.
4. Break the feature into docs.
   - Create one `.md` file per function, endpoint, branch, or subflow when each part has distinct behavior.
   - Keep shared setup or cross-cutting behavior in a separate overview doc if needed.
5. Write each doc.
   - Explain purpose, inputs, flow, key rules, side effects, dependencies, and edge cases.
   - Use exact file paths and symbol names.
   - Save the `.md` files under `E:\D\Git\uat\Codex\docs` unless the user requested a different location.
6. Verify against code.
   - Keep claims grounded in source.
   - Mark anything unclear as `not determined from code`.

## Output Template

Use a structure like this for each file:

```md
# <Feature or Function Name>

## Purpose

## Entry Points

## Inputs

## Flow

## Key Logic

## Side Effects

## Edge Cases

## Dependencies
```

## Doc Splitting Rules

- Create separate files for distinct behavior, even when they live in one class.
- Group a controller endpoint with its service method only when the endpoint is a thin wrapper.
- Split branch-heavy logic into separate docs when each branch has a different business meaning.
- For large features, write an overview file plus one file per subfeature.

## Writing Rules

- Prefer short, factual sentences.
- Keep docs narrowly scoped and easy to scan.
- Mention persistence, network calls, file generation, template rendering, and status changes.
- Do not copy large code blocks.
- Distinguish observed behavior from inferred intent.

## Good Triggers

- "Document this feature and split it into separate Markdown files."
- "Explain how this function works and create `.md` docs for each subflow."
- "Write docs for the requested feature from the code."
