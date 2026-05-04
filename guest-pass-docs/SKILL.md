---
name: guest-pass-docs
description: Document the Guest Pass feature in the Codex-Membership codebase. Use when reading GuestPasses logic, controllers, jobs, or related membership flows and when you need to produce one Markdown doc per function or subfeature.
---

# Guest Pass Docs

## Purpose

Read the Guest Pass feature code, trace the actual behavior, and write separate Markdown docs for each function or subflow.

## Scope

Focus on the Guest Pass lifecycle in `Codex-Membership`, especially:

- `Services/Implement/GuestPassesService.cs`
- `Services/Interface/IGuestPassesService.cs`
- `Controllers/MembershipGuestPassesController.cs`
- `Controllers/MembershipWebsiteController.cs`
- related member and renewal flows that create, suspend, use, or print guest passes

If a request touches a wider membership flow, document only the Guest Pass parts unless the user asks for the broader system.

## Workflow

1. Identify the exact subfeature.
   - Examples: create, update status, list by member, generate PDF, delete, controller endpoint, renewal job.
2. Read the primary code path first.
   - Start from the service or controller that owns the behavior.
   - Follow the method calls into repositories, helpers, and related services.
3. Trace the full flow.
   - Capture inputs, validation, branching, persistence, and side effects.
   - Note any status transitions, PDF generation, or branding/template rules.
4. Split the output by function or subfeature.
   - Write one `.md` file per feature/function when the code path is distinct.
   - Keep each doc narrowly scoped and easy to scan.
5. Verify against code.
   - Only include behavior that is visible in the code.
   - Mark uncertain intent as `not determined from code`.

## Output Rule

When writing docs, produce files like:

- `guest-passes-create.md`
- `guest-passes-update-status.md`
- `guest-passes-get-by-member.md`
- `guest-passes-get-pdf.md`
- `guest-passes-delete.md`
- `guest-passes-controller.md`

Use a consistent structure in each file:

```md
# <Function or Feature Name>

## Purpose

## Entry Points

## Inputs

## Flow

## Key Logic

## Side Effects

## Edge Cases

## Dependencies
```

## Writing Rules

- Prefer exact file paths and symbol names.
- Keep explanations short and factual.
- Separate observed behavior from inference.
- Mention status changes, database writes, and external rendering or template calls.
- For brand-specific behavior, document each brand branch explicitly.
- If multiple functions share one flow, still create separate docs when the output should be consumed independently.

## Good Triggers

- "Document the Guest Pass feature."
- "Write Markdown docs for `GuestPassesService`."
- "Explain the PDF generation flow for guest passes."
- "Create one `.md` file per Guest Pass function."
