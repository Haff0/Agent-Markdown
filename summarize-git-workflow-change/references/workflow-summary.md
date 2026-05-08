# Workflow Summary Checklist

## Read Before Writing

- Identify the workflow or business rule that changed.
- Compare the old behavior and the new behavior.
- Look for changes in triggers, validation, branching, approvals, state transitions, calculations, or user-visible outcomes.
- Treat refactors, renames, formatting, and file movement as noise unless they change behavior.

## Include

- What changed in the workflow
- What users or systems can do now that they could not do before
- What behavior was removed, tightened, loosened, or rerouted
- Any impact on roles, permissions, statuses, timing, or dependencies
- Any likely business impact or risk

## Exclude

- Line-by-line code explanation
- Low-level implementation details
- Pure cleanup changes
- File names unless they help explain the workflow

## Response Template

Use this shape when it fits the change:

1. Summary
2. What changed
3. Before vs after
4. Business impact
5. Risks or notes

## Good Style

- Use plain Vietnamese or English, depending on the user request.
- Keep the explanation concrete and easy to scan.
- Say "workflow changed" only when the behavior really changed.
- If the diff is ambiguous, state the most likely interpretation and mark it as an inference.
