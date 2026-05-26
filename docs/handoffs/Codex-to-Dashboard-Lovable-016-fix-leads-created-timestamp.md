# Codex to Dashboard Lovable 016: Fix Leads Created Timestamp

Mode: Build

Action requested: Apply a narrow frontend fix, then report back with the changed files and verification notes.

## Context

Codex verified Step 2A Leads CRUD in the live preview after Dashboard Lovable completed the source-aware Leads work.

Verified working:

- Dashboard quick actions now show `Add Lead`, `New Appointment`, `Send Test Notification`, and `Open Review Queue`.
- `Start AI Call`, `Send SMS`, and `Payment Link` were removed from dashboard quick actions.
- `Send Test Notification` is local-only and does not imply a real email/SMS provider is connected.
- `/leads` no longer presents itself as demo data.
- The empty real-data state works.
- `Add Lead` opens a modal.
- A real lead was created through the UI and persisted after refresh.
- Search works.
- Edit works.
- Status update persisted after refresh.

Test lead created during verification:

- Name: Sarah Johnson
- Email: `donjericho617+sarahjohnson@gmail.com`
- Phone: `+1 555 010 1001`
- Source: Manual
- Source detail: `manual-mvp-test`
- Service: Botox consultation
- Message: `I would like pricing and availability for a Botox appointment this week.`
- Notes after edit: `Updated by Codex: contacted status verification.`
- Final status after edit: Contacted

## Bug To Fix

The Leads table `Created` value is wrong immediately after creating a new lead.

Observed behavior:

- A newly created lead immediately showed `about 8 hours ago`.

Expected behavior:

- A newly created lead should show a correct local relative time such as `just now`, `less than a minute ago`, or `1 minute ago`.
- After refresh, the relative time should still be accurate.

## Scope

Fix only the Leads timestamp display/root cause.

Do not:

- Change database schema unless absolutely required.
- Add fake production data.
- Change RLS policies.
- Change auth/roles.
- Start Step 2B yet.
- Add paid/external integrations.
- Touch unrelated modules.

## Implementation Guidance

Please inspect how `created_at` is stored and rendered in the Leads page/hook/components.

Likely causes to check:

- UTC/local timezone parsing issue.
- Date string being parsed as local time when it should be UTC.
- Use of `new Date()` against a timestamp without timezone.
- Manual formatting helper subtracting the wrong offset.

Prefer a small shared helper if the same timestamp formatting will be reused in other modules, but keep the change minimal.

## Verification Required

After the fix, verify:

1. Create a new test lead in `/leads`.
2. Confirm the `Created` column says `just now`, `less than a minute ago`, or equivalent.
3. Refresh `/leads`.
4. Confirm the timestamp remains accurate.
5. Confirm existing search/filter/edit behavior still works.

Use a test email based on:

`donjericho617+timestamp-test@gmail.com`

## Response Back To Codex

Please respond with:

1. Summary
2. Files changed
3. Root cause
4. Verification performed
5. Any remaining risk

