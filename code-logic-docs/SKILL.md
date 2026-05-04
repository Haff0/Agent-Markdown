---
name: code-logic-docs
description: Read code and write Markdown docs for logic, flows, and behavior. Use when you need to inspect source code, trace control flow or data flow, and produce concise `.md` documentation for modules, features, APIs, or business rules.
---

# Code Logic Docs

## Purpose

Read source code, reconstruct the intended behavior, and write clear Markdown documentation that explains how the code works.

## Workflow

1. Define the scope.
   - Identify the repo, files, module, or feature to document.
   - Note the language, framework, and runtime if they affect behavior.
2. Map the structure.
   - Find entry points, public APIs, handlers, services, jobs, or scripts.
   - List the main functions, classes, and dependencies that shape the logic.
3. Trace the behavior.
   - Follow control flow, data flow, state changes, branching, and side effects.
   - Separate core business logic from plumbing, validation, and integration code.
4. Write the documentation.
   - Turn the traced behavior into concise Markdown.
   - Prefer facts tied to code locations over speculation.
5. Verify the result.
   - Check that every claim is supported by the code.
   - Mark unclear areas as `not determined from current code` instead of guessing.

## Documentation Output

Use a structure like this unless the codebase suggests a better one:

```md
# <Feature or Module Name>

## Purpose
What this code does and why it exists.

## Entry Points
Relevant files, functions, classes, or handlers.

## Flow
Step-by-step explanation of how data moves through the code.

## Key Logic
Important branches, rules, validations, and transformations.

## Side Effects
Database writes, file I/O, network calls, logging, or state changes.

## Edge Cases
Errors, fallbacks, assumptions, and known limitations.

## Dependencies
Internal modules and external services this logic relies on.
```

## Writing Rules

- Prefer short, factual sentences.
- Reference exact file paths and symbol names when possible.
- Do not paste large code blocks unless a short excerpt is necessary to explain a branch.
- Distinguish observed behavior from inferred intent.
- If asked for a file, write the `.md` file directly; if asked for analysis only, provide the outline and key findings first.
- For large codebases, split output into multiple docs by bounded area, such as `module-name.md`, `service-name.md`, or `feature-name.md`.

## Good Triggers

- "Read this service and document its business logic."
- "Create Markdown docs for the flow in these files."
- "Explain how this module works and write a `.md` summary."
