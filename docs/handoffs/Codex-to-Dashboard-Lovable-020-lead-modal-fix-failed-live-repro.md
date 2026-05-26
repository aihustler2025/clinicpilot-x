# Codex to Dashboard Lovable 020: Lead Modal Fix Failed Live Reproduction

Mode: Build

Action requested: Re-open and fix the Add/Edit Lead modal tab-switch bug. Handoff 018 is not verified.

## Context

Dashboard Lovable reported handoff 018 fixed the Add/Edit Lead modal disappearing/resetting when switching tabs/windows.

The owner and VA followed the deployment/cache guidance from handoff 019:

- Used the current preview URL.
- Hard refreshed.
- Logged out and logged back in.
- Retested the Add Lead modal.

The bug still happens.

## Current Live Reproduction

On the current preview:

`https://id-preview--429b406c-37ef-4d15-bcd5-c8384746cc95.lovable.app/leads`

Steps:

1. Log in.
2. Open `/leads`.
3. Click `Add Lead`.
4. The Add Lead modal opens.
5. Click/switch to another browser tab.
6. Return immediately to ClinicPilot X.

Actual result:

- The Add Lead modal is gone.

Expected result:

- The Add Lead modal remains open.
- Any typed/pasted data remains in place.

This happens even after hard refresh and fresh login, so please do not treat this as a stale bundle issue.

## Required Debugging

Please inspect the full modal open/close chain, not only `LeadFormDialog`.

Check:

- `src/pages/Leads.tsx` parent open state.
- Any `setIsDialogOpen(false)`, `setSelectedLead(null)`, or equivalent state reset.
- Any `useEffect` that responds to auth/user/session changes.
- React Query refetch on window focus, route refresh, or parent remount.
- Any `Dialog` wrapper props that still allow close on focus loss.
- Any `Tabs`, page-level click handler, visibility handler, or route-level auth guard that resets the Leads component.
- Whether `onOpenChange` is called with `false` during tab switch and why.

## Fix Requirement

The Add/Edit Lead dialog must not close due to:

- Browser tab switch.
- Window focus loss.
- Supabase `TOKEN_REFRESHED`.
- React Query refetch.
- Parent component re-render/remount.
- Focus outside event.
- Pointer outside event.

Allowed close paths:

- Successful save.
- Cancel button.
- X/close button.
- Escape, only if intentional and safe.

## Strong Recommended Implementation

If the issue is hard to isolate quickly, make the dialog state more defensive:

- Keep dialog `open` state controlled in `Leads.tsx`.
- Do not set `open=false` from `onOpenChange` unless the user explicitly clicks Cancel/X/Escape or save succeeds.
- Ignore `onOpenChange(false)` when it is caused by outside focus/pointer/tab switching.
- Preserve an in-memory draft while the dialog is open.
- Optionally add temporary console logs while debugging:
  - when `onOpenChange(false)` fires
  - why it fired
  - current `document.visibilityState`
  - current dirty state

Remove noisy debug logs before final report unless they are intentionally minimal and useful.

## Verification Required

Please verify in the live preview, not just by reasoning through code:

1. Open `/leads`.
2. Click `Add Lead`.
3. Type `Sarah Johnson` into Full Name.
4. Switch to another browser tab for 5+ seconds.
5. Return to ClinicPilot X.
6. Confirm modal is still open.
7. Confirm `Sarah Johnson` is still in the Full Name field.
8. Click outside the modal/backdrop.
9. Confirm modal does not close while dirty.
10. Use Cancel/X to close intentionally.
11. Repeat with Edit Lead and typed Notes.

## Response Back To Codex

Please respond with:

1. Confirmation that handoff 018 was not sufficient.
2. Root cause found in the live app.
3. Files changed.
4. Exact verification performed in the preview.
5. Whether the owner/VA should hard refresh again.

## Guardrails

Do not:

- Start Step 2B.
- Change DB schema.
- Change RLS.
- Add fake data.
- Change domain/DNS.
- Touch unrelated modules.

