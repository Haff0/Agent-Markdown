# Guest Pass Feature Map

Use this as the default reading order when documenting Guest Pass logic.

## Primary Files

- `Codex-Membership/BoApi/Services/Implement/GuestPassesService.cs`
- `Codex-Membership/BoApi/Services/Interface/IGuestPassesService.cs`
- `Codex-Membership/BoApi/BoApi/Controllers/MembershipGuestPassesController.cs`
- `Codex-Membership/BoApi/BoApi/Controllers/MembershipWebsiteController.cs`

## Related Flows

- `Codex-Membership/BoApi/Services/Implement/MembershipMemberService.cs`
  - Guest pass creation during member creation and renewals
  - guest pass suspension and re-creation
- `Codex-Membership/BoApi/Services/Jobs/GuestPassRenewJob.cs`
  - guest pass expiration and renewal job

## Recommended Doc Split

- `guest-passes-create.md`
  - member lookup, code generation, expiry, status, persistence
- `guest-passes-update-status.md`
  - status transition logic and save behavior
- `guest-passes-get-by-member.md`
  - query rules, filtering, returned model shape
- `guest-passes-get-pdf.md`
  - PDF rendering, template replacement, brand selection, QR code generation
- `guest-passes-delete.md`
  - soft delete behavior
- `guest-passes-controller.md`
  - API endpoints and how they delegate to the service

## Doc Rules

- Document one function per file when the logic is independently meaningful.
- If a controller endpoint only forwards to a service method, document the forwarding behavior briefly and keep the main logic in the service doc.
- Include any special cases for `Active`, `Inactive`, `Used`, `Suspended`, or `Deleted` guest passes.
- Call out template branding for Hampshire and non-Hampshire branches.
