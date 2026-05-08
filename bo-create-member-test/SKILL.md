---
name: bo-create-member-test
description: Execute the BO UAT web workflow for creating a Member, including logging in, navigating to the Customer Members page, clicking Add, filling required fields with valid test data, saving, and reporting the actual result. Use when Codex needs to run or verify the BO create-member flow in a browser, or when the user explicitly asks for the BO member creation test.
---

# BO Create Member Test

## Overview

Use this skill to perform the BO `Member` creation flow on the UAT web app.
Default to executing the workflow in a browser, not merely drafting a checklist.
Only produce a manual checklist when the user explicitly asks for documentation instead of execution.

## Browser Requirement

- Use the Browser Use plugin or another available browser automation tool to open and interact with the BO site.
- If no browser automation tool is available, state that execution is blocked and provide the exact workflow that would be run.
- Do not use the general web search tool for the BO app workflow.

## Execution Report Shape

Return a concise execution report:

- Environment / Module / Test type
- Member test data used, including the generated email, but do not repeat the password
- Steps completed
- Actual result
- Pass/fail status
- Validation issues, blockers, or screenshots if useful

## Required Test Data

- Login URL: `https://bo-cadw-ticketing-uat.ecr-aws.co.uk/auth/login?returnUrl=%2F`
- Username: `lehuy@janeto.com`
- Password: `12345.Com`
- Search term: `members`
- Navigation: `Customer > Members`
- Add button: red `Add`
- Email format: `phungkhacha+{random email}@teams.airlab.dev`

## Workflow

1. Start from the login URL and confirm the URL is the UAT BO environment.
2. Authenticate with the provided credentials.
3. Confirm the user lands on `Your ticketing`.
4. Search for `members`.
5. Open `Customer > Members`.
6. Click the red `Add` button.
7. Inspect the form and fill all required member fields with valid synthetic test data.
8. For `Email address`, always generate a unique value using `phungkhacha+{random email}@teams.airlab.dev`.
9. Save the member.
10. Verify the success message and confirm the new member appears in the list.

## Test Data Rules

- Use a different `{random email}` value for each test run, preferably timestamp-based, such as `phungkhacha+member20260506143000@teams.airlab.dev`.
- Use safe synthetic values for required non-email fields when the user has not provided exact data.
- Record every generated value in the execution report except the password.
- If the app exposes validation messages for missing or invalid fields, capture them and decide whether to correct the input or report a validation blocker.

## Guardrails

- Run only against the configured UAT URL unless the user explicitly supplies another non-production environment.
- Stop and report a blocker if the site requires CAPTCHA, MFA, unavailable credentials, or permissions that cannot be completed.
- Do not create duplicate test members with the same email.
- After saving, verify both the success notification and the created member's presence in the list whenever the UI allows it.
- If the user explicitly asks for a manual checklist, use this compact documentation format:
  - Title
  - Module / Priority / Type / Environment
  - Prerequisites
  - Test Data
  - Checklist Steps
  - Expected Result
  - Pass Criteria
  - Notes

## Manual Checklist Fallback

When execution is unavailable or the user asks only for documentation:

1. Open the login URL.
2. Log in with the provided credentials.
3. Confirm the user lands on `Your ticketing`.
4. Search for `members`.
5. Open `Customer > Members`.
6. Click the red `Add` button.
7. Fill all required member fields with valid data.
8. For `Email address`, always use the required format `phungkhacha+{random email}@teams.airlab.dev`.
9. Save the member.
10. Verify the success message and confirm the new member appears in the list.
